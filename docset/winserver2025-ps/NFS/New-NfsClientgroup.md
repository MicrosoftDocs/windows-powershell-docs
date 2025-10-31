---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NfsServerTasks.cmdletDefinition.cdxml-help.xml
Module Name: NFS
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/nfs/new-nfsclientgroup?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NfsClientgroup
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
You can add one or more client computers to the new client group by using the *AddMember* parameter.
You can also add and remove members of the client group by using the Set-NfsClientgroup cmdlet.

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
Accept wildcard characters: True
```

### -AsJob
Indicates that this cmdlet runs the command as a background job on a remote computer.
Use this parameter to run commands that take an extensive time to finish.

When you use the *AsJob* parameter, the command returns an object that represents the job, and then displays the command prompt.
You can continue to work in the session while the job finishes.
To manage the job, use the **Job** cmdlets.
To get the job results, use the Receive-Job cmdlet.

The *AsJob* parameter resembles using the Invoke-Command cmdlet to run a Start-Job command remotely.
However, with *AsJob*, the job is created on the local computer, even though the job runs on a remote computer, and the results of the remote job are automatically returned to the local computer.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251) and [about_Remote_Jobs](https://go.microsoft.com/fwlink/?LinkID=135184).

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Nothing

## NOTES

## RELATED LINKS

[Get-NfsClientgroup](./Get-NfsClientgroup.md)

[Remove-NfsClientgroup](./Remove-NfsClientgroup.md)

[Rename-NfsClientgroup](./Rename-NfsClientgroup.md)

[Set-NfsClientgroup](./Set-NfsClientgroup.md)

