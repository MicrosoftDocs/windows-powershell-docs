---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: brianlic
author: brianlic-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: New-VMGroup
ms.assetid: DE25B3FF-9D3D-4A1D-B209-EFD5F56F5FD1
---

# New-VMGroup

## SYNOPSIS
Creates a virtual machine group.

## SYNTAX

```
New-VMGroup [-Name] <String> [-GroupType] <GroupType> [[-Id] <Guid>] [-CimSession <CimSession[]>]
 [-ComputerName <String[]>] [-Credential <PSCredential[]>] [<CommonParameters>]
```

## DESCRIPTION
The **New-VMGroup** cmdlet creates a virtual machine group.

## EXAMPLES

### Example 1: Create a group to contain virtual machines
```
PS C:\> New-VMGroup -Name "CollectionGroup07" -GroupType VMCollectionType
```

This command creates a virtual machine group named CollectionGroup07 of type VMCollectionType.
This group can contain collections of virtual machines.

### Example 2: Create a group to contain groups of virtual machines
```
PS C:\> New-VMGroup -Name "ManagementCollectionGroup03" -GroupType ManagementCollectionType
```

This command creates a virtual machine group named ManagementCollectionGroup03 of type ManagementCollectionType.
This group can contain collections of other groups.

## PARAMETERS

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies one or more Hyper-V hosts that run this cmdlet.
NetBIOS names, IP addresses, and fully qualified domain names are allowable.
The default is the local computer.
Use localhost or a dot (.) to specify the local computer explicitly.

```yaml
Type: String[]
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupType
Specifies the type of group that this cmdlet creates.
The acceptable values for this parameter are: ManagementCollectionType and VMCollectionType.

```yaml
Type: GroupType
Parameter Sets: (All)
Aliases: 
Accepted values: VMCollectionType, ManagementCollectionType

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Specifies the unique ID of the group that this cmdlet creates.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name for the group that this cmdlet creates.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.PowerShell.VMGroup

## NOTES

## RELATED LINKS

[Get-VMGroup](./Get-VMGroup.md)

[Remove-VMGroup](./Remove-VMGroup.md)

[Rename-VMGroup](./Rename-VMGroup.md)

