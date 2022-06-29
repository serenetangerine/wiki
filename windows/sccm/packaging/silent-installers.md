# Silent Installers
## Silent Flags
Below are some common silent flags for various installation media. For `.exe` files, good practice is to run `.\installer.exe /?` to attempt to bring up a help page.
- .msi (these are the most standard media 
    - `/qn`
    - Powershell Examples
        - Install: `Start-Process "msiexec.exe" -Args "/i $msiFile /qn" -Wait`
        - Uninstall: `Start-Process "msiexec.exe" -Args "/x $msiProductCode /qn" -Wait`
- .exe (these vary greatly by manufacturer, but here are some common examples)
    - `--silent`
    - `/silent` or `/verysilent`
    - `/S /v/qn` or `/s /v/qn`
    - InstallShield --TODO--
        - InstallShield compiled installers support flags to record the options as you run through the installer manually, save that recording as a file, then pass the recording file in with the original `.exe` to skip through setup silently. The method for this needs to be documented.
