Specs:
Type|Item
:----|:----
**CPU** | AMD Ryzen 5 5600 3.5 GHz 6-Core Processor
**Motherboard** | Asus ROG STRIX B450-F GAMING II ATX AM4 Motherboard
**Memory** | Corsair Vengeance LPX 16 GB (2 x 8 GB) DDR4-3600 CL16 Memory [DOCP disabled]
**Storage** | Crucial P3 1 TB M.2-2280 PCIe 3.0 X4 NVME Solid State Drive [MacOS Drive]
**Video Card** | XFX Speedster MERC 319 CORE Radeon RX 6800 XT 16 GB Video Card
**Power Supply** | be quiet! Pure Power 12 M 750 W 80+ Gold Certified Fully Modular ATX Power Supply

Make sure to follow BIOS guide on OpenCore website


Disable:

    Fast Boot
    Secure Boot
    Serial/COM Port
    Parallel Port
    Compatibility Support Module (CSM) (Must be off in most cases, GPU errors/stalls like gIO are common when this option is enabled)
    IOMMU

#
Enable:

    Above 4G Decoding (This must be on, if you can't find the option then add npci=0x3000 to boot-args. Do not have both this option and npci enabled at the same time.)
        If you are on a Gigabyte/Aorus or an AsRock motherboard, enabling this option may break certain drivers(ie. Ethernet) and/or boot failures on other OSes, if it does happen then disable this option and opt for npci instead
        2020+ BIOS Notes: When enabling Above4G, Resizable BAR Support may become an available on some X570 and newer motherboards. Please ensure that Booter -> Quirks -> ResizeAppleGpuBars is set to 0 if this is enabled.
    EHCI/XHCI Hand-off
    OS type: Windows 8.1/10 UEFI Mode (some motherboards may require "Other OS" instead)
    SATA Mode: AHCI

#
