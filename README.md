# hackintosh-catalina-z77-ds3h

#####spec:
3.5 GHz Quad-Core Intel Core i7
16 GB 1333 MHz DDR3
NVIDIA GeForce GTX 1060 6GB 6 GB

#####upgraded from macOS Sierra
- use Clover Configurator to mount EFI partition
- place kext into EFI partition \EFI\CLOVER\kexts\Other
- modify \EFI\CLOVER\config.plist


#####AppleALC.kext for audio support
- get latest AppleALC.kext and add to \EFI\CLOVER\kexts\Other
- get macOS installation package from app store
- "Install macOS Catalina" -> right click -> "Show package contents"
- mount /Contents/SharedSupport/BaseSystem.dmg
- copy /Library/Extensions/AppleHDA.kext to \EFI\CLOVER\kexts\Other (native HDA)

- "AppleHDA.kext" -> right click -> "Show package contents"
- check the integer value of `<key>LayoutID</key>` in /Contents/Info.plist
- Modify layout id in config.plist as same value (\EFI\CLOVER\config.plist `<key>Devices</key>` `<key>Audio</key>` `<key>Inject</key>` `<integer>[XXX]</integer>`)

#####nvidia graphics support
- disable NVidia graphics injection in config.plist, keep web driver enabled
- get latest CUDA and nvidia web driver
