<div id="table-of-contents">
<h2>Table of Contents</h2>
<div id="text-table-of-contents">
<ul>
<li><a href="#sec-1">1. urxvt Terminal Configuration</a>
<ul>
<li><a href="#sec-1-1">1.1. Installation</a>
<ul>
<li><a href="#sec-1-1-1">1.1.1. Keybindings for tabs</a></li>
</ul>
</li>
</ul>
</li>
</ul>
</div>
</div>

# urxvt Terminal Configuration<a id="sec-1" name="sec-1"></a>

## Installation<a id="sec-1-1" name="sec-1-1"></a>

First you need to install the packages *rxvt-unicode* and *xsel*. If you use 
*Ubuntu* you can install those packages with

    $ sudo apt install -y rxvt-unicode xsel

rxvt-unicode is the package name of URxvt. And xsel is a clipboard manager.
You also need the *Perl* extension to send the marked text to *xsel*. 

Run the following commands to configure *urxvt terminal*:

    $ git clone https://github.com/marianogaragiola/urxvt_config.git
    $ cd urxvt_config
    $ mkdir -p $HOME/.urxvt/ext
    $ cp resources/* $HOME/.urxvt/ext/
    $ cp Xresources $HOME/.Xresources
    $ xrdb .Xresources

### Keybindings for tabs<a id="sec-1-1-1" name="sec-1-1-1"></a>

The default configuration of *urxvt* terminal for create and switch between tabs 
is using the *Shift* key, this can be changed by the key *Control* modifying the 
file */usr/local/x86_64-linux-gnu/urxvt/perl/tabbed*. In line 353 reads:

    if ($event->{state} & urxvt::ControlMask) {

All you have to do, is replace "Shift", with "Control". The line must look like this:

    if ($event->{state} & urxvt::ControlMask) {
