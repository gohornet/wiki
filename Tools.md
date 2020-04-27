HORNET has an integrated toolset.

### Autopeering seed generator

Generates an autopeering seed.<br>
**Note:** This tool is not intended for the creation of autopeering seeds for production usage.

```bash
hornet tool seedgen
```

### Password SHA256 sum generator

Generates an sha265 sum from your password and salt.

```bash
hornet tool pwdhash
```

### Merkle tree generator

Generates a merkle tree for the coordinator plugin.

This tool assumes that:

1. The merkle tree file path, the security level and the merkle tree depth is set to your needs ([Coordinator configuration docu](https://github.com/gohornet/hornet/wiki/Configuration#Coordinator))
2. The environment variable `COO_SEED` with your seed is set and available

**Note:** The below listed example assumes that you have installed HORNET with APT (or the `.deb` package). Otherwise please adapt the config dir path.

```bash
COO_SEED="YOUR9COO9SEED9HERE..." hornet -d /var/lib/hornet tool merkle
```
