My own version following the vanilla guide at OpenCore install Guide at https://dortania.github.io/OpenCore-Install-Guide/

Hardware: 
- Gigabyte Aorus Z390 I PRO WIFI
- i3 8300
- 16GB DDR4 3200 RAM
- NVME Samsung SSD960 EVO
- AMD Vega 56

Bios Setup:

Disable

Fast Boot
Secure Boot
Serial/COM Port
Parallel Port
VT-d (can be enabled if you set DisableIoMapper to YES)
CSM
Thunderbolt(For initial install, as Thunderbolt can cause issues if not setup correctly)
Intel SGX
Intel Platform Trust
CFG Lock (MSR 0xE2 write protection)(This must be off, if you can't find the option then enable AppleXcpmCfgLock under Kernel -> Quirks. Your hack will not boot with CFG-Lock enabled)

# Enable

VT-x
Above 4G decoding
Hyper-Threading
Execute Disable Bit
EHCI/XHCI Hand-off
OS type: Windows 8.1/10 UEFI Mode
DVMT Pre-Allocated(iGPU Memory): 64MB
SATA Mode: AHCI

OpenCore gained support for signed kernel verification in a recent commit. You may get reboots in early booting due to this being enabled by default in the sample plist - make sure SecureBootModel is set to Disabled in your config.plist - and not set to Default.
