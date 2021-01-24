## zfs-autoload-keys

This script queries ZFS for passphrase-prompt volumes, and then attempts to
locate and load keys for those volumes via a naming scheme:

```
  $HOSTNAME.$POOLNAME.$VOLUMEPATH.zfs
```
slashes are replaced with dots, and dot-segments are dropped until a keyfile
is found or there are no more segments. The text of the keyfile is piped
directly to `zfs load`. Currently, only fetching keys via `curl` is supported.


