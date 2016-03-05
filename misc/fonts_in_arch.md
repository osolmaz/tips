# Problems with Fonts in Arch Linux

Note for future self:

If you have the issue of overridden fonts, like application fonts don't change
no matter what you do, check the ~/.gtkrc-2.0 file or the one for .gtk-x.0. The
settings there override the desktop environments', and don't show up in any
configuration manager.

KDE is an asshole for generating that file. I mean, why...
