---
external help file: Microsoft.Iscsi.Target.Commands.dll-Help.xml
Module Name: IscsiTarget
online version: 
schema: 2.0.0
title: Remove-IscsiVirtualDiskSnapshot
ms.author: v-kaunu
ms.reviewer: brianlic
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: D66A76E7-28E7-4231-91A4-03183871F4A0
---

# Remove-IscsiVirtualDiskSnapshot

## SYNOPSIS
Deletes the specified snapshot.

## SYNTAX

### SnapshotId (Default)
```
Remove-IscsiVirtualDiskSnapshot [-SnapshotId] <String> [-ComputerName <String>] [-Credential <PSCredential>]
 [<CommonParameters>]
```

### InputObject
```
Remove-IscsiVirtualDiskSnapshot -InputObject <IscsiVirtualDiskSnapshot> [-ComputerName <String>]
 [-Credential <PSCredential>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-IscsiVirtualDiskSnapshot** cmdlet deletes the specified snapshot.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Remove-IscsiVirtualDiskSnapshot -SnapshotId "{E9A5BA03-85B9-40CA-85DF-DC1695690B40}"
```

This example deletes the snapshot with the identifier (ID) {E9A5BA03-85B9-40CA-85DF-DC1695690B40}.

### EXAMPLE 2
```
PS C:\> Remove-IscsiVirtualDiskSnapshot -SnapshotId "{E9A5BA03-85B9-40CA-85DF-DC1695690B40}" -ComputerName "fscluster.contoso.com"
```

This example deletes the snapshot with the ID {E9A5BA03-85B9-40CA-85DF-DC1695690B40} on the remote file server cluster named fscluster.contoso.com.

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
Accepts an iSCSI Virtual Disk Snapshot object from the input pipeline.

```yaml
Type: IscsiVirtualDiskSnapshot
Parameter Sets: InputObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SnapshotId
Specifies the identifier (ID) for the snapshot.

```yaml
Type: String
Parameter Sets: SnapshotId
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Iscsi.Target.Commands.IscsiVirtualDiskSnapshot

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Dismount-IscsiVirtualDiskSnapshot](./Dismount-IscsiVirtualDiskSnapshot.md)

[Export-IscsiVirtualDiskSnapshot](./Export-IscsiVirtualDiskSnapshot.md)

[Get-IscsiVirtualDiskSnapshot](./Get-IscsiVirtualDiskSnapshot.md)

[Mount-IscsiVirtualDiskSnapshot](./Mount-IscsiVirtualDiskSnapshot.md)

[Set-IscsiVirtualDiskSnapshot](./Set-IscsiVirtualDiskSnapshot.md)

