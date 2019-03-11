# linux-surface for Arch Linux latest stable kernel

- Currently based on Arch Linux linux kernel 5.0.y

- Intended for **Surface Book 1 (especially, with Performance Base)** and **Surface 3**, but all patches (or equivalent) from [jakeday repository](https://github.com/jakeday/linux-surface) are applied

- PKGBUILD is from [core/linux](https://git.archlinux.org/svntogit/packages.git/?h=packages/linux)
	- `linux.preset` is modified not to create fallback initramfs. If you need it, rename `linux.preset.orig` to `linux.preset`

- Patch files will be retrieved from my patches repository: [kitakar5525/linux-surface-patches](https://github.com/kitakar5525/linux-surface-patches)

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



## Status

Arch Linux linux version
- 5.0.1.arch1-1: [svntogit/packages.git - Git clone of the 'packages' repository](https://git.archlinux.org/svntogit/packages.git/commit/trunk?h=packages/linux&id=cda26f1f58041fd565373e78a32642b29da26fb8)

kitakar5525/linux-surface-patches version
- [kitakar5525/linux-surface-patches at v1.0](https://github.com/kitakar5525/linux-surface-patches/tree/v1.0)