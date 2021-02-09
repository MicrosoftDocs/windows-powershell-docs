---
external help file: MSFT_NfsServerTasks.cmdletDefinition.cdxml-help.xml
Module Name: NFS
online version: 
schema: 2.0.0
title: Set-NfsClientgroup
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 3875B931-5D6D-4E60-AFA2-01AFDD09F95C
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Set-NfsClientgroup

## SYNOPSIS
Adds and removes client computers from a client group.

## SYNTAX

```
Set-NfsClientgroup [-ClientGroupName] <String> [[-AddMember] <String[]>] [[-RemoveMember] <String[]>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NfsClientGroup** cmdlet adds and removes client computers from a client group on a Network File System (NFS) server.
Use the **ClientGroupName** parameter to specify a client group to modify.
Then, use the **AddMember** parameter to specify the client computers to add, and use the **RemoveMember** parameter to specify the client computers to remove.

## EXAMPLES

### Example 1: Add a client computer to a client group
```
PS C:\> Set-NfsClientGroup -Name "Contoso-Group2" -AddMember "10.121.24.132"
```

This command adds the client computer that has the IP address 10.121.24.132 to the client group named Contoso-Group2.

### Example 2: Remove a client computer from a client group
```
PS C:\> Set-NfsClientGroup -ClientGroupName "Contoso-Group1" -RemoveMember "bill-laptop"
```

This command removes the client computer named bill-laptop from the client group named Contoso-Group1.

## PARAMETERS

### -AddMember
Specifies an array of host names or IP addresses of client computers to add to the specified client group.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: add

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
Specifies the name of a client group.

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

### -RemoveMember
Specifies an array of host names or IP addresses of client computers to remove from the specified client group.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: remove

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

[New-NfsClientgroup](./New-NfsClientgroup.md)

[Remove-NfsClientgroup](./Remove-NfsClientgroup.md)

[Rename-NfsClientgroup](./Rename-NfsClientgroup.md)

