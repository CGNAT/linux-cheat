# truncate

GNU Coreutils.

CLI for the `truncate` [POSIX 2007 function](http://pubs.opengroup.org/onlinepubs/9699919799/functions/truncate.html), implemented through the truncate system call.

Sets file to given size.

If greater, pads with 0s. Sparse files are generated by default.

If smaller, data loss.

Operates inline without mercy, only works on files.

    printf 'ab' > /tmp/a
    truncate -s 1 /tmp/a
    [ "$(cat f)" = 'a' ] || exit 1

Negative values truncate up to from the end:

    echo abc > f
    truncate -s -1 f
    [ `cat f` = ab ] || exit 1

*Must* have a space: `-s -1`, *not* `-s-1`.
