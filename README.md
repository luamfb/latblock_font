### About

This is a textual representation of a PSF (PC Screen Font),
meant to be used in the Linux console after being converted
to the actual PSF file, as explained below.

This is a 512-bit 8x16 pixels font that was obtained by
augmenting the font `Lat15-Terminus16.psf.gz`,
(as named in Debian, and which can be [seen here][lat15-terminus16-screenshot])

This font contains all of the original font's codepage, plus
all Unicode Block Elements, which allows some neat `figlet` fonts
to be displayed in the console.

### Converting to PSF and using

Convert this to a .psf file with
```
$ $PATH_TO_CMD/psftx2psf --no-strict < latblock.psftx >latblock.psf
```

The psftx2psf command is part of the
[console font utils][console-font-utils-page],
and can be obtained with
```
$ git clone git://git.zap.org.au/data/git/console-fonts-utils.git
```

Then move the .psf file to `/usr/share/consolefonts`
(optionally compressing it with gzip first).

Then, one can set the font temporarily with

```
$ setfont latblock
```

And set it permanently by changing the `FONT` variable in
`/etc/default/console-setup` to `latblock.psf`
(or `latblock.psf.gz` if compressed).

[console-font-utils-page]: https://www.zap.org.au/projects/console-fonts-utils/
[lat15-terminus16-screenshot]: https://www.zap.org.au/projects/console-fonts-distributed/psftx-debian-10.5/Lat15-Terminus16.psf.png
