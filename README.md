# linux-surface for Arch Linux latest stable kernel

- Currently based on Arch Linux linux kernel 4.20.x

- Intended for **Surface Book 1 (especially, with Performance Base)** and **Surface 3**, but all patches (or equivalent) from [jakeday repository](https://github.com/jakeday/linux-surface) are applied

- PKGBUILD is from [core/linux](https://git.archlinux.org/svntogit/packages.git/?h=packages/linux)
	- `linux.preset` is modified not to create fallback initramfs. If you need it, rename `linux.preset.orig` to `linux.preset`

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



## Changelog

2019-02-18 4.20.10-arch1-2-surface
- [updating 4.19 patches · jakeday/linux-surface@2f1570d](https://github.com/jakeday/linux-surface/commit/2f1570d509eb7de8330ad4bc01b725c501ab9a8c)

2019-02-16 4.20.10-arch1-1-surface
- Arch Linux linux: [4.20.10.arch1-1](https://git.archlinux.org/svntogit/packages.git/commit/trunk?h=packages/linux&id=a0ed2c4c7b62fdad505cd9fa2fa18c922fce1662)
-  jakeday patchset: [updating 4.19 patches · jakeday/linux-surface@5b7dd5a](https://github.com/jakeday/linux-surface/commit/5b7dd5a7a9967c34f04c7108f5c7fbe326e261e2)