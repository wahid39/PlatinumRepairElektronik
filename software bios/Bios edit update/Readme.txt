LeakyMosfet BiosExtractor

Tool for extracting BIOS stock firmware from vendor website. The tool is also capable
of cleaning ME/TXE region, split combined firmware from bin file, extract firmware 
from BIOS update EXE file, remove EFI locks, etc.

## Type of License
 - PC Edition - includes standard functionalities and tools.
 - USB Edition - includes features in PC Edition, plus Disable RAM, NVRAM Tools, password/unlocks and DMI tools for corporate laptops.

Version History
================================
v2.1.21
 - Fixed throwing exception when dell firmware does not contain ec region
 - Updated file data and libraries for analyzing ME/TXE/CSME (also download and install the data files update at discord channel - #bioscreator-release)
 - DMI for HP Business Laptops is now disabled for PC Edition, get the USB Edition instead.
 - Fixed issue when extracting multiple firmware in Winflash
 - Improved detection of HP AMI System BIOS when extracting firmware from Winflash
 - Added NVRAM Reset for AMI UEFI
 - Fixed NVRAM Reset for Dell 5490 fails (#256)
 - Created stock bios is not right for Asus GU603HE ()#257)
 - Fixed issue with AMI BIOSGuard where extracted BIOS Region is longer than the correct size.
 - Implemented FFS v3 to simplify extraction of capsule file
 - Added password unlock for HP EliteDesk 800 G2
 - Could not find a part of the path ...\BiosCreator\FileMon\tmpAF0F error (#260)
 - Added support for bios version info for HP business laptops and PC up to G9 (e.g., elitebooks, elitedesks, probooks, prodesks)
 - Added autodetection for System BIOS and EC Firmware in UI when removing locks/password for HP business laptops and PCs
 - Fixed issue removing lock for HP 840 G7 where patched file results to "NO POWER" Issue
 - Updated referenced DLL to latest release
 - Fixed issue with changing serial numbers in Chromebook utility
 - Added future support in Chromebook utility where machine unique info from one dump is now possible to be copied to another dump.
 - Added parser for NVRAM entries
 - Refactored AMI Aptio capsule file extractor for asus
 - fix validation tests for ffs parsers
 - Removed leading space when copy-pasting DMI from system bios to ec firmware and vice versa for HP business laptops.
 - Set software updates to become optional.
v2.1.20 
 - Fixed issue where BiosCreator would refuse to run when license is already expired (#245)
 - Improved detection and extraction of lenovo bios update utility for AMD CPUs (#230)
 - Refactored and fixed issues with old format of Dell Bios update utility (#233)
 - Fixed detection of Bios region when extracting HP Elitebook stock firmware
 - Fixed removal of SWAT lock in HP Elitebook 840 G8
 - Fixed throwing error when the firmware does not have a device secret in Chromebook (#238)
 - Added unlock for Dell Latitude 5500 series - 5500/5501/5520/5540/5550/5560 (#239, #234)
 - Added detection/extraction of ITE IT8227E & IT8587E/FX in EC Firmware Tool
 - Added support for extracting KB9542 from System BIOS
 - Redesign of EC Firmware Extraction tool
 - Extract EC Firmware from laptop with AMD CPU
 - Fixed issue where EC firmware is not being extracted from EXE for (#243)
 - Fixed unable to correctly parse system bios in Asus gx531gs (#232). Now, all laptops that utilize 
   capsule file with bios region only or full system bios firmware can be detected and extracted correctly.
 - Fixed issue with Toshiba COM file not being extracted
 - Fixed issue with absolute persistence in HP 840 G8 (#237, #236) 
 - Improved UI fo password/swat/absolute persistence removal in HP Elitebooks (#237)
 - Fixed issues when extracting firmware for Dell Alienware Area-51m and m15/m17 r3
 - Added support for Asrock, panasonic

v2.1.19 (5/27/2023)
 - Improved detection and extraction of Asus capsule file header (#221)
 - Added support for Chromebooks 11th gen (#224)
 - Improved UI for extracting BIOS region from old Lenovo BIOS update file(e.g, Lenovo G580, G480)
 - Improved extraction of BIOS region for old Lenovo BIOS update file (#33)
 - Added ability to edit serial number of Chromebook
 - Firmware for HP Elitebooks w/ AMD CPUs can now be extracted correctly (#219, #197)
 - NVRAM does not open due to multiple exports registration (#218)
 - Fixed issue in extracting Toshiba firmware - C55T (#173)
 - Fixed incorrect detection of ME and System BIOS in Dell Inspiron 7447 Bios Update utility (#217)
 - Fixed AMI BIOS extraction for Dell (#185)
 - Resolved issues when copying DMI info for HP laptops w/ AMD CPUs, e.g., HP 14s-fq0017na (#139)
v2.1.18 (04/08/2023)
 - fixed #184 - Unable to extract alienware m15/m17
 - fixed #195 - Issue with EC Region tool error not correctly replacing the dump's EC region section for Dell UEFI Firmware
 - fixed #193 - Exception is thrown in Lenovo Flex 2-14 CAP file
 - fixed #199 - Extraction of FIrmware for Gigabyte Desktop Motherboard
 - fixed #200 - DMI Info for some HP (e.g., HP 13-AO10DX)
 - fixed #206 - Unable to extract Dell 5420. This fix resolves errors that occur when file(s) to be processed have 
     filename length exceeds 255 characters.
 - fixed #207 - Support for unlocking Dell 7420, 5430, 5420, 3420 and 11th gen CPU.
 - fixed #209 - Unable to extract bios region for HP 840 G5
 - fixed #210 - Unable to extract DMI Info for HP 840 G5
 - fixed #211 - Unable to extract firmware from CAP file in Lenovo L500w Gen3 L500W  (system hangup)
 - fixed #212 - Unable to extract from CAP file for Lenovo 5-15IKB
 - fixed #213 - Wrong extracted firmware size for HP w/ AMI BIOS when multiple bin file is found
 - fixed #214 - Unable to extract Lenovo 3-15iil05
 - fixed #215 - Unable to properly extract firmware from Lenovo v130-15ikb
 - fixed bugs in HP DMI for Elitebooks where UUID is not parsed correctly.
 - fixed end of stream exception when parsing evsa
 - added functions for cleaning AMI NVRAM for laptops/desktops with AMD CPUs (coming in v2.1.19)
 - added functions for updating ME/TXE region files online, delayed a bit, due to design considerations (coming in v2.19)

v2.1.17 (12/28/2022)
 - fixed #181 - issue with NVRAM Restore functionality where resulting firmware = nvram size
 - fixed #186 - Correctly parse VSS Entry
 - fixed #183 - added a way to copy or edit dmi information from EC to System Bios and vice versa. 
     Copy/paste of system information to/from clipboard is also supported. 
 - fixed #179 - Clear NVRAM for Acer E5-411(ZQM) error
 - fixed #188 - Update license status to Subscription to avoid confusion.
 - fixed #182 - Add a new function to combine firmware stored in 2 spi chips
 - added a function to split the full uefi firmware for writing into two separate spi chips.
 - fixed #191 - RegionExtraction and Bios Region repair now provides an error message when a UEFI is 
     truncated and may need to be merged with the missing part.
 - fixed #180 - Capsule file not supported for Lenovo Thinkpad
 - fixed #167 - Ability to create stock firmware for Dell 3153 3158 7353 7359 7568
 - fixed #161 - Extraction if APTIO firmware where the content is only a Bios Region but appears a full-sized firmware (Asus x409JP)
 - fixed #137 - Stock Firmware for Lenovo Thinkpad 490, 490s Crashes
 - fixed #111 - Detect when EC Firmware is inside the System Bios
 - fixed #189 - Unable to extract firmware from Lenovo Thinkpad E570
 - fixed #168 - Acer Swift SF314-43 extracted stock firmware as BiosRegion
 - fixed #192 - Lenovo 330-14igm throws an exception when extracting an FD file due to invalid character in filename
 - fixed #190 - USB Edition functionalities are missing. 

v2.1.16 (11-28-2022)
 - fixed #175 - Unable to remove standard cap header for asus 0X800 X509UA
 - fixed #176 - Unable to extract and replace corrupted FD Region
 - fixed #177 - Unable to extract regions for Acer Spin 3
 - fixed #171 - Implement PFAT Extraction, refactored AMI PFAT and replaced with own implementation

v2.1.15 (11-06-2022)
 - added #160 - added support for backup/restore of GbE region
 - added support for replacing EC region in Dell UEFI Firmware
 - added #60 - Inject/Repair EC firmware for Dell System Bios
 - fixed #165 - Apple firmware throws an exception - could not find a part of a path
 - added tab icons

2.1.14 (11-04-2022)
 - fixed #159 - issue with some users where BiosCreator throws an exception during startup
 - closes #128 - copy ME region from other dump.
 - closes #87 - remove SWAT for HP 840 G7
 - improved extraction of EC firmware for AMI-based firmware
 - closes #163 - Unable to extract bios region from firmware for Acer Aspire C24-1650
 - added support for Intel UEFI Firmware (implemented from scratch)
 - improved the stability of UEFI Region extraction, now GbE, EC and PDR Regions are supported.
 - This version will no longer force new update during start up. Update button is available in Settings Tab.

2.1.13 (10-24-2022)
 - fixed issue with HP 840 G8 w/ partial unlock
 - fixed issue with MS Surface Pro View not responding to any operation.
 - added license status info when current update is not valid for current license.
 - fixed issue #135 - Unble to extract HP Probook 360 11
 - fixed issue #146 - False detection of E1-451G System Bios as Bios Region
 - closed #132 - Online download of UEFI Firmware at MS (see v2.1.11 release notes)
 - fixed annoying error message when temporary files are unable to delete
 - adjust error messages to be visible in debug level only when connection is offline.
 - fixed issue #152 - Incorrect name for extracted Asus UX433FN Firmware  
 - fixed #158 - Failed to extract hp firmware w/ padding - hp 15-dk1000 series
 - fixed #142 - Disable On-Board RAM for all brand
 - fixed #153 - added whitelisting of HP 580 G8
 - closed #156 - Unlock for Dell w/ Service Tag Prefix 8FC8
 - added custom unlock for Dell Inspiron 5410, 3080, 790
 - fixed #157 - clean, backup, restore nvram data
 - added support for extracting bios region for HP Elitebook G8 laptops

2.1.12 (09-10-2022)
 - fixed issue #143 with setup script causing "file not found" error during startup.
 - fixed issue #144 - Dell button does not open in stock firmware tab

2.1.11 (09-08-2022)
 - resolved issue where trial version would auto update.
 - added structure for parsing FFSv2
 - added parsing VSS2 and VSS
 - fixed bugs in Lenovo Thinkpad Supervisor Password unlock for 4rth-8th Gen CPU.
 - added test cases for hp and lenovo supervisor password unlocks
 - added password unlock and patch for MS Surface Book 1 & 2 and Surface Pro 3, 4, 5, 6 & 7
 - added a tool to extract FD, ME and BIOS region from Intel UEFI firmware.
 - added a tool for clearing VSS in NVRAM volume
 - added a tool for downloading bios update from MS Update Catalog Server
 - fixed Chromebook bugs failing unit test

2.1.10 (08-25-2022)
 - master password generator is now enabled.
 - fixed systm crashes with removing password for 840/820/450 G3
 - added support for removing password for 840/820/450 G2
 - added support for 840/820/450 G1
 - added/improved support for 840/820/450 G6
 - added downloads tab for searching/downloading bios updates for common laptops/destops
 - added package download tool for mac firmware
 - added copying of Serial Number (DMI) from backup to apple stock firmware

2.1.9 (08-20-2022)
 - activate loglevel for debugging purposes
 - fixed issue #130 - Unable to extract HP Elitebook 2170P
 - fixed issue #131 - After activation, app crashes for no reason
 - updated dependency libraries

2.1.8 (08-17-2022)
 - refactor update service to prevent false positive detection - malware/ransomware

2.1.7 (07-16-2022)
 - improved extracting firmware from Sony VAIO
 - improved stability
 - fixed double file extraction for HP
 - improved accuracy in determining region files for cleaning
 - extraction of Dell Inspiron 15** (e.g. Dell Inspiron 1545, 1546) is now supported
 - removed activation/deactivation link in Settings that causes issues with new users
 - fixed issue #119 - unable to resize ec firmware extracted from dell where size > 128kb
 - fixed issue #11 - x407m downloaded bios update does not decompress when dragged
 - fixed issue #17 - Crashes when dragging Dell ROM file extracted via /writeromfile with 12mb
 - fixed issue #19 - extract zip downloaded from asus
 - fixed issue #98 - Unable to extract Dell 1555
 - fixed issue #44 - Newer Asus firmware is packaged as exe installer
 - fixed issue #88 - Add Bios Info for HP consumer laptops
 - fixed issue #90 - Add Bios Info to Lenovo consumer laptops
 - fixed issue #118 - unable to extract dell version 2 format
 - fixed issue #121 - Unable to extract Dell 3520 5280 5480 5488 5580 where multiple firmware set is present
 - fixed issue #116 - Error running BiosCreator caused by missing library
 - fixed issue #95 - Unable to extract multiple InsydeH20 firmware 
 - fixed issue #77 - extract FD region
 - fixed issue #91 - Unable to get Bios Info for Acer v5-132 wistron
 - fixed issue #75 - Add support for unlocking/unenrollment chromebook
 - fixed issue #102 - Unable to extract HP x360 F/W
 - fixed issue #30 - Compiled version throws an error in log file when extracting Acer Zip Bios file
 - fixed issue #37 - Add autodetection of BID in HP when extracting firmware
 - closed issue #91 - Unable to get Bios Info for Acer v5-132 wistron
 - fixed issue #93 - Unable to extract Asus GX703HS
 - fixed issue #95 - Unable to extract multiple InsydeH20 firmware
 - fixed issue #29 - Acer E1-470 - Unable to split CAP file

2.1.6
 - fix update URl
 - fix bugs introduced when extracting zip files

2.1.5
 - added online activation
 - fixed error with resizing EC firmware when the resize radio button is not selected
 - added support for two version of licensing - PC-Locked, Dongle
 - fixed activation window
 - fixed bugs in dell self-extracting insydeflash format
 - improved handling of dialog window, now, main window can be dragged and make the log window visible.
 - fixed issue with tools not running in 32-bit mode (for 32-bit OS)
 - enable manual update button in Settings -> Update
 - fixed hiding/showing of log windows

2.1.4 (05-19-2022)
 - added support for Bios Info in Acer, supporting most models
 - added support for Bios Info for Asus, supporting most models
 - addes support for Bios Info for HP Spectre and Pavilion
 - fixed issue with acer bios info not recognizing wistron firmware
 - added support for stock firmware extraction for LG
 - added support for Lenovo direct download of stock firmware if backup firmware version is known.
 - added BiosInfo support for Lenovo
 - added BiosInfo support for Toshiba
 - added support for chromebook unlock(tested to work in acer chromebook)
 - fixed issue #99 - Unable to extract Acer 4745G F/W
 - fix with license information logs not properly aligned
 - added support for auto update (need to convert licensing from license file to license registry key)
 - added supervisor unlock for HP Elitebook 840 G7, G8
2.1.3
 - improved me/txe cleaning function
 - code cleanup, performance enhancement
 - fixed issue #74 - Unable to extract Ideapad 3-15ARE05 
 - fixed issue #73 - Unable to extract Dell Inspiron 22-3277
 - fixed issue #72 - Firmware upgrade does not work
 - fixed issue #69 - error extracting Acer 3935
 - fixed issue #68 - Unable to extract stock firmware for HP 14-DQ1037WM
 - remove support for hardware-locked PC in v2.1.4
  
2.1.0
 - improved UI, now uses tab control to seggregate similar utilities
 - implemented downloading of samsung firmware
 - copying of DMI information from HP backup firmware to stock firmware
 - improved/added link to forum and online guide
 - fixed extraction of acer zip file where exe files are included in the output dir
 - implemented FD region repair tool. It's now possible to fix corrupted FD region, backup firmware is needed to make this work.
 - refactored Windows license key tool, added validation
 - added tooltips for all buttons
 - fixed issue when drag-drop is not working. Now, simply "double-click" or "right-click-> open" the drag-drop control to manually open file.
 - HEX view is now available to see the content of the file, "right-click -> view"
 - Toshiba stock firmware extraction is now available
 - Added support for for fixing System Bios with incorrect size (e.g., 8193kB to be corrected to 8192kB)
 - MSI firmware extraction tool is implemented.
 - master password generation tool is now fully implemented.
 - improved bios region from cap file, now supports lenovo, dell and acer (for both laptops and desktop PCs)
 - added ECS firmware extraction tool for desktop
 - added lenovo supervisor password
 - more bug fixes and stability  improvement
 - added online update
 - fix issues with licensing, now supports online activation and deactivation
 - Improved detection of DELL BIOS update utility
 - Improved backend services to improve quality enhancement 
 - added unlock for HP Elitebook, probook and zbook
 - added support for extracting the newer Toshiba bios update in EXE format.
 - added support to extract newer asus bios update exe file

2.0.33 (10-03-2020)
 - added EMC info
 - fixed issue #35 Acer Z1401 not being extracted 
 - fixed invalid and unrecognized firmware when cleaning

2.0.32
 - can now extract firmware in HP probook where fimrware is compressed inside rom.cab
 - fixed issue #27 - Unable to extract hp firmware hp 14-ce0043tx
 - fixed issue #26 - Add a button to load the license file
 - fixed issue #24 - Add "Registered" status in startup, to indicate product is registered and supported 
 - fixed issue #25 - Unable to extract HP 840 G1 Firmware
 - fixed issue #22 - Add a reset config
 - fixed issue #28 - Added logo branding
 - fixed isue #9 - Support newer HP firmware to autorun when detected
 - added the capability to extract EC from system bios for ITE SIO
 - fixed issue with ME Cleaning error

2.0.31 
 - removed dialog in ME region cleaning
 - fixed issue with ME region cleaning where file is saved in temp folder
 - fixed naming issue in ME/TXE custom cleaning in Dell.
 - fixed hp where binfile inside rompaq can't be extracted
 - added option to use more advanced ME/TXE detection/identification
 - added support for resizing EC firmware up to 1024KB
 - added new feature to change windows license key
 - re-implemented the ME/TXT region cleaning engine with more stable ones
 - ME Cleaning is now more accurate, because it can exactly match the correct ME region to use
 - fixes LogLevel.Debug color not properly seen in log file
 - BiosCreator can now be installed anywhere ;)

2.0.14
 - fixed a bug that broke the hp decryption functionality
 - fixed issue with HP BID# being displayed even if the file is encrypted.
 - fixed splitting of EC and BIOS throwing an exception when a file is not loaded.
 - added bios cleaning with custom ME region
 - fixed bug where cleaning of ME region fails to save

2.0.13
 - created stub for icloud removal in macbook
 - added feature to dell bios extractor where packaging utilizes InsydeFlash
 - refactored Dell bios extractor, removed 'others' option
 - fixed bug in Lenovo where innosetup is not extracted
 - fixed bugs in lenovo extraction where bin file is InsydeFlash
 - fixed a bug in Lenovo extraction where CAP file embeds EC firmware inside System BIOS
 - fixed a bug in Lenovo extraction where packaged EXE is in InsydeFlash format
 - fixed file monitor service which simplifies getting bin file out of temp folder 
 - InsydeFlashService now extracts file more accurately.  Size is now obtained from the header
 - fixed issue with InysdeFlashService when EC firmware is not found
 - added support for extracing Sony VAIO Package Manager
 - added support for removing 2kb Asus CAP header 
 - fixed issue with IOC not instantiating new object
 - added extraction of BID# and version information for HP FIRMWARE
 - added capability to replace corrupted BIOS REGION w/ validation (useful for creating Asus stock firmware)
 - Refactor AppleService
 - fixes bug in HPService where file is not decrypted properly
 - fixed a bug in LenovoService being unable to extract a package (e.g. lenovo 330-14ikb)
 - added feature to replace bios region for creating asus and dell stock firmware (not fully tested) or fixing corrupted bios region. 
 - fixed licensing implementation

2.0.12
 - improved UI in ME/TXE Repair
 - bug fixes and refactoring
 - added the ability to display macbook serial number
 - added feature to change macbook serial number
 - fixed dell not showing filename when dragged to extractor
 - EFI password for Macbooks prior to 2011 can now be decoded.

2.0.11
 - Support for Dell extraction w/ ME + BIOS Region

2.0.10
 - Now supports ME/TXE Region cleaning

Requirements:
================================
1. Windows 7+
2. .NET Framework 4.8
3. Visual C++ Runtime Library 2015 (for Windows 7)
4. WebView2 Runtime Library

Installation Instructions:
================================

1. Run BiosCreator_Setup.exe
2. Follow the setup wizard

Known Issues:
 - CSE TXE 3/4 is not supported at this time
 - newer bios update file from toshiba and samsung, not yet supported

Supported Models
================================
 - All laptop/desktop models are supported except the following:
   - Laptops w/ CSE TXE 3.0/4.0 Firmware

Credits
================================
MEAnalyzer Plato Mavropoulos
Contains zlib code, Copyright © 1995-2005 Jean-loup Gailly and Mark Adler.
Contains bzip2 code, Copyright © 1996-2009 Julian R Seward. All rights reserved.
Contains LZMA code, Copyright © 1999-2009 Igor Pavlov.