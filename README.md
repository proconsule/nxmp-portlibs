# nxmp-portlibs

This portlibs is a WIP for creating all libs needed by NXMP
Hope this helps

# Compile in Windows

Clone without CRLF
```
git config --global core.autocrlf false
```
Using **"C:\devkitPro\msys2\msys2.exe"**
```
pacman -S patch
pacman -S binutils
pacman -S dkp-toolchain-vars
```
then in the package folder
```
makepkg
```
