---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/get-vmhostsupportedversion?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-VMHostSupportedVersion
---

# Get-VMHostSupportedVersion

## SYNOPSIS
Returns a list of virtual machine configuration versions that are supported on a host.

## SYNTAX

### ComputerName (Default)
```
Get-VMHostSupportedVersion [[-ComputerName] <String[]>] [[-Credential] <PSCredential[]>] [-Default]
 [<CommonParameters>]
```

### CimSession
```
Get-VMHostSupportedVersion [-CimSession] <CimSession[]> [-Default] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMHostSupportedVersion** cmdlet returns a list of virtual machine configuration versions that are supported on a host.

## EXAMPLES

### Example 1: Return a table of supported configurations
```
PS C:\> Get-VMHostSupportedVersion
```

This command returns a table showing the supported virtual machine configuration versions on this host.

### Example 2: Return the default configuration version
```
PS C:\> Get-VMHostSupportedVersion -Default
```

This command returns the default virtual machine configuration version for this host.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: CimSession
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts to run the cmdlet.
NetBIOS names, IP addresses, and fully-qualified domain names are allowable.
The default is the local computer.
Use "localhost" or a dot (".") to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: ComputerName
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Credential
Specifies a user account that has permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: ComputerName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Default
Specifies that the cmdlet is to return the default virtual machine configuration version for this host.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMHostSupportedVersion

## NOTES

## RELATED LINKS

[Get-VMHost](./Get-VMHost.md)

