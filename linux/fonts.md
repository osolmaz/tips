# Good font rendering in unconfigured installs such as Arch and Debian

In Arch, installing infinality seems to resolve the issue.

In Debian, installing infinality proved to be more tedious than expected, so I
found the following solution online:

Create the following file and either put it in

- `~/.config/fontconfig/fonts.conf`
- or `/etc/fonts/conf.avail/10-hinting.conf`, and then link it into `/etc/fonts/conf.d`.

```xml
<?xml version="1.0"?>
<!DOCTYPE fontconfig SYSTEM "fonts.dtd">
<fontconfig>
  <match target="font">
    <edit name="antialias" mode="assign"><bool>true</bool></edit>
  </match>
  <match target="font">
    <edit name="hintstyle" mode="assign"><const>hintslight</const></edit>
  </match>
  <match target="font">
    <edit mode="assign" name="hinting"><bool>true</bool></edit>
  </match>
  <match target="font">
    <edit name="rgba" mode="assign">
      <const>rgb</const>
    </edit>
  </match>
</fontconfig>
```
