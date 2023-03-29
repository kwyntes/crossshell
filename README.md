# Cross(s)hell
A single shell snippet that works in Bash, PowerShell and Command Prompt.

## The script

* on Windows<sup>1</sup> downloads and runs [windows_code.ps1]
* on Linux/macOS downloads and runs [linux_macos_code.sh]

##### 1. Note there exists a cross-platform PowerShell nowadays, so technically speaking you should still do an OS check in the PowerShell script.

<br>

#### With Bash syntax highlighting
```bash
echo ^">NUL \" >$null "^";&powershell.exe -c iex (iwr https://raw.githubusercontent.com/kwyntes/crossshell/main/windows_code.ps1);&echo '>NUL ' ">/dev/null;curl -s https://raw.githubusercontent.com/kwyntes/crossshell/main/linux_or_macos_code.sh|sh;echo >/dev/null \"\`" <#\"">/dev/null #>>$null
```
#### With PowerShell syntax highlighting
```powershell
echo ^">NUL \" >$null "^";&powershell.exe -c iex (iwr https://raw.githubusercontent.com/kwyntes/crossshell/main/windows_code.ps1);&echo '>NUL ' ">/dev/null;curl -s https://raw.githubusercontent.com/kwyntes/crossshell/main/linux_or_macos_code.sh|sh;echo >/dev/null \"\`" <#\"">/dev/null #>>$null
```
#### With Batch syntax highlighting
```batch
echo ^">NUL \" >$null "^";&powershell.exe -c iex (iwr https://raw.githubusercontent.com/kwyntes/crossshell/main/windows_code.ps1);&echo '>NUL ' ">/dev/null;curl -s https://raw.githubusercontent.com/kwyntes/crossshell/main/linux_or_macos_code.sh|sh;echo >/dev/null \"\`" <#\"">/dev/null #>>$null
```

Note that the syntax highlighter doesn't actually understand what's going on either.
