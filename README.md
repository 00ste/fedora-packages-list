# Fedora Packages List

A system I use to manage dnf and Flatpak packages declaratively on Fedora Linux.

# Usage

The `install.sh` script does the following:

- installs all packages in `*-list.txt` that are not in `*-lock.txt`
- removes all packages in `*-lock.txt` that are not in `*-list.txt`
- overwrites `*-lock.txt` with the contents of `*-list.txt`

To install a package, instead of running `sudo dnf install <package>` or
`flatpak install <package>`, add the package name inside the file `dnf-list.txt`
for dnf packages and `flatpak-list.txt` for flatpak packages, then run
`install.sh`.

> Even though they are called "lock" files, `*-lock.txt` are not real lock
> files, that lock specific versions of packages. Instead, they just contain the
> "currently installed" packages.

The scripts `*-install.sh` look for the respective list and lock files in the
directory `~/pkglist`, so make sure to edit those scripts if you place them in a
different location. I was too lazy to set up a better solution, and I didn't
want this system to get overly complicated.
