# Windows-x64---PIC-Null-Free-Calc.exe-Shellcode

When an unpatched Windows 11 host loads a theme file referencing an msstyles file, Windows loads the msstyles file, and if that file's PACKME_VERSION is 999, it then attempts to load an accompanying dll file ending in _vrf.dll. Before loading that file, it verifies that the file is signed. It does this by opening the file for reading and verifying the signature before opening the file for execution. Because this action is performed in two discrete operations, it opens the procedure for a time of check to time of use vulnerability. By embedding a UNC file path to an SMB server we control, the SMB server can serve a legitimate, signed dll when queried for the read, but then serve a different file of the same name when the host intends to load/execute the dll.
