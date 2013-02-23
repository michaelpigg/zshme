!SLIDE 
# Intro to Z Shell #

!SLIDE
* Installing zsh

!SLIDE bullets
# OS X with homebrew #
* 10.8 ships with 4.3.11
* homebrew version is 5.0.2
* brew install zsh
* add to /etc/shells
* run chsh

!SLIDE bullets
# BSD #
* install zsh from ports
* run chsh

!SLIDE bullets
# Configuring #
* Enable new completion system
* choose vi (or Emacs) mode
* Common shell options
** turn on autocd
** turn on appendhistory

!SLIDE
Cool Features

!SLIDE
no 'cd' required

!SLIDE
Suppose you have a client

!SLIDE
with a handful of products composed of a bunch of modules

!SLIDE
- src
-- client
--- product1
---- foo
---- bar
--- product2
---- baz
---- qux

!SLIDE
at ~, switch to foo
now to qux
now product1

!SLIDE
cdpath=(~/src/client/product1 ~/src/client/product2)

!SLIDE
command history

!SLIDE
command correction

!SLIDE
globbing

!SLIDE
# oh-my-zsh #

!SLIDE
# Unexpected Features #
*  find . -name *.pdf

!SLIDE
Resources

!SLIDE
zsh-lovers (http://grml.org/zsh/#zshlovers)

!SLIDE
brew install zsh-lovers
