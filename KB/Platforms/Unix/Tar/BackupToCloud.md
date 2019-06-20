## Backup to Cloud

tar/split with compression:

    tar zcf - file1 file2 ... | split -b 1024m - backup.tar.gz.

join/untar with decompression:

    cat backup.tar.gz.* | tar zxvf -


