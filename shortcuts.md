# Tar

`tar -c --use-compress-program=pigz -f tar.file dir_to_zip` Use pigz parallel implementation of gzip

# Apt

`apt-cache show <package name>` Get information about a package

# Git

`git checkout -b myfeature develop` Branch off from `develop` branch, switch to branch `myfeature`

Merge work from `myfeature` into `develop` branch
```
git checkout develop
git merge --no-ff myfeature
git branch -d myfeature
git push origin develop
```

`git add -A` stage all changes

`git add -u` stage modifications and deletions, without new files

`GIT_SSH_COMMAND="ssh -i ~/.ssh/id_rsa_example" <git command>` Specify identity file

# Git-fugitive

The Git index is where you put changes that you want to be included in the next commit.

`<leader>ga` Stage the current file

`<leader>gs` Bring up a summary window vaguely akin to git-status

`<leader>gc` A wrapper around git-commit. A new tab will be used to obtain
             a commit message. Write and close that window (:wq or |:Gwrite|)
             to finish the commit. 

`<leader>gt` ???

`<leader>gd` Perform a |vimdiff| against the index version of the current file.

`<leader>ge` |:edit| a |fugitive-object|

`<leader>gr` From the working copy, reset all changes. OR from the index file,
             add all changes from the current file to the index file. 

`<leader>gw` From the working copy, add all changes from the current file to
             the index file. OR from the index file, reset all changes to 
             the working copy.

`<leader>gl` 

`<leader>gp`

`<leader>gm` Rename/relocate file, update buffer

`<leader>gb`

`<leader>gb` 

`<leader>go` 

`<leader>gps` 

`<leader>gpl` 

`[c` In vimdiff, jump to previous changeset

`]c` In vimdiff, jump to next changeset


# Tmux

`ls` List active sessions

`a -t n -d` Attach to session number `n` and disconnect any other screens

`,` Name window

`$` Name session

# Vim

## vimrc

Python compatible tabs
```
filetype plugin indent on
" show existing tab with 4 spaces width
set tabstop=4
" when indenting with '>', use 4 spaces width
set shiftwidth=4
" On pressing tab, insert 4 spaces
set expandtab
```

## Moving

`zz` Center current line on screen

`Ctrl + e` Move screen up without moving cursor

`Ctrl + y` Move screen down without moving cursor

`Ctrl + o` Jump to last edit location

`Ctrl + i` Jump to next edit location

## Windows

`Ctrl + w{h,j,k,l}` move focus to {left, lower, upper, right} split

`:vsplit <another file>` Open another file in side-by-side split

`Ctrl + wx` Swap split

`Ctrl + w=` Equalize split

`Ctrl + wo` Close other windows

## Tabs

`:tabm i` Move tab to position `i`

`:tabm +i` Move tab right `i` positions

`:tabm -i` Move tab left `i` positions

## Buffers

`<leader>h` Switch to left buffer

`<leader>l` Switch to right buffer

## Bookmarks

`ma` Set position for mark `a`

`` `a`` Jump to location at mark `a`

`:bd` Unload the buffer, delete it from the buffer list, losing changes

`:bw` Unload the buffer, delete it from the buffer list, writing changes

## Formatting

`gqq` Format entire document

## Editing

`da[` Delete around left bracket

## Cut and paste

`yi"` yank in quotation marks

`<C-R> "` Paste ring buffer into command line

`y(` yank from beginning of sentence

`y)` yank to end of sentence

### Ctrlp

* Press `<F5>` to purge the cache for the current directory to get new files, remove deleted files and apply new ignore options.
* Press `<c-f>` and `<c-b>` to cycle between modes.
* Press `<c-d>` to switch to filename only search instead of full path.
* Press `<c-r>` to switch to regexp mode.
* Use `<c-j>`, `<c-k>` or the arrow keys to navigate the result list.
* Use `<c-t>` or `<c-v>`, `<c-x>` to open the selected entry in a new tab or in a new split.
* Use `<c-n>`, `<c-p>` to select the next/previous string in the prompt's history.
* Use `<c-y>` to create a new file and its parent directories.
* Use `<c-z>` to mark/unmark multiple files and `<c-o>` to open them.

# Conda

`conda info --envs` View a list of environments

`conda create --name myclone --clone myenv` Clone an environment

`conda remove --name myenv --all` Remove an environment

`conda list --explicit > spec-file.txt` List packages installed in environment, write to `spec-file.txt`

`conda create --name myenv --file spec-file.txt` Create new environment from `spec-file.txt`

# Other

Accidentally pressed `Ctrl+s`: `Ctrl+q` to unlock

# System

## GPU

`fuser -v /dev/nvidia*` What process(es) are using the GPU?

## Rsync

`rsync -avzP –include ‘*.txt’ –exclude ‘*’ /src/dir user@10.10.1.10:/dst/dir` Sync a local directory to a remote directory, with progress bar

`rsync -e "ssh -i ~/.ssh/abc_rsa" /src/dir user@10.10.1.10:/dst/dir` Use an identity file

Ref: https://linuxtechlab.com/start-with-rsync-command-8-rsync-examples/

## SCP

`scp -i ~/.ssh/abc_rsa` Use identity file `abc_rsa`
`scp -r` Copy a directory

## PyTorch

`tensor.detach()` creates a tensor that shares storage with tensor that does not require grad

`tensor.clone()` creates a copy of tensor that imitates the original tensor's requires_grad field

> You should use detach() when attempting to remove a tensor from a computation graph, and clone as a way to copy the tensor while still keeping the copy as a part of the computation graph it came from.

> tensor.data returns a new tensor that shares storage with tensor. However, it always has requires_grad=False (even if the original tensor had requires_grad=True

> You should try not to call tensor.data in 0.4.0. What are your use cases for tensor.data?

> tensor.clone() makes a copy of tensor. variable.clone() and variable.detach() in 0.3.1 act the same as tensor.clone() and tensor.detach() in 0.4.0.

Ref: https://discuss.pytorch.org/t/clone-and-detach-in-v0-4-0/16861/2

## MySQL

`mysql --host=<ip> --port=<port> -u <username> -p` Connect to server, prompt for password

Ref: https://gist.github.com/hofmannsven/9164408

## PyTorch

Ref: https://jhui.github.io/2018/02/09/PyTorch-neural-networks/

> The difference between torch.nn and torch.nn.functional is very subtle. In fact, many torch.nn.functional have a corresponding equivalent in torch.nn. For layers with trainable parameters, we use torch.nn to create the layer. 

> In many code samples, it uses torch.nn.functional for simpler operations that have no trainable parameters or configurable parameters.

# Shortcuts

`find /wbdata/Datasets/output1/ -type f \( -name "*.jpg" \) -printf "%f\n" |sed 's/\.jpg$//1' > all.txt`

`ffmpeg -r 2 -i '%*.jpg' fullstitch.mp4` Stitch a bunch of jpegs together into a video at 2 fps

`ssh user@server "echo \"`cat ~/.ssh/id_rsa.pub`\" >> .ssh/authorized_keys"` Copy public key to authorized_keys on remote machine

`ps afx` Get a listing of all processes and child processes with full commands

`usermod -a -G sudo geek` Add existing user to existing group
