# MediaTek Genio · Zephyr

Zephyr RTOS for MediaTek Genio platforms. On the Genio 510 and Genio 700 EVKs,
Zephyr runs next to Linux on dedicated CPU cores, partitioned by the Jailhouse
hypervisor.

## Get started

<a href="https://github.com/mtk-zephyr/genio-docs/releases/latest/download/genio-jailhouse-zephyr-guide.pdf"><img src="https://raw.githubusercontent.com/mtk-zephyr/genio-docs/v1.0/assets/guide-preview.png" alt="Pages of the user guide: the cover, the system overview, and running a Zephyr image" width="100%"></a>

**[User guide (PDF)](https://github.com/mtk-zephyr/genio-docs/releases/latest/download/genio-jailhouse-zephyr-guide.pdf):
Running Zephyr alongside Linux with Jailhouse on Genio 510 and Genio 700 EVKs.**
Build the IoT Yocto image with Jailhouse, flash the board, build Zephyr and the
Genio samples, and run Zephyr in a Jailhouse cell, step by step.

**Pre-release:** `v26.1-rc1` of mtk-zephyr (branch `mtk-v4.4.2`, based on
Zephyr 4.4.2) and of the samples, paired with
[MediaTek Jailhouse](https://github.com/mtk-jailhouse/jailhouse) `v26.1-rc1`
and described by
[user guide 26.1-rc1](https://github.com/mtk-zephyr/genio-docs/releases/tag/v26.1-rc1),
whose PDF was revised on 2026-10-28 for the Zephyr tags.

A complete Zephyr workspace at that pre-release, with the Genio tree, its
modules and the samples (the guide's Chapter 5 sets up the toolchain):

```bash
west init -m https://github.com/mtk-zephyr/samples --mr v26.1-rc1 genio-workspace
cd genio-workspace
west update
```

**Last release:** `mtk-genio-v1.0.0` of mtk-zephyr and the samples, paired with
MediaTek Jailhouse `mtk-v1.0.0` and described by
[user guide 1.0](https://github.com/mtk-zephyr/genio-docs/releases/tag/v1.0).
For a workspace at that release, use `--mr mtk-genio-v1.0.0`.

A tag pins the Genio tree, so `west update` gives the same tree every time.

In the history of mtk-zephyr, the subjects of the Genio commits start with
`GENIO:`, and those of fixes backported from later upstream Zephyr releases
with `BACKPORT:`.

## Repositories

| Repository | Content |
|---|---|
| [mtk-zephyr](https://github.com/mtk-zephyr/mtk-zephyr) | The Genio Zephyr tree: board support and drivers. Releases are tags: the pre-release `v26.1-rc1` on the branch `mtk-v4.4.2` (Zephyr 4.4.2), and the release `mtk-genio-v1.0.0`. Development continues on `mtk-genio-dev`, on a Zephyr 4.5.0-rc1 snapshot |
| [samples](https://github.com/mtk-zephyr/samples) | The Genio samples, and the west manifest of a complete workspace; its tags pin the tree |
| [genio-docs](https://github.com/mtk-zephyr/genio-docs) | Documentation, including the user guide |

## Supported boards

| Board | SoC | Zephyr board target |
|---|---|---|
| Genio 510 EVK | MT8370 | `mt8370_genio_510_evk/mt8188/a55` |
| Genio 700 EVK | MT8390 | `mt8390_genio_700_evk/mt8188/a55` |

Both have a two-core variant, `<board target>/smp`.

## Related

- [MediaTek Jailhouse](https://github.com/mtk-jailhouse/jailhouse): the hypervisor, with the Genio cell configurations
- [IoT Yocto](https://genio.mediatek.com/doc/iot-yocto/latest/sw/yocto/get-started.html): the Linux BSP for Genio
