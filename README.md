# X99-EFI-Folder-Distributions

1.) EFI-Folder distributions valid for ASUS X99-A II with patched BIOS Firware for MSR register kernel write. 

For mainbaords with locked MSR register, check KernelPM and enable _xcpm_core_scope_msrs © Pike R. Alpha Kernel patch in config.plist - Section "Kernel and Kext Patches" of Clover Configurator 

2.) EFI-Folder distribution valid for Broadwell-E

For use with Haswell-E CPUs, change 

# FakeCPUID (Broadwell-E):0x040674 

to

# FakeCPUID (Haswell-E):0x0306F2

in config.plist - Section "Kernel and Kext Patches" of Clover Configurator.

Also implemnted but disabled _xcpm_cpuid_set_info  and _xcpm_bootstrap  Kernel patches are for Broadwell-E!

# _xcpm_cpuid_set_info (Broadwell-E)

Find: 723cd077 500fb6c0

Replace: 6a3cd077 500fb6c0 

# _xcpm_bootstrap (Broadwell-E)

Find: 89d804c4 3c227722

Replace:89d804c3 3c227722 


For Haswell-E change to:

# _xcpm_cpuid_set_info (Haswell-E)

Find: 723cd077 500fb6c0

Replace: 6f3cd077 500fb6c0 

# xcpm_bootstrap (Haswell-E)

Find: 89d804c4 3c227722

Replace:89d804c1 3c227722 

xcpm_bootstrap Kernel patch seems still required for some of the Haswell-E CPUs, e.g. i7-5820k. 

For most Broadwell-E CPUs, _xcpm_cpuid_set_info and _xcpm_bootstrap Kernel patches are however obsolete and can remain disabled.
