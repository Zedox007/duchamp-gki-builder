# duchamp-gki-builder

GKI kernel builder for Poco X6 Pro (Duchamp) with KernelSU-Next and Droidspaces support.

Built on top of [GKI-Duchamp](https://github.com/ahmed-alnassif/GKI-Duchamp) by ahmed-alnassif.
Droidspaces patches by [ravindu644](https://github.com/ravindu644/Droidspaces-OSS).

---

## What it builds

- Kernel 6.1 (android14-6.1-lts)
- KernelSU-Next
- Droidspaces support
- Baseband Guard (BBG)
- Performance tweaks

---

## Dependencies

**Arch:**
```bash
pacman -Syu --noconfirm base-devel git python bc bison flex cpio libelf pahole perl wget curl zip unzip clang lld ccache
pip install lxml --break-system-packages
```

**Debian:**
```bash
apt-get update && apt-get install -y git bc bison flex libssl-dev libelf-dev dwarves cpio build-essential clang lld ccache python3-pip
pip3 install lxml --break-system-packages
```

---

## Build

```bash
git clone https://github.com/Zedox007/duchamp-gki-builder
cd duchamp-gki-builder
chmod +x run_build.sh py/kmi-check-6.x.py
bash run_build.sh
```

Output zip will be in the working directory.

---

## Configuration

Edit `run_build.sh` to change build options:

| Variable | Values | Description |
|---|---|---|
| `KSU` | `KSUN` `KSU` `SKSU` `RSKSU` `no` | Root solution (default: `KSUN`) |
| `KSU_SUSFS` | `true` `false` | SUSFS (default: `false`) |
| `KSU_COMPAT` | `true` `false` | Compat variant (default: `false`) |
| `STATUS` | `BETA` `RELEASE` | Build type (default: `BETA`) |
| `KERNEL_REPO` | any GKI 6.1 repo URL | Kernel source |

---

## Credits

- [ahmed-alnassif](https://github.com/ahmed-alnassif) — base builder
- [ravindu644](https://github.com/ravindu644) — Droidspaces patches
- [KernelSU-Next](https://github.com/KernelSU-Next/KernelSU-Next)
- [Baseband Guard](https://github.com/vc-teahouse/Baseband-guard)
