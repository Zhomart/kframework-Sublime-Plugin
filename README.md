# Jump to Section

* [Installation](#installation)

# Installation

## via Package Control

> This is the recommended installation method.

If you have Sublime Package Control, you know what to do. If not, well: it's a package manager for Sublime Text 2; it's awesome and you can [read about it here](http://wbond.net/sublime_packages/package_control).

To install Package Control, open the Python Console (`ctrl+'` or ``cmd+` ``) and paste the following into it:

    import urllib2,os; pf='Package Control.sublime-package'; ipp=sublime.installed_packages_path(); os.makedirs(ipp) if not os.path.exists(ipp) else None; urllib2.install_opener(urllib2.build_opener(urllib2.ProxyHandler())); open(os.path.join(ipp,pf),'wb').write(urllib2.urlopen('http://sublime.wbond.net/'+pf.replace(' ','%20')).read()); print 'Please restart Sublime Text to finish installation'

After installing the package and restarting the editor:

* Open the Command Pallete (`ctrl+shift+P` or `cmd+shift+P`).
* Type "Install Package" and hit return.
* Type "kframework" and hit return.

## via Source Control

> If you plan to contribute, then you should install via this method. Otherwise it is recommended that you install the package via Package Control, see above.

Sublime stores packages in the following locations:

  Nix: ~/.config/sublime-text-2/packages
  Mac: ~/Library/Application\ Support/Sublime\ Text\ 2/Packages
  Win: %APPDATA%\Sublime Text 2\Packages

### As a repository within the packages directory

Open a Terminal/Console and run the following commands, replacing `PACKAGE_PATH` with the path corresponding to your OS above.

  cd PACKAGE_PATH
  git clone https://github.com/Zhomart/kframework-Sublime-Plugin.git kframework

### As a repository outside of the packages directory

If you use Github for Mac/Windows which store repositories in a specific location, or if you just don't want a repository in your packages directory, then instead you can use a link.

If you don't yet have the repository, then grab it via your GUI program or via the command line:

  cd WHEREVER_YOU_WANT
  git clone https://github.com/Zhomart/kframework-Sublime-Plugin.git

Once that is done, we will create the link:

#### Windows:

  cd PACKAGE_PATH
  mklink /D kframework ABSOLUTE_PATH_TO_REPOSITORY

#### Nix/Mac:

  cd PACKAGE_PATH
  ln -s ABSOLUTE_PATH_TO_REPOSITORY kframework

#### A note on Package Control

When Package Control tries to update your packages, if you have a repository in your packages directory then it will try to pull down and merge any changes. If you don't want this to happen and would rather handle everything yourself, then you can add the following to your settings (Preferences » Package Settings » Package Control » Settings - User):

  "auto_upgrade_ignore": ["kframework"]
