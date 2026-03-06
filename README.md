# APT Repository

This is the APT (Debian/Ubuntu) package repository for [jmerhar/scripts](https://github.com/jmerhar/scripts) — a collection of shell and Perl scripts for macOS and Linux.

Packages are signed with a GPG key to ensure authenticity and integrity.

## Available packages

<!-- BEGIN TABLE -->
| Package | Description |
|---------|-------------|
| `local-backup` | A generic script to create and automatically prune rsync-based system backups. |
| `photo-backup` | A robust script for backing up photo collections from multiple sources to a remote server using rsync. |
| `remove-sidecars` | A script to find and delete "sidecar" files when a corresponding RAW photo file exists. |
| `unlock-pdf` | Decrypts a password-protected PDF file using the 'qpdf' command-line tool. |

<!-- END TABLE -->

## Installation

### 1. Add the GPG key

```bash
sudo mkdir -p /etc/apt/keyrings
wget -qO- https://jmerhar.github.io/apt-scripts/public.key | sudo gpg --dearmor -o /etc/apt/keyrings/jmerhar-scripts.gpg
```

### 2. Add the repository

```bash
echo "deb [arch=all signed-by=/etc/apt/keyrings/jmerhar-scripts.gpg] https://jmerhar.github.io/apt-scripts/ stable main" | sudo tee /etc/apt/sources.list.d/jmerhar-scripts.list
```

### 3. Install packages

```bash
sudo apt-get update
sudo apt-get install unlock-pdf
```

For more details on each script, see the [main repository](https://github.com/jmerhar/scripts).

## GPG Signing Key

All packages and the repository metadata are signed with the following GPG key:

| Property | Value |
|----------|-------|
| **UID** | `jmerhar-bot <dev@merhar.si>` |
| **Fingerprint** | `E949 5DC0 EB91 48C5 6D62 793B 8DF9 1E70 7EE1 EAA9` |
| **Created** | 2025-08-27 |
| **Expires** | Never |

You can verify the fingerprint after importing the key:

```bash
gpg --show-keys /etc/apt/keyrings/jmerhar-scripts.gpg
```

If the key is ever rotated, a new `public.key` will be published here and existing users will need to re-import it using the installation step above.

## License

The scripts distributed in this repository are released under the [MIT License](LICENSE).
