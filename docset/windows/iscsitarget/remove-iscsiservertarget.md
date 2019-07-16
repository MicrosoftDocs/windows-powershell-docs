---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: v-anbarr
author: andreabarr
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Remove-IscsiServerTarget
ms.reviewer:
ms.assetid: 623064A6-E1A2-40C9-9A44-2EF6D22518CD
---

# Remove-IscsiServerTarget

## SYNOPSIS
Deletes the specified iSCSI target.

## SYNTAX

### TargetName (Default)
```
Remove-IscsiServerTarget [-TargetName] <String> [-ComputerName <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### InputObject
```
Remove-IscsiServerTarget -InputObject <IscsiServerTarget> [-ComputerName <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-IscsiServerTarget** cmdlet deletes an iSCSI Target object.
An iSCSI initiator cannot access the virtual disk after the target is deleted.

## EXAMPLES

### Example 1: Remove a target
```
PS C:\> Remove-IscsiServerTarget -Targetname "TargetOne"
```

This example deletes the target named TargetOne on the local server.

### Example 2: Remove all targets on a server
```
PS C:\> $all = Get-IscsiServerTarget
PS C:\> ForEach-Object -InputObject ($each in $all) -Process {Remove-IscsiServerTarget -InputObject $each}
```

The example deletes all of the targets on the local server.

## PARAMETERS

### -ComputerName
Specifies the computer name, or IP address, of the remote computer, if this cmdlet is run on a remote computer.

Specifies the cluster resource group network name, or cluster node name, if this cmdlet is run on a cluster configuration.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Credential
Specifies the credentials when connecting to a remote computer.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Accepts an iSCSI Target object from the input pipeline.

```yaml
Type: IscsiServerTarget
Parameter Sets: InputObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetName
Specifies the name of the iSCSI target.

```yaml
Type: String
Parameter Sets: TargetName
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Iscsi.Target.Commands.IscsiServerTarget

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[ForEach-Object](http://go.microsoft.com/fwlink/p/?Linkd=113300)

[Get-IscsiServerTarget](./Get-IscsiServerTarget.md)

[New-IscsiServerTarget](./New-IscsiServerTarget.md)

[Set-IscsiServerTarget](./Set-IscsiServerTarget.md)

