# MediaTek Genio · Zephyr

Zephyr RTOS for MediaTek Genio platforms. On the Genio 510 and Genio 700 EVKs,
Zephyr runs next to Linux on dedicated CPU cores, partitioned by the Jailhouse
hypervisor.

## Get started

<a href="https://github.com/mtk-zephyr/genio-docs/releases/latest/download/genio-jailhouse-zephyr-guide.pdf"><img src="https://raw.githubusercontent.com/mtk-zephyr/genio-docs/main/assets/guide-preview.png" alt="Pages of the user guide: the cover, the system overview, and running a Zephyr image" width="100%"></a>

**[User guide (PDF)](https://github.com/mtk-zephyr/genio-docs/releases/latest/download/genio-jailhouse-zephyr-guide.pdf):
Running Zephyr alongside Linux with Jailhouse on Genio 510 and Genio 700 EVKs.**
Build the IoT Yocto image with Jailhouse, flash the board, build Zephyr and the
Genio samples, and run Zephyr in a Jailhouse cell, step by step.

A complete Zephyr workspace, with the Genio tree, its modules and the samples
(the guide's Chapter 5 sets up the toolchain):

```bash
west init -m https://github.com/mtk-zephyr/samples genio-workspace
cd genio-workspace
west update
```

## Repositories

| Repository | Content |
|---|---|
| [mtk-zephyr](https://github.com/mtk-zephyr/mtk-zephyr) | The Genio Zephyr tree: board support and drivers |
| [samples](https://github.com/mtk-zephyr/samples) | The Genio samples, and the west manifest of a complete workspace |
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
