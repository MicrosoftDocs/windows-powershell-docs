---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-VMSwitchExtension
ms.reviewer:
ms.assetid: 38546FDC-E327-4EAE-A851-E6C55615D982
---

# Get-VMSwitchExtension

## SYNOPSIS
Gets the extensions on one or more virtual switches.

## SYNTAX

### SwitchName (Default)
```
Get-VMSwitchExtension [-VMSwitchName] <String[]> [[-Name] <String[]>] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [<CommonParameters>]
```

### SwitchObject
```
Get-VMSwitchExtension [-VMSwitch] <VMSwitch[]> [[-Name] <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-VMSwitchExtension** cmdlet gets the extensions on one or more virtual switches.
These extensions may be of different types, and may be either enabled or disabled.
Output can be filtered by extension.
The retrieved extension object does not contain embedded objects for features, or an array of feature IDs.

## EXAMPLES

### Example 1
```
PS C:\> Get-VMSwitch InternalSwitch | Get-VMSwitchExtension
```

Gets all virtual switch extensions available to the virtual switch InternalSwitch.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: SwitchName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts on which the extensions are to be retrieved.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: SwitchName
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
Parameter Sets: SwitchName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the extension to be retrieved.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSwitch
Specifies the virtual switch from which the extensions are to be retrieved.

```yaml
Type: VMSwitch[]
Parameter Sets: SwitchObject
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMSwitchName
Specifies the name of the virtual switch from which the extensions are to be retrieved.

```yaml
Type: String[]
Parameter Sets: SwitchName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMSwitchExtension

## NOTES

## RELATED LINKS

