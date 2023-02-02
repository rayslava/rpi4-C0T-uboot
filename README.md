U-Boot workaround for RPi4 B rev 1.5
====================================

If you try to boot ArchLinux ARM with AArch64 kernel have boot errors like

```
mmc1: ADMA error: 0x02000000
mmc1: sdhci: =========== SDHCI REGISTER DUMP ============
mmc1: sdhci: Blk size:  ...
```

you might have purchased too new hardware. Due to a set of reasons armv7hl
build will work just fine, but AArch64 version won't boot.

This happens because new revision of Raspberry Pi 4 (a.k.a. `C0T`) requires
patching FDT accordingly to firmware, so an updated U-Boot is required.

The idea is taken from the [forum post](https://archlinuxarm.org/forum/viewtopic.php?f=67&t=15422&start=20#p69111)

And I hope this change will be taken to upstream at last

Usage
-----

Just use your `makepkg` to build a bootloader for `aarch64` and install the
package. You can just unpack the package using `tar`.

keywords: archlinux, archlinuxarm, aarch64, u-boot, uboot, adma error
