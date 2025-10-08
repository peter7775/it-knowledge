## mt
## dump
## restore
## tar
## cdrecord
## rsync

### archive mode (-a or --archive)
It's all of these:
    -r, --recursive recurse into directories
    -l, --links copy symlinks as symlinks
    -p, --perms preserve permissions
    -t, --times preserve modification times
    -g, --group preserve group
    -o, --owner preserve owner (super-user only)
    -D same as --devices --specials
    --devices preserve device files (super-user only)
    --specials preserve special files

It excludes:
    -H, --hard-links preserve hard links
    -A, --acls preserve ACLs (implies -p)
    -X, --xattrs preserve extended attributes

https://serverfault.com/questions/141773/what-is-archive-mode-in-rsync