# 更新到PowerShell Core 6.0

**[Cheng Jun](https://github.com/chengjun90)**

2018-01-13

---

2018年1月11日微软正式发布了[PowerShell Core 6.0](https://github.com/PowerShell/PowerShell/releases/tag/v6.0.0)。点击这里的超链接可以根据自己的电脑平台进行安装。

在Win10 安装PowerShell Core不会影响系统自带的PowerShell，所以可以放心安装和使用。

---

## PSEdition

在自带的PowerShell终端上输入`$PSVersionTable`，结果如下。
```PowerShell
PS C:\Users\cheng> $PSVersionTable

Name                           Value
----                           -----
PSVersion                      5.1.16299.98
PSEdition                      Desktop
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
BuildVersion                   10.0.16299.98
CLRVersion                     4.0.30319.42000
WSManStackVersion              3.0
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
```

在PowerShell Core终端上输入`$PSVersionTable`，结果如下。
```PowerShell
PS C:\Users\cheng> $PSVersionTable

Name                           Value
----                           -----
PSVersion                      6.0.0
PSEdition                      Core
GitCommitId                    v6.0.0
OS                             Microsoft Windows 10.0.16299
Platform                       Win32NT
PSCompatibleVersions           {1.0, 2.0, 3.0, 4.0...}
PSRemotingProtocolVersion      2.3
SerializationVersion           1.1.0.1
WSManStackVersion              3.0
```
两者一个重要区别就是PSEdition分别是Desktop和Core。

---

## 更新了哪些命令
下面列示部分的命令结果。
```PowerShell
PS C:\Users\cheng> Get-Command

CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Function        A:
Function        AddDscResourceProperty                             0.0        PSDesiredStateConfiguration
Function        AddDscResourcePropertyFromMetadata                 0.0        PSDesiredStateConfiguration
Function        Add-NodeKeys                                       0.0        PSDesiredStateConfiguration
Function        B:
Function        C:
Function        cd..
Function        cd\
Function        CheckResourceFound                                 0.0        PSDesiredStateConfiguration
Function        Clear-Host
Function        Compress-Archive                                   1.1.0.0    Microsoft.PowerShell.Archive
Function        Configuration                                      0.0        PSDesiredStateConfiguration
Function        ConvertFrom-SddlString                             3.1.0.0    Microsoft.PowerShell.Utility
Function        ConvertTo-MOFInstance                              0.0        PSDesiredStateConfiguration
Function        D:
Function        Disable-PSTrace                                    1.0.0.0    PSDiagnostics
Function        Disable-PSWSManCombinedTrace                       1.0.0.0    PSDiagnostics
Function        Disable-WSManTrace                                 1.0.0.0    PSDiagnostics
Function        E:
Function        Enable-PSTrace                                     1.0.0.0    PSDiagnostics
Function        Enable-PSWSManCombinedTrace                        1.0.0.0    PSDiagnostics
Function        Enable-WSManTrace                                  1.0.0.0    PSDiagnostics
Function        Expand-Archive                                     1.1.0.0    Microsoft.PowerShell.Archive
```

下面列示PowerShell Core 6.0新增的命令。
```PowerShell
PS C:\Users\cheng> Get-Command | Where-Object -FilterScript {$_.Version -eq "6.0.0.0"}

CommandType     Name                                               Version    Source
-----------     ----                                               -------    ------
Cmdlet          Add-History                                        6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Clear-History                                      6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Connect-PSSession                                  6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Debug-Job                                          6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Disable-PSRemoting                                 6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Disable-PSSessionConfiguration                     6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Disconnect-PSSession                               6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Enable-PSRemoting                                  6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Enable-PSSessionConfiguration                      6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Enter-PSHostProcess                                6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Enter-PSSession                                    6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Exit-PSHostProcess                                 6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Exit-PSSession                                     6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Export-ModuleMember                                6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          ForEach-Object                                     6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-Command                                        6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-Help                                           6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-History                                        6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-Job                                            6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-Module                                         6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-PSHostProcessInfo                              6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-PSSession                                      6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-PSSessionCapability                            6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Get-PSSessionConfiguration                         6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Import-Module                                      6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Invoke-Command                                     6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Invoke-History                                     6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          New-Module                                         6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          New-ModuleManifest                                 6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          New-PSRoleCapabilityFile                           6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          New-PSSession                                      6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          New-PSSessionConfigurationFile                     6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          New-PSSessionOption                                6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          New-PSTransportOption                              6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Out-Default                                        6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Out-Host                                           6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Out-Null                                           6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Receive-Job                                        6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Receive-PSSession                                  6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Register-ArgumentCompleter                         6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Register-PSSessionConfiguration                    6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Remove-Job                                         6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Remove-Module                                      6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Remove-PSSession                                   6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Save-Help                                          6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Set-PSDebug                                        6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Set-PSSessionConfiguration                         6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Set-StrictMode                                     6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Start-Job                                          6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Stop-Job                                           6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Test-ModuleManifest                                6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Test-PSSessionConfigurationFile                    6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Unregister-PSSessionConfiguration                  6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Update-Help                                        6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Wait-Job                                           6.0.0.0    Microsoft.PowerShell.Core
Cmdlet          Where-Object                                       6.0.0.0    Microsoft.PowerShell.Core
```
那么新增命令的比例有多大？结果显示在13.18%左右。
```
PS C:\Users\cheng> $n1=Get-Command | measure
PS C:\Users\cheng> $n2=Get-Command | Where-Object -FilterScript {$_.Version -eq "6.0.0.0"} | measure
PS C:\Users\cheng> $n2.Count/$n1.Count
0.131764705882353
```

---

## 更改VS Code的**输出**和**终端**
把VS Code的**输出**和**终端**更换到PowerShell Core。
打开“文件”-“首选项”-“设置”-“用户设置”中增加下面的命令：
```
"terminal.integrated.shell.windows": "C:\\Program Files\\PowerShell\\6.0.0\\pwsh.exe",

"code-runner.executorMap": {
  "powershell": "pwsh -ExecutionPolicy ByPass -File",
},
```
pwsh.exe是PowerShell Core的可执行文件。上述的安装路径需要自己根据实际安装情况进行调整。

另外，可以使用快捷键Win+R，输入pwsh，可以快速调用PowerShell Core。

---

<a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/"><img alt="知识共享许可协议" style="border-width:0" src="https://i.creativecommons.org/l/by-nc-nd/4.0/88x31.png" /></a><br />本作品采用<a rel="license" href="http://creativecommons.org/licenses/by-nc-nd/4.0/">知识共享署名-非商业性使用-禁止演绎 4.0 国际许可协议</a>进行许可。
