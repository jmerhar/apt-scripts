# APT Scripts Repository

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository hosts a Debian package (`.deb`) collection for my personal shell scripts, making them easily installable on Debian-based Linux distributions like Ubuntu.

The repository is signed with a GPG key to ensure the authenticity and integrity of the packages.

---

## Installation

To use this repository, you need to add its source to your system's APT configuration and trust its GPG key.

### 1. Add the GPG Key

First, add the repository's GPG key to your system's list of trusted keys. This is the modern, secure method for adding APT keys.

```bash
# Create the keyrings directory if it doesn't exist
sudo mkdir -p /etc/apt/keyrings

# Download and save the GPG public key
wget -qO- https://jmerhar.github.io/apt-scripts/public.key | sudo gpg --dearmor -o /etc/apt/keyrings/jmerhar-scripts.gpg
```

### 2. Add the Repository Source

Next, create a source list file that tells APT where to find the packages.

```bash
# Add the repository to your APT sources
echo "deb [arch=all signed-by=/etc/apt/keyrings/jmerhar-scripts.gpg] https://jmerhar.github.io/apt-scripts/ stable main" | sudo tee /etc/apt/sources.list.d/jmerhar-scripts.list
```

---

## Usage

Once the repository is configured, you can install, upgrade, and remove scripts using standard `apt-get` commands.

### 1. Update Package Lists

Before installing a package for the first time, update your local package index.

```bash
sudo apt-get update
```

### 2. Install a Script

Install any script from the repository by its package name.

```bash
# Example: Install the 'unlock-pdf' script
sudo apt-get install unlock-pdf

# Example: Install the 'install-dependency' script
sudo apt-get install install-dependency
```

---

## Contributing

This repository is automatically managed by a CI/CD workflow from the [jmerhar/scripts](https://github.com/jmerhar/scripts) source repository. Contributions and suggestions should be directed there.

## License

The scripts distributed in this repository are released under the **MIT License**. See the [LICENSE](LICENSE) file for more details.
