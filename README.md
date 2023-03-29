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

<br>


## How does it work?

**Short answer**: By abusing almost every single syntax feature of each shell.

<br>

**Long answer:** Here's an almost-character-by-character explanation of the whole script:

<!-- GitHub markdown doesn't support colspan sadly -->
<table>
  <tr>
    <th>Character sequence</th>
    <th>Bash interpretation</th>
    <th>PowerShell interpretation</th>
    <th>Command Prompt interpretation</th>
  </tr>

  <tr>
    <td><code>echo</code></td>
    <td colspan=3><center>Same for all shells</center></td>
  </tr>
  <tr>
    <td><code>^"</code></td>
    <td colspan=2><center>Echo <code>^</code> and begin a string literal</center></td>
    <td>Echo <code>"</code> (<code>^</code> is the escape character)</td>
  </tr>
  <tr>
    <td><code>>NUL</code></td>
    <td colspan=2><center>&lt;Inside string literal&gt;</center></td>
    <td>Redirect output to <code>NUL</code> (discard)</td>
  </tr>
  <tr>
    <td><code>\"</code></td>
    <td>&lt;Inside string literal&gt;</td>
    <td>End string literal</td>
    <td>Echo <code>\</code> and begin string literal</td>
  </tr>
  <tr>
    <td><code>>$null</code></td>
    <td>&lt;Inside string literal&gt;</td>
    <td>Redirect output to <code>$null</code> (discard)</td>
    <td>&lt;Inside string literal&gt;</td>
  </tr>
  <tr>
    <td><code>"</code></td>
    <td>End string literal</td>
    <td>Begin string literal</td>
    <td>End string literal</td>
  </tr>
  <tr>
    <td><code>^"</code></td>
    <td>Echo <code>^</code> and begin string literal</td>
    <td><code>^</code> into string literal and end literal</td>
    <td>Echo <code>"</code></td>
  </tr>
  <tr>
    <td><code>;</code></td>
    <td>&lt;Inside string literal&gt;</td>
    <td>Command seperator</td>
    <td>Echo <code>;</code></td>
  </tr>
  <tr>
    <td><code>&</code></td>
    <td style="background:#ece994;color:#000">&lt;Inside string literal&gt;</td>
    <td>Invocation operator</td>
    <td>Command seperator</td>
  </tr>
</table>