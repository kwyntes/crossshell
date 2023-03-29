# Cross(s)hell
A single shell snippet that works in Bash, PowerShell and Command Prompt.

## The script

With Bash syntax highlighting
```bash
echo ^">NUL \" >$null "^";&powershell.exe -c echo FETCH WINDOWS CODE;&echo '>NUL ' ">/dev/null;echo FETCH LINUX CODE;echo >/dev/null \"\`" <#\"">/dev/null #>>$null
```
With PowerShell syntax highlighting
```powershell
echo ^">NUL \" >$null "^";&powershell.exe -c echo FETCH WINDOWS CODE;&echo '>NUL ' ">/dev/null;echo FETCH LINUX CODE;echo >/dev/null \"\`" <#\"">/dev/null #>>$null
```
With Batch syntax highlighting
```batch
echo ^">NUL \" >$null "^";&powershell.exe -c echo FETCH WINDOWS CODE;&echo '>NUL ' ">/dev/null;echo FETCH LINUX CODE;echo >/dev/null \"\`" <#\"">/dev/null #>>$null
```

Note that the syntax highlighter doesn't actually understand what's going on either.
