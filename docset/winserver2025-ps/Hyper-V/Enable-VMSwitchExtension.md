---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/enable-vmswitchextension?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-VMSwitchExtension
---

# Enable-VMSwitchExtension

## SYNOPSIS
Enables one or more extensions on one or more switches.

## SYNTAX

### ExtensionName (Default)
```
Enable-VMSwitchExtension [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Name] <String[]> [<CommonParameters>]
```

### ExtensionNameSwitchName
```
Enable-VMSwitchExtension [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Name] <String[]> [-VMSwitchName] <String[]> [<CommonParameters>]
```

### ExtensionNameSwitchObject
```
Enable-VMSwitchExtension [-Name] <String[]> [-VMSwitch] <VMSwitch[]> [<CommonParameters>]
```

### ExtensionObject
```
Enable-VMSwitchExtension [-VMSwitchExtension] <VMSwitchExtension[]> [<CommonParameters>]
```

## DESCRIPTION
The **Enable-VMSwitchExtension** cmdlet enables one or more extensions on one or more switches.
You can use the **Get-VMSystemSwitchExtension** cmdlet to enumerate the virtual switch extensions installed on the system.

## EXAMPLES

### Example 1
```
PS C:\> Enable-VMSwitchExtension -VMSwitchName External -Name "Microsoft Windows Filtering Platform"
```

Enables WFP ("Microsoft Windows Filtering Platform") on a virtual switch named External.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: ExtensionName, ExtensionNameSwitchName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which an extension is to be enabled.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: ExtensionName, ExtensionNameSwitchName
Aliases: PSComputerName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: ExtensionName, ExtensionNameSwitchName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the network extension to be enabled.

```yaml
Type: String[]
Parameter Sets: ExtensionName, ExtensionNameSwitchName, ExtensionNameSwitchObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSwitch
Specifies the virtual switch on which the extension is to be enabled.

```yaml
Type: VMSwitch[]
Parameter Sets: ExtensionNameSwitchObject
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMSwitchExtension
Specifies the extension to be enabled.

```yaml
Type: VMSwitchExtension[]
Parameter Sets: ExtensionObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMSwitchName
Specifies the name of the switch on which the extension is to be enabled.

```yaml
Type: String[]
Parameter Sets: ExtensionNameSwitchName
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMSwitchExtension

## NOTES

## RELATED LINKS

