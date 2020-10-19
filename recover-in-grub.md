```
# Find the / and /boot partitions,
# the latter being the EFI partition in your case.
ls                # List available partitions.
ls (hdX,gptY)[/]  # List a partition's information [files].

# Let (hdA,gptB) be the /boot partition and /dev/sdxY the / partition.
set root=(hdA,gptB)
linux /vmlinuz-linux root=/dev/sdxY rw
initrd [/intel-ucode.img] /initramfs-linux.img
```
