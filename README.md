# Bash Aliases by Directory
A better way to keep organized and share bash/linux keyboard shortcuts (i.e. bash aliases)

Pretty simple.  

Clone to directory .kbd-aliases within your home directory  

`git clone https://github.com/dkebler/.kbd-aliases.git`  

Make sure your .bashrc file has this somewhere

```
if [ -f ~/.bash_aliases ]; then
    . ~/.bash_aliases
fi
```

if you don't currently have a .bash_aliases file then simply copy .bash_aliases.off in this repo to you home directory (one up) and remove the `.off` extension

otherwise

Add
```
for f in ~/.kbd-aliases/*; do
if [ ${f: -4} != ".off" ] && [ $(basename $f) != "README.md" ] ; then
  # echo 'loading alises '$f
. $f
fi
done
```

to your `.bash_aliases` file.  At which point you could move your aliases there into files within .kbd-aliases

Every file in `.kdb-aliases` will be sourced except ones ending with a `.off` extension and the README.md file of course.

If need to turn off some of your aliases just add `.off` to the file name rather than move or delete the file...simple.

To make use of aliases that open an editor set an EDITOR environment variable in .bashrc
e.g.
`export EDITOR=nano`
