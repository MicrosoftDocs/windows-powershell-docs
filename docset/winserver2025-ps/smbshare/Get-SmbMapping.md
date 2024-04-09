---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: SmbMapping.cdxml-help.xml
Module Name: SmbShare
ms.date: 02/22/2024
online version: https://learn.microsoft.com/powershell/module/smbshare/get-smbmapping?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-SmbMapping
---

# Get-SmbMapping

## SYNOPSIS
Retrieves the SMB client directory mappings created for a server.

## SYNTAX

```
Get-SmbMapping [[-LocalPath] <String[]>] [[-RemotePath] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `Get-SmbMapping` cmdlet retrieves the Server Message Block (SMB) client directory mappings
created for a server. This can be a mapping from a local drive letter to a remote shared folder, or
it can be a mapping without a local path.

## EXAMPLES

### Example 1: Get SMB client directory mappings

```powershell
Get-SmbMapping
Status                                  Local Path                              Remote Path
------                                  ----------                              -----------
OK                                      X:                                      \\Contoso-SO\VMFiles
OK                                      Y:                                      \\Contoso-FS\VMS1
```

This command retrieves the SMB client directory mappings created for the SMB server.

### Example 2: Get SMB client directory mapping for a directory

```powershell
Get-SmbMapping -LocalPath "X:" | Select-Object -Property *
Status                : OK
LocalPath             : X:
RemotePath            : \\Contoso-SO\VMFiles
PSComputerName        :
CimClass              : ROOT/Microsoft/Windows/SMB:MSFT_SmbMapping
CimInstanceProperties : {LocalPath, RemotePath, Status}
CimSystemProperties   : Microsoft.Management.Infrastructure.CimSystemProperties
```

This command retrieves the SMB client directory mapping for the **X:** directory created for the SMB
server.

## PARAMETERS

### -AsJob

Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to
complete.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession

Runs the cmdlet in a remote session or on a remote computer. Enter a computer name or a session
object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/get-cimsession)
or [Get-CimSession](/powershell/module/cimcmdlets/get-cimsession) cmdlet. The default is the
current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocalPath

Specifies the local path used to map the remote path on this computer.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RemotePath

Specifies the remote path that's accessed from this computer.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit

Specifies the maximum number of concurrent operations that can be established to run the cmdlet. If
this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an
optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the
computer. The throttle limit applies only to the current cmdlet, not to the session or to the
computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUTS

### System.String[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/SMB/MSFT_SmbMapping

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays
Windows Management Instrumentation (WMI) objects. The path after the pound sign (`#`) provides the
namespace and class name for the underlying WMI object. This cmdlet returns a **MSFT_SmbMapping**
object that represents the mappings created from the SMB client to SMB shares.

## NOTES

## RELATED LINKS

[New-SmbMapping](New-SmbMapping.md)

[Remove-SmbMapping](Remove-SmbMapping.md)
