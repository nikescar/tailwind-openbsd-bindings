# Tailwind CSS v4 OpenBSD Native Bindings

Pre-built native bindings for Tailwind CSS v4 on OpenBSD x64.

## Quick Download

```bash
curl -OL https://github.com/nikescar/tailwind-openbsd-bindings/releases/latest/download/lightningcss.openbsd-x64.node
curl -OL https://github.com/nikescar/tailwind-openbsd-bindings/releases/latest/download/tailwindcss-oxide.openbsd-x64.node
```

## What's Included

- **lightningcss.openbsd-x64.node** (11MB) - CSS parser and transformer
- **tailwindcss-oxide.openbsd-x64.node** (3.4MB) - Rust-based CSS compiler

## Compatibility

- Tailwind CSS v4.3.3
- lightningcss v1.32.0 - v1.33.0
- @tailwindcss/oxide v4.3.3
- OpenBSD 8.0+
- Node.js v18+

## Usage

These bindings work with the automated patch scripts:

**Installation with patches:**
```bash
# 1. Download bindings
curl -OL https://github.com/nikescar/tailwind-openbsd-bindings/releases/latest/download/lightningcss.openbsd-x64.node
curl -OL https://github.com/nikescar/tailwind-openbsd-bindings/releases/latest/download/tailwindcss-oxide.openbsd-x64.node

# 2. Download and run patch installer
mkdir -p scripts && cd scripts
curl -O https://gist.githubusercontent.com/nikescar/8dce8c05b2cfeb977a97630146fa09ff/raw/install-tailwind-openbsd.sh
chmod +x install-tailwind-openbsd.sh
cd .. && bash scripts/install-tailwind-openbsd.sh
```

**Complete patch scripts:** https://gist.github.com/nikescar/8dce8c05b2cfeb977a97630146fa09ff

## Building from Source

If you prefer to build the bindings yourself:

### lightningcss

```bash
cd /tmp
git clone --depth=1 --branch v1.33.0 https://github.com/parcel-bundler/lightningcss.git
cd lightningcss
npm install --ignore-scripts
npx napi build --release --platform --cargo-cwd node
cp lightningcss.openbsd-x64.node /path/to/your/project/
```

### @tailwindcss/oxide

```bash
cd /tmp
git clone --depth=1 --branch v4.3.3 https://github.com/tailwindlabs/tailwindcss.git
cd tailwindcss
cargo build --release -p tailwind-oxide
cp target/release/libtailwind_oxide.so /path/to/your/project/tailwindcss-oxide.openbsd-x64.node
```

## Releases

Each release is tagged with the Tailwind CSS version number (e.g., `v4.3.3`).

Download bindings from [Releases](https://github.com/nikescar/tailwind-openbsd-bindings/releases).

## License

These are compiled binaries from:
- [lightningcss](https://github.com/parcel-bundler/lightningcss) - MPL-2.0
- [tailwindcss](https://github.com/tailwindlabs/tailwindcss) - MIT

## Support

For issues or questions:
- Patch scripts: https://gist.github.com/nikescar/8dce8c05b2cfeb977a97630146fa09ff
- This repo: https://github.com/nikescar/tailwind-openbsd-bindings/issues
