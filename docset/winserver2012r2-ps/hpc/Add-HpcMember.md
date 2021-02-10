---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Add-HpcMember
description:
keywords: powershell, cmdlet
ms.date: 12/20/2016
ms.prod: powershell
ms.topic: reference
online version: http://go.microsoft.com/fwlink/?LinkId=182659
schema: 2.0.0
ms.assetid: B0D29FB7-E5E3-466A-8247-05A7151F1734
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Add-HpcMember

## SYNOPSIS
Adds a domain account to the HPC cluster as a member in a cluster role.

## SYNTAX

```
Add-HpcMember [-Name] <String[]> [-Role <String>] [-Scheduler <String[]>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Add-HpcMember** cmdlet adds one or more domain accounts to the HPC cluster as members in a cluster role.
If you do not specify a role, the **Add-HpcMember** cmdlet adds the specified accounts as users by default.

## EXAMPLES

### Example 1: Add a member by name
```
PS C:\>Add-HpcMember -Name "CONTOSO\PattiFuller"
```

This command adds the account with a user name of PattiFuller and a domain of CONTOSO to the HPC cluster as a user.

### Example 2: Add multiple members
```
PS C:\>Add-HpcMember -Name "CONTOSO\user1,CONTOSO\user2" -Role "Administrator"
```

This command adds the accounts with user names of user1 and user2 in the CONTOSO domain to the HPC cluster as administrators.

## PARAMETERS

### -Name
Specifies an array of accounts that you want to add as members to the HPC cluster.
Use the domain\user_name format.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Role
Specifies the role to which you want to add the member.
Valid values are: User, Administrator.
The default role is User.

The following additional roles were introduced in HPC Pack 2012 with Service Pack 1 (SP1): JobAdministrator and JobOperator.
These roles are not supported in previous versions.

Starting with HPC Pack 2012 with SP1, a member can be added in more than one cluster role and is granted the union of the privileges of the roles.

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

### -Scheduler
Specifies the host name or IP address of the head node for the cluster to which you want to add the member.
The value must be a valid computer name or IP address.
If you do not specify the *Scheduler* parameter, this cmdlet uses the scheduler on the head node that the CCP_SCHEDULER environment variable specifies.
To set this environment variable, run the following cmdlet:

`Set-Content Env:CCP_SCHEDULER \<head_node_name\>`

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### HpcMember[]

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.
* For information about user roles on the HPC cluster, see Understanding User Roleshttp://technet.microsoft.com/library/ff919445(v=ws.10).aspx on TechNet.

## RELATED LINKS

[Get-HpcMember](./Get-HpcMember.md)

[Remove-HpcMember](./Remove-HpcMember.md)
