## vim-parinfer

this is a vim plugin for using [parinfer](https://shaunlebron.github.io/parinfer/) to indent your clojure and lisp code.

<h5 style="color: blue;"> **WIP** pull requests // issues welcome </h5>

## Installation 

### using pathogen: 

```
cd ~/.vim/bundle
git clone git://github.com/bhurlow/vim-parinfer.git
cd vim-parinfer && npm install 
```
### using Vundle:

add 

```
Plugin 'bhurlow/vim-parinfer'
```

to your `.vimrc`

run
 
```
:PluginInstall
```
in vim
 
and finally:

```
 cd ~/.vim/bundle/vim-parinfer/ && npm install
```


## Mappings 

I'm still getting a feel for what the most idiomatic mappings for vim parinfer should be. As suggested by the parinfer site, I've mapped `<Tab>` to perform a smart indent and `Shift + <Tab>` to un-indent. 

Currently text changes in insert mode changes **do not** cause parinfer evaluation. The eval is caused when ***leaving*** insert mode. 

## Notes

This is a really basic wrapper that shells out to a node.js server which parses the clj text using the parinfer js module target. This is cool because it allows us to upgrade the parinfer lib without changing any vim code. Also the less vimscript the better imho. Also you should know that ~~the entire buffer~~ the top level form by your cursor is sent to the parser on every ~~cursor move~~ indent and `InsertLeave` event.

## Todos

- scope vars in script instead of global 
- toggle between indent and paren mode
- catch parsing errors in node server
- set-able server port 
- handle other filetypes besides clojure 



