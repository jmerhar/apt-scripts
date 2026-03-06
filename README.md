# APT Repository

This is the APT (Debian/Ubuntu) package repository for [jmerhar/scripts](https://github.com/jmerhar/scripts) — a collection of shell and Perl scripts for macOS and Linux.

Packages are signed with a GPG key to ensure authenticity and integrity.

## Available packages

<!-- BEGIN PACKAGE TABLE -->
%b

<!-- END PACKAGE TABLE -->

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

## License

The scripts distributed in this repository are released under the [MIT License](LICENSE).
