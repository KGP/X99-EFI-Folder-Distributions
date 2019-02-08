# X99-EFI-Folder-Distributions

1.) EFI-Folder distributions valid for ASUS X99-A II with patched BIOS Firware for MSR register kernel write. 

For mainbaords with locked MSR register, check KernelPM and enable _xcpm_core_scope_msrs © Pike R. Alpha Kernel patch in config.plist - Section "Kernel and Kext Patches" of Clover Configurator 

2.) EFI-Folder distribution valid for Broadwell-E

For use with Haswell-E CPUs, change 

# FakeCPUID (Broadwell-E):0x040674 

to

# FakeCPUID (Haswell-E): empty, not required, natively suported

in config.plist - Section "Kernel and Kext Patches" of Clover Configurator.

For Haswell-E also chhange _xcpm_cpuid_set_info  and _xcpm_bootstrap  Kernel patches for Broadwell-E

# _xcpm_cpuid_set_info (Broadwell-E)

Find: 723cd077 500fb6c0

Replace: 6a3cd077 500fb6c0 

# _xcpm_bootstrap (Broadwell-E)

Find: 89d804c4 3c227722

Replace:89d804c3 3c227722 

to:

# _xcpm_cpuid_set_info (Haswell-E)

Find: 723cd077 500fb6c0

Replace: 6f3cd077 500fb6c0 

# xcpm_bootstrap (Haswell-E)

Find: 89d804c4 3c227722

Replace:89d804c1 3c227722 

_xcpm_cpuid_set_info kernel patch is obsolete for Broadwell-E and Haswell-E and can remain disabled

_xcpm_bootstrap kernel patch seems still required for some Haswell-E CPUs, e.g. i7-5820k. 

_xcpm_bootstrap Kernel patch for Broadwell-E is also obsolete and can remain disabled.
