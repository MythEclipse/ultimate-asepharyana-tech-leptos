# Leptos Web App

Frontend WASM berbasis Leptos (CSR) dengan build pipeline Trunk + Tailwind.

## Prerequisites

- Rust toolchain `nightly`
- target `wasm32-unknown-unknown`
- `trunk`
- Bun (untuk dependency CSS/Tailwind)

```bash
rustup toolchain install nightly --allow-downgrade
rustup target add wasm32-unknown-unknown
cargo install trunk
```

## Install

```bash
bun install
```

## Development

```bash
trunk serve
```

Default local URL: `http://localhost:3000`

Catatan:

- Trunk menjalankan hook pre-build untuk compile Tailwind:
    `./node_modules/.bin/tailwindcss -i style/main.css -o style/output.css`
- Request `/api/*` diproxy ke `https://rust.asepharyana.tech/api/` sesuai `Trunk.toml`.

## Build

```bash
trunk build --release
```

Output static ada di folder `dist`.

## Manual CSS Build (optional)

```bash
bun run build
```
