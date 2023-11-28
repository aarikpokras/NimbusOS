# NimbusOS

An Arch-based Linux distribution.

## Compilation
To compile Nimbus, you need `archiso` tools. I'm pretty sure it's only available on pacman, but you can try it with apt:
```console
# apt install archiso
```
```console
# pacman -Syu archiso
```
To compile Nimbus, use `mkarchiso`:
```console
# mkarchiso -v -w ./working-directory/ -o ./output-directory/ ./nimbusos/
```
Where `nimbusos` is this downloaded repository's folder (See `mkarchiso -h`)

**Warning:** _It's going to take a long time to compile. Please be patient. Don't throw your computer out the window like I did._

## Usage
### Flashing
Flash the iso file in the output directory to a drive:
```console
# dd if=/path/to/iso of=/dev/sdX bs=4M status=progress
```
Replace `/path/to/iso` with the path to the iso file and `/dev/sdX` with your device file.
### Testing in QEMU
First, we should get `qemu-desktop` and `edk2-ovmf`:
```console
# pacman -Syu qemu-desktop edk2-ovmf
```
Using tools included with `archiso`, we can get a VM running:
```console
$ run_archiso -i /path/to/iso.iso
```
To use UEFI emulation:
```console
$ run_archiso -u -i /path/to/iso.iso
```
