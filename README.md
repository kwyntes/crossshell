# Cross(s)hell
A single shell snippet that works in Bash, PowerShell and Command Prompt.

<br>

### In theory, the script

* on Windows<sup>1</sup> downloads and runs [`windows_code.ps1`](windows_code.ps1)
* on Linux/macOS<sup>2</sup> downloads and runs [`linux_macos_code.sh`](linux_macos_code.sh)

##### 1. Note there exists a cross-platform PowerShell nowadays, so technically speaking you should still do an OS check there - but realistically speaking, who uses that anyway?
##### 2. or any OS that runs a bash-like shell (yeah it could even be Windows through Git Bash or something)

<br>

## The script

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

<br>

Note that the syntax highlighter doesn't actually understand what's going on either.
