# linux-surface for Arch Linux latest stable kernel

- Currently based on Arch Linux linux kernel 5.0.y

- Intended for **Surface Book 1 (especially, with Performance Base)** and **Surface 3**, but all patches (or equivalent) from [jakeday repository](https://github.com/jakeday/linux-surface) are applied

- PKGBUILD is from [core/linux](https://git.archlinux.org/svntogit/packages.git/?h=packages/linux)
	- `linux.preset` is modified not to create fallback initramfs. If you need it, rename `linux.preset.orig` to `linux.preset`

- I may change some kernel configs. See [config.diff](config.diff)

See also:
- [kitakar5525/note-linux-on-surface-book-1: Notes to use Linux on Surface Book 1 with Performance Base](https://github.com/kitakar5525/note-linux-on-surface-book-1)
- [kitakar5525/note-linux-on-surface-3: Notes to use Linux on Surface 3](https://github.com/kitakar5525/note-linux-on-surface-3)



## Issues on Linux 5.0

### ipts is not working

`dmesg` log when booting with drm.debug=0x02:
```
kern  :info  : [Thu Mar  7 18:50:57 2019] i915 0000:00:02.0: GuC firmware version 9.33
kern  :info  : [Thu Mar  7 18:50:57 2019] i915 0000:00:02.0: GuC submission enabled
kern  :info  : [Thu Mar  7 18:50:57 2019] i915 0000:00:02.0: HuC enabled
kern  :debug : [Thu Mar  7 18:50:57 2019] [drm:gen8_init_common_ring [i915]] Applied 5 rcs0 workarounds
kern  :debug : [Thu Mar  7 18:50:57 2019] [drm:gen9_init_render_ring [i915]] Applied 4 whitelist workarounds
kern  :info  : [Thu Mar  7 18:50:57 2019] ipts: initializing ipts
kern  :debug : [Thu Mar  7 18:50:57 2019] [drm:guc_client_alloc [i915]] client 2 (high prio=yes) reserved doorbell: 2
kern  :debug : [Thu Mar  7 18:50:57 2019] [drm:guc_client_alloc [i915]] reserved cacheline 0x80, next 0xc0, linesize 64
kern  :debug : [Thu Mar  7 18:50:57 2019] [drm:guc_client_alloc [i915]] new priority 1 client 00000000df811bf9 for engine(s) 0x47: stage_id 2
kern  :debug : [Thu Mar  7 18:50:57 2019] [drm:guc_client_alloc [i915]] doorbell id 2, cacheline offset 0x80
kern  :err   : [Thu Mar  7 18:50:57 2019] [drm:intel_guc_send_mmio [i915]] *ERROR* MMIO: GuC action 0x10 failed with error -5 0xf000f000
kern  :debug : [Thu Mar  7 18:50:57 2019] [drm:create_doorbell [i915]] Couldn't create client 2 doorbell: -5
kern  :err   : [Thu Mar  7 18:50:57 2019] [drm:intel_ipts_init [i915]] *ERROR* i915_guc_ipts_submission_enable failed : -5
[...]
kern  :err   : [Thu Mar  7 18:50:58 2019] ipts mei::3e8d0870-271a-4208-8eb5-9acb9402ae04:0F: open gpu error : -5
kern  :err   : [Thu Mar  7 18:50:58 2019] ipts mei::3e8d0870-271a-4208-8eb5-9acb9402ae04:0F: error in handling resp msg
```



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
- [updating 4.19 patches and config · jakeday/linux-surface@5d21cc8](https://github.com/jakeday/linux-surface/commit/5d21cc824c9b41e65f92fdebcbcccd2181b9393f)

Improve s0ix
- [[1/1] ipu3-cio2: Allow probe to succeed if there are no sensors connected - Patchwork](https://patchwork.kernel.org/patch/10714257/)
- [[v3,0/5] ICL support and other enhancements for PMC Core - Patchwork](https://patchwork.kernel.org/cover/10812541/)

Surface 3 sound fix for OEMB devices
- 5525-sound-add-dmi-match-OEMB-for-affected-surface-3.patch