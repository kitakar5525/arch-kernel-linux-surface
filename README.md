# linux-surface for Arch Linux latest stable kernel

- Currently based on Arch Linux linux kernel 5.3.y

- Intended for **Surface Book 1 (especially, with Performance Base)** and **Surface 3**, but all patches (or equivalent) from [jakeday repository](https://github.com/jakeday/linux-surface) are applied
- PKGBUILD is from [trunk/linux](https://git.archlinux.org/svntogit/packages.git/log/trunk?h=packages/linux)
- I will apply my modifications on top of Arch Linux official commit.
- Patch files will be retrieved from my patches repository: [kitakar5525/linux-surface-patches](https://github.com/kitakar5525/linux-surface-patches)

See also:
- [kitakar5525/note-linux-on-surface-book-1: Notes to use Linux on Surface Book 1 with Performance Base](https://github.com/kitakar5525/note-linux-on-surface-book-1)
- [kitakar5525/note-linux-on-surface-3: Notes to use Linux on Surface 3](https://github.com/kitakar5525/note-linux-on-surface-3)



## How to build

```bash
git clone --depth 1 https://github.com/kitakar5525/arch-kernel-linux-surface
cd arch-kernel-linux-surface
makepkg -sC
```


---

## About branches

I decided that the "master" branch will now be synced with Arch Linux linux package PKGBUILD root/trunk
(https://git.archlinux.org/svntogit/packages.git/log/trunk?h=packages/linux)

See linux-surface branch for PKGBUILD with linux-surface patches.
