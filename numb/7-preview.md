Semplice 7-preview "Comfortably Numb"
=====================================

It's our pleasure to announce the release of Semplice 7-preview, codenamed "Comfortably Numb".

After long delays on the Semplice 7 cycle, we are now pretty confident to make
a preview release available to the general public.

This release ships with the latest sid at the moment of build (2014-11-27) and with
Linux kernel 3.17.2.

Known issues
------------

We have squashed as many bugs as possible, but given the huge under-the-hood changes
that this cycle had we are rolling-out a preview release first.  
Expect bugs to be present.

Additionally, please keep in mind the following notes about this preview snapshot:

* There is no user interface to add, modify and remove users/groups  
  This has been implemented in master, soon it will land into the development repositories.
* There is no user interface to modify power management preferences  
  This has been implemented in vera-control-center version [0.32-1](https://github.com/vera-desktop/vera-control-center/compare/debian/0.31-1...debian/0.32-1)
* tlp (power management) is missing  
  tlp is now into the repositories and will be automatically installed at the next upgrade.
* The new desktop launcher is not reliable and may not show some applications.
  Reliability issues and other bugfixes have been resolved in vera-plugin-desktop version [0.26-1 and 0.27-1](https://github.com/vera-desktop/vera-plugin-desktop/compare/debian/0.25.0-1...debian/0.27.0-1)
* The new login greeter is missing  
  This has been postponed to Semplice 8.
* It's not possible to set different backgrounds on multiple monitors.  
  This is only an user interface issue, as it's still possible to set
  different backgrounds manually  
  This has been implemented in vera-control-center version [0.33-1](https://github.com/vera-desktop/vera-control-center/compare/debian/0.32-2...debian/0.33-1)
* There is no user interface to configure the applications to autostart  
  This has been implemented in vera-control-center version [0.31-1](https://github.com/vera-desktop/vera-control-center/compare/debian/0.30-1...debian/0.31-1)
* Only GTK+3 applications take advantage of the "vera-color" feature.  
  There are plans to expand this feature to GTK+2 applications.  
  vera-color Openbox support has been implemented in vera-plugin-openbox version [0.29-2](https://github.com/vera-desktop/vera-plugin-openbox/compare/debian/0.28-1...debian/0.29-2)  
  vera-color GTK+2 support has been implemented in vera-plugin-desktop version [0.31](https://github.com/vera-desktop/vera-plugin-desktop/commit/0dbc6a2fd2de3eead8f087985a861f06f0865b08).
* Translation support for vera is missing  
  This has been implemented. Check [Transifex](https://www.transifex.com/organization/semplice/dashboard) to help with translations.
* You must enable the MPRIS2 pragha plugin to get the music player controls
  in the menu.  
  Open Pragha Music Player, then Tools -> Preferences -> Plugins, then
  tick the "Mpris2" checkbutton.  
  This has been resolved with pragha version 1.3.1+git20141121-10.
* The installer fails to accept LVM/LUKS+LVM configurations. [linstaller bug #4](https://github.com/semplice/linstaller/issues/4)  
  This has been fixed in [linstaller commit c32de7e](https://github.com/semplice/linstaller/commit/c32de7eceb977eae13ab8562be5fc875d427edd9) and released
  as linstaller version 6.2.1.  
  Just ensure you update the installer via the built-in method.
* Both isos are big, expecially the 32-bit one. **They** still **fit** in a normal,
  700 MB CD, but we'll do our best to lower the final iso image.
* Images put into an USB drive using dd/cat do not boot in BIOS systems **only**.  
  EFI boot works fine.  
  If you want to put Semplice 7-preview in an USB drive and you have a BIOS-powered
  machine, use UNetbootin (this will be obviously fixed in the final release)
* The screen auto-locks in live session.  
  To exit from the screensaver you must use the "live" password.  
  This is tracked in [live-config-semplice bug #1](https://github.com/semplice/live-config-semplice/issues/1) and fixed in [live-config-semplice commit ac24121](https://github.com/semplice/live-config-semplice/commit/ac2412166525270ae5260e12d9eece9c295a5ef7).

We are commited to solve all these issues before distributing the final release.

Upgrading
---------

While we strive to offer full upgrade compatibilty between near Semplice releases,
the Semplice 6 -> 7-preview upgrade hasn't been tested throughly and end users
should not attempt to upgrade.

It will be possible to upgrade to the final 7 release when it will be made
available.

Installation notes
------------------

An installed Semplice 7-preview system will regularly get updates and will
upgrade to Semplice 7 without problems, but it will still look for updates
in the development channels.

This means that users installing Semplice 7-preview will take part of the
Semplice 8 development.

Instructions on how to opt-out from the development channel will be shared
after the final Semplice 7 release.

What's new?
-----------

This release brings many changes since Semplice 6, most notably the new
[vera desktop environment](https://github.com/vera-desktop).

There are also many minor chnages that haven't been listed here.

### Pulseaudio now enabled by default ###

Pulseaudio is now enabled by default. This also means that users with multiple
audio cards will not have to manually set the right audio card as the default.

Note that Pulseaudio can be disabled during installation by flipping the relevant
switch and at any time by going to Settings -> Features.

### PCManFM compiled against GTK+3 ###

Semplice 7 ships a custom PCManFM version in the package pcmanfm-semplice.  
This version is compiled against GTK+3 and also re-introduces the "Open as
administrator" menu option.

### New power management indicator ###

xfce4-power-manager has been replaced with [vera-plugin-power](https://github.com/vera-plugin-power), an
upower-based vera plugin that keeps track of the current battery level
of connected devices.

### New screenshooter ###

xfce4-screenshooter has been removed as the Screenshot capability is built-in
in vera.

### Chromium replaced by Iceweasel ###

Chromium has been replaced by Iceweasel.  
It's our plan to ship "vanilla" Mozilla-branded Firefox releases in the future.

### Desktop launcher ###

The Desktop Environment, via the [vera-plugin-desktop](https://github.com/vera-plugin-desktop) plugin, 
provides a keyboard-driven launcher, that permits to easily launch applications.

### Interactive tutorial ###

New users can enjoy a new, interactive, tutorial about the basics of Semplice.

### "Web application support" removed ###

The "Web application support" feature, introduced in Semplice 5, has been removed from the standard
system.  
It's still available for existing users and after the installation of the meta-openbox-feature-oneslip
package.

### Exaile replaced by Pragha ###

Exaile has been replaced by Pragha Music Player.

### Menu module for MPRIS2 media players ###

The Exaile menu module has been replaced by a generic extension that
supports every media player compilant with the MPRIS2 specification. This
include Pragha and Spotify.

### Under-the-hood changes ###

Our menu generator and framework, [alan2](https://github.com/semplice/alan2) has been
ported to GTK+3 and GMenu3.

The [quickstart](https://github.com/semplice/quickstart) library has been
ported to Python 3.  
In addition, more features have been implemented, most notably support for
Scenes.

Keeptalking has been ported to Python 3 and systemd, and the new version is
named [keeptalking2](https://github.com/semplice/keeptalking2).  
Keeptalking2 can still work without systemd by using the fallback mode.  

### Control center ###

Thanks to the vera effort, we are happy to roll-out a [new control center](https://github.com/vera-desktop/vera-control-center).

Old configuration tools have been removed as most of the things are integrated in the control center.

### New artwork ###

Semplice 7 has an entire new artwork, sporting a [modified Zukitre theme](https://github.com/semplice/zuki-themes) and
the Moka icon theme.

Additionally, the theme adapts to the current wallpaper.

### vera ###

This is probably the biggest feature of this cycle.

vera is a new, plugin-oriented GTK+3 Desktop Environment. The current
implementation is of course a bit rough and does not embrace our vision
fully.  
We are commited to make vera the central part of the upcoming Semplice
releases.

As the project is still at its early stages, vera doesn't really
differentiate with a normal, configured Openbox installation.
