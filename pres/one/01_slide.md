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

!SLIDE smaller incremental
# first login #
    @@@
    This is the Z Shell configuration function for new users,
    zsh-newuser-install.
    You are seeing this message because you have no zsh startup files
    (the files .zshenv, .zprofile, .zshrc, .zlogin in the directory
    ~).  This function can help you with a few settings that should
    make your use of the shell easier.

    You can:

    (q)  Quit and do nothing.  The function will be run again next time.

    (0)  Exit, creating the file ~/.zshrc containing just a comment.
         That will prevent this function being run again.

    (1)  Continue to the main menu.

    --- Type one of the keys in parentheses --- 

* Don't Panic!
* type q

!SLIDE smaller skip
# first login #
    @@@
    Please pick one of the following options:

    (1)  Configure settings for history, i.e. command lines remembered
         and saved by the shell.  (Recommended.)

    (2)  Configure the new completion system.  (Recommended.)

    (3)  Configure how keys behave when editing command lines.  (Recommended.)

    (4)  Pick some of the more common shell options.  These are simple "on"
         or "off" switches controlling the shell's features.  

    (0)  Exit, creating a blank ~/.zshrc file.

    (a)  Abort all settings and start from scratch.  Note this will overwrite
         any settings from zsh-newuser-install already in the startup file.
         It will not alter any of your other settings, however.

    (q)  Quit and do nothing else.  The function will be run again next time.
    --- Type one of the keys in parentheses --- 

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

!SLIDE incremental
# command history #

* share history between sessions

    @@@ sh
    setopt share_history

* append history

    @@@ sh
    setopt append_history

!SLIDE
# matching in command history #
    @@@ sh
    bindkey '^[[A' up-line-or-search
    bindkey '^[[B' down-line-or-search

!SLIDE commandline incremental
# (a)typical day #
    $ mvn clean install
    [Build Failed]

     hack, hack, hackey, hack

    $ mvn clean install -DskipTest=true
    [Build Successful]
    $ git commit -m "Awesome code"
    $ git push

    Did I just break the build?

    $ mvn<up arrow>
    $ mvn clean install -DskipTest=true<up arrow>
    $ mvn clean install<enter>
    [Build Successful]

    Phew!

!SLIDE commandline incremental
# command correction #
    $ mnv clean install
    zsh: correct 'mnv' to 'mvn' [nyae]?

!SLIDE
# globbing #
* recursive globbing

!SLIDE commandline incremental

# find all poms in #

~/src/felix/gogo

    $ ls **/pom.xml
    command/pom.xml     pom.xml         shell/pom.xml
    gogo-parent/pom.xml runtime/pom.xml

!SLIDE commandline incremental

# find poms with snapshot versions #

~/src/felix/gogo

    $ grep SNAPSHOT **/pom.xml

    command/pom.xml:  <version>0.9.0-SNAPSHOT</version>
    gogo-parent/pom.xml:    <version>0.7.0-SNAPSHOT</version>
    pom.xml:    <version>0.7.0-SNAPSHOT</version>
    runtime/pom.xml:    <version>0.9.0-SNAPSHOT</version>
    shell/pom.xml:    <version>0.9.0-SNAPSHOT</version></version>

!SLIDE commandline incremental skip

# Unexpected Features #

    $ find . -name *.pdf
    zsh: no matches found: *.pdf

    $ find . -name "*.pdf"
    foo/bar.pdf
    baz/quz.pdf

!SLIDE

# oh-my-zsh #

Quick, easy installation with good defaults

* plugins system
    * git 
    * mvn
    * etc (https://github.com/robbyrussell/oh-my-zsh/tree/master/plugins)
* themes

!SLIDE
Resources

!SLIDE
zsh-lovers (http://grml.org/zsh/#zshlovers)

!SLIDE
brew install zsh-lovers
