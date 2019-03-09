# linux-surface for Arch Linux latest stable kernel

- Currently based on Arch Linux linux kernel 5.0.y

- Intended for **Surface Book 1 (especially, with Performance Base)** and **Surface 3**, but all patches (or equivalent) from [jakeday repository](https://github.com/jakeday/linux-surface) are applied

- PKGBUILD is from [core/linux](https://git.archlinux.org/svntogit/packages.git/?h=packages/linux)
	- `linux.preset` is modified not to create fallback initramfs. If you need it, rename `linux.preset.orig` to `linux.preset`

- I may change some kernel configs. See [config.diff](config.diff)

See also:
- [kitakar5525/note-linux-on-surface-book-1: Notes to use Linux on Surface Book 1 with Performance Base](https://github.com/kitakar5525/note-linux-on-surface-book-1)
- [kitakar5525/note-linux-on-surface-3: Notes to use Linux on Surface 3](https://github.com/kitakar5525/note-linux-on-surface-3)



## How to build

```bash
git clone --depth 1 https://github.com/kitakar5525/arch-kernel-linux-surface
cd arch-kernel-linux-surface
makepkg -sC
```



## patch filename prefix

- 4416
	- Indicate that the patch is not from me (Hayataka@kitakar5525)
- 552?
	- Indicate that the patch is made by me
- 4416-*552?
	- Indicate that the patch is from another person and modified by me



## Status

Arch Linux PKGBUILD
- 5.0.arch1-1: [svntogit/packages.git - Git clone of the 'packages' repository](https://git.archlinux.org/svntogit/packages.git/commit/trunk?h=packages/linux&id=88bced9118156f0e11267dbab1bfdb77cada9022)

jakeday patches
- [updating patches · jakeday/linux-surface@e09d9e1](https://github.com/jakeday/linux-surface/commit/e09d9e11f58281aec3780849cdaf9336579a4169)
- [Porting patches to Linux 5.0 (surface-acpi, ipts) · Issue #417 · jakeday/linux-surface](https://github.com/jakeday/linux-surface/issues/417)

Improve s0ix
- [[1/1] ipu3-cio2: Allow probe to succeed if there are no sensors connected - Patchwork](https://patchwork.kernel.org/patch/10714257/)
- [[v3,0/5] ICL support and other enhancements for PMC Core - Patchwork](https://patchwork.kernel.org/cover/10812541/)

Surface 3 sound fix for OEMB devices
- 5525-sound-add-dmi-match-OEMB-for-affected-surface-3.patch