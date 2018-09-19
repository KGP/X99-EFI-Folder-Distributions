# X99-EFI-Folder-Distributions

1.) EFI-Folder distributions valid for ASUS X99-A II with patched BIOS Firware for MSR register kernel write. 

For mainbaords with locked MSR register, check KernelPM and enable _xcpm_core_scope_msrs © Pike R. Alpha Kernel patch in config.plist - Section "Kernel and Kext Patches" of Clover Configurator 

2.) EFI-Folder distributions valid for Broadwell/Broadwell-E

For use with Haswell/Haswell-E CPUs, change FakeCPUID from 0x040674 to 0x0306F2 in config.plist - Section "Kernel and Kext Patches" of Clover Configurator 
