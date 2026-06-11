# Fedora Packages List

A system I use to manage dnf and Flatpak packages declaratively on Fedora Linux.

# Usage

The `install.sh` script does the following:

- installs all packages in `*-list.txt` that are not in `*-lock.txt`
- removes all packages in `*-lock.txt` that are not in `*-list.txt`
- overwrites `*-lock.txt` with the contents of `*-list.txt`

The list and lock files are stored into `~/.config/pkglist`, and they will be generated when running the script if not already present. The list file should contain a package for each line.

To install a package, instead of running `sudo dnf install <package>` or
`flatpak install <package>`, add the package name inside the file `dnf-list.txt` for dnf packages and `flatpak-list.txt` for flatpak packages, then run `install.sh`. The list file should contain one package name per line, lines starting with a hash `#` are treated as comments. For example:

```
# Internet
chromium
firefox
thunderbird

# Networking
syncthing
podman
docker-ce
docker-ce-cli
filezilla

# ...
```
