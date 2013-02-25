!SLIDE 
# Intro to Z Shell #

Chariot Day 2013

!SLIDE
# Installing zsh #

!SLIDE left
# OS X with homebrew #

* 10.8 ships with 4.3.11
* homebrew version is 5.0.2
* brew install zsh
* add to /etc/shells
* run chsh

!SLIDE left 
# BSD #

* install zsh from ports
* run chsh

!SLIDE left 
# Configuring #

* Enable new completion system
* choose vi (or Emacs) mode
* Common shell options
** turn on autocd
** turn on appendhistory

!SLIDE
# Cool Features #

!SLIDE
# Cool Features #
no 'cd' required

!SLIDE
# enable autocd #

setopt autocd

<!SLIDE bullets> 

command line entries
  1. evaluated as possible commands
  2. evaluated as possible cd paths

<!SLIDE commandline incremental>

# autocd in action #

	$ Desktop
	~/Desktop

	$ foo
	~/Desktop/foo

	$ cd ~/Downloads
	~/Downloads


!SLIDE bullets
# cdpath power #

cdpath=(~)

!SLIDE commandline incremental
# autocd + cdpath in action #

	$ Desktop
	~/Desktop

	$ foo
	~/Desktop/foo

	$ Downloads
	~/Downloads


!SLIDE
Suppose you've checked out Apache Felix

!SLIDE

	@@@ sh
	.
	├── bundleplugin
	├── bundlerepository
	├── commons
	├── configadmin
	├── coordinator
	├── dependencymanager
	├── deploymentadmin
	├── deviceaccess
	├── doap
	├── eventadmin
	├── examples
	├── fileinstall
	├── framework
	├── framework.security
	├── gogo
	├── http
	├── http.jetty

!SLIDE
	@@@ sh
	├── installers
	├── io
	├── ipojo
	├── javax.servlet
	├── jmood
	├── jmxintrospector
	├── log
	├── main
	├── main.distribution
	├── maven-obr-plugin
	├── metatype
	├── mishell
	├── mosgi
	├── org.apache.felix.daemon
	├── org.osgi.compendium
	├── org.osgi.core
	├── org.osgi.foundation
	├── org.osgi.service.obr

!SLIDE
	@@@ sh
	├── prefs
	├── scr
	├── scrplugin
	├── service
	├── servicebinder
	├── shell
	├── shell.gui
	├── shell.gui.plugin
	├── shell.remote
	├── shell.tui
	├── sigil
	├── tools
	├── transaction
	├── upnp
	├── useradmin
	├── utils
	├── webconsole
	├── webconsole-plugins
	└── wireadmin

!SLIDE commandline
# autocd power #
	$ cdpath=(~/src/felix)
	~/src/felix
	$ upnp
	~/src/felix/upnp

	hack, hack, hackey, hack

	$ http/base
	~/src/felix/http/base

	more hacking	

!SLIDE commandline incremental
# autocd completion #
	$ http/<tab key>
	api/         bridge/      cometd/      proxy/       whiteboard/  
	base/        bundle/      jetty/       samples/     

	$ http/b<tab key>
	base/    bridge/  bundle/

!SLIDE
command history

!SLIDE commandline incremental
# command correction #
$ mnv clean install
zsh: correct 'mnv' to 'mvn' [nyae]?

!SLIDE
# globbing #
* recursive globbing

!SLIDE commandline incremental
# find all poms #
    $ ls **/pom.xml

!SLIDE commandline incremental
# find all poms with snapshot versions #
    $ find . grep -SNAPSHOT {} \;

!SLIDE
# Unexpected Features #
    $ find . -name *.pdf
    zsh: no matches found: *.pdf

    $ find . -name "*.pdf"
    foo/bar.pdf
    baz/quz.pdf

!SLIDE
# oh-my-zsh #

!SLIDE
Resources

!SLIDE
zsh-lovers (http://grml.org/zsh/#zshlovers)

!SLIDE
brew install zsh-lovers
