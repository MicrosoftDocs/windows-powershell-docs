---
external help file: MSFT_NfsServerTasks.cmdletDefinition.cdxml-help.xml
Module Name: NFS
online version: 
schema: 2.0.0
title: New-NfsClientgroup
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: AE9F7C4F-D326-4DD5-B6FF-7EE2E14AD002
ms.author: v-kaunu
ms.reviewer: brianlic
---

# New-NfsClientgroup

## SYNOPSIS
Creates a client group on an NFS server.

## SYNTAX

```
New-NfsClientgroup [-ClientGroupName] <String> [[-AddMember] <String[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **New-NfsClientGroup** cmdlet creates a Network File System (NFS) client group on a target computer.
You can add one or more client computers to the new client group by using the **AddMember** parameter.
You can also add and remove members of the client group by using the **Set-NfsClientGroup** cmdlet.

## EXAMPLES

### Example 1: Create a client group and add members by using host names
```
PS C:\> New-NfsClientGroup -ClientGroupName "Contoso-Group1" -AddMember ("joe-desktop", "bill-laptop")
ClientGroupMembers : {joe-desktop,bill-laptop}
ClientGroupName    : Contoso-Group1
PSComputerName     :
```

This command creates a client group named Contoso-Group1 and adds client computers to the new client group by using the host names of the client computers.

### Example 2: Create a client group that has no members
```
PS C:\> New-NfsClientGroup -Name "Contoso-Group2"
ClientGroupMembers :
ClientGroupName    : Contoso-Group2
PSComputerName     :
```

This command creates a client group named Contoso-Group2.
No members are added to the new client group.

### Example 3: Create a client group and add a member by using an IP address
```
PS C:\> New-NfsClientGroup -Name "Contoso-Group2" -AddMember "10.121.24.132"
ClientGroupMembers : {10.121.24.132}
ClientGroupName    : Contoso-Group2
PSComputerName     :
```

This command creates a client group named Contoso-Group2 and adds a client computer that has the IP address 10.121.24.132 to the client group.

## PARAMETERS

### -AddMember
Specifies an array of host names or IP addresses of client computers to add to the new client group.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: add, member

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
ps_cimcommon_asjob

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
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

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

### -ClientGroupName
Specifies a name for a new client group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: name, cgname

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Nothing

## NOTES

## RELATED LINKS

[Get-NfsClientgroup](./Get-NfsClientgroup.md)

[Remove-NfsClientgroup](./Remove-NfsClientgroup.md)

[Rename-NfsClientgroup](./Rename-NfsClientgroup.md)

[Set-NfsClientgroup](./Set-NfsClientgroup.md)

