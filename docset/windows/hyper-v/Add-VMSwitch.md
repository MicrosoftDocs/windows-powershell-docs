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
title: Add-VMSwitch
ms.reviewer:
ms.assetid: CBDB65E2-F651-4FF0-9BB1-9A13C104056F
---

# Add-VMSwitch

## SYNOPSIS
Adds a virtual switch to an Ethernet resource pool.

## SYNTAX

### NetworkByName (Default)
```
Add-VMSwitch [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-Name] <String[]> [-ResourcePoolName] <String[]> [<CommonParameters>]
```

### NetworkByObject
```
Add-VMSwitch [-VMSwitch] <VMSwitch[]> [-ResourcePoolName] <String[]> [<CommonParameters>]
```

## DESCRIPTION
The **Add-VMSwitch** cmdlet adds a virtual switch to an Ethernet resource pool.

## EXAMPLES

### Example 1
```
PS C:\> Add-VMSwitch -Name Test -ResourcePoolName "Engineering Department"
```

Adds virtual switch Test to Ethernet resource pool Engineering Department.

### Example 2
```
PS C:\> Get-VMSwitch -Name Test | Add-VMSwitch -ResourcePoolName "Engineering Department"
```

Adds virtual switch Test to Ethernet resource pool Engineering Department.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: NetworkByName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies an array of Hyper-V hosts.
The cmdlet adds the virtual switch on the Hyper-V hosts that you specify.

```yaml
Type: String[]
Parameter Sets: NetworkByName
Aliases: 

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
Parameter Sets: NetworkByName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the virtual switch to be added.

```yaml
Type: String[]
Parameter Sets: NetworkByName
Aliases: SwitchName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourcePoolName
Specifies the name of the resource pool to which the virtual switch is to be added.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMSwitch
Specifies the virtual switch to be added to the Ethernet resource pool.

```yaml
Type: VMSwitch[]
Parameter Sets: NetworkByObject
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

###  
None by default; **Microsoft.HyperV.PowerShell.VMNetwork** if **-PassThru** is present.

## NOTES

## RELATED LINKS

