# Tiramisu Universe Package Repository

Official package repository for **Tiramisu OS** hosted on GitHub (`https://github.com/tnuproject/universe`).

This repository provides binary packages (`.pkg`), including GNU nano, GNU bash, networking tools, core utilities, development libraries, and hardware firmware, built and packaged for the Tiramisu / FreeBSD 14 amd64 architecture.

---

## Repository Structure

```
universe/
├── repo.json           # Catalog index with package metadata, dependencies, and SHA256 hashes
├── packages/           # Binary .pkg archives
│   ├── nano-9.2.pkg    # Authentic FreeBSD GNU nano binary
│   ├── bash-5.2.26.pkg # Authentic FreeBSD GNU bash binary
│   └── ...
└── README.md
```

---

## How to Upload to GitHub

To publish or update this repository on GitHub:

```bash
# Clone the repository
git clone https://github.com/tnuproject/universe.git
cd universe

# Copy the contents of this folder into the git repo
# Ensure git-lfs is installed if uploading packages >50MB
git lfs install
git lfs track "*.pkg"

git add .
git commit -m "Update Tiramisu Universe package repository"
git push origin main
```

---

## Using with Tiramisu OS `pkg`

By default, Tiramisu OS connects directly to this repository at:
`https://raw.githubusercontent.com/tnuproject/universe/main`

In the Tiramisu shell:

```bash
# Update repository index
pkg update

# Search for available packages
pkg search nano

# Install GNU nano
pkg install nano

# List installed packages
pkg list
```
