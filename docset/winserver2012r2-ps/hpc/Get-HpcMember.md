---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Get-HpcMember
description:
keywords: powershell, cmdlet
ms.date: 12/20/2016
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: http://go.microsoft.com/fwlink/?LinkId=182659
schema: 2.0.0
ms.assetid: B0D29FB7-E5E3-466A-8247-05A7151F1734
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Get-HpcMember

## SYNOPSIS
Gets a member for the HPC cluster.

## SYNTAX

```
Get-HpcMember [[-Name] <String[]>] [-Role <String[]>] [-Scheduler <String[]>] [<CommonParameters>]
```

## DESCRIPTION
The **Get-HpcMember** cmdlet gets one or more specified members for the HPC cluster, or gets all members of one or more specified roles.
If you do not specify any members or roles, the **Get-HpcMember** cmdlet gets all members in all roles for the HPC cluster.

## EXAMPLES

### Example 1: Get all users and administrators
```
PS C:\>Get-HpcMember
```

This command gets all of the users and administrators for the HPC cluster.

### Example 2: Get administrators by head node
```
PS C:\>Get-HpcMember -Role "Administrator" -Scheduler "HeadNode"
```

This command gets all of the administrators for the HPC cluster with a head node named HeadNode.

### Example 3: Get a member by name
```
PS C:\>Get-HpcMember -Name "CONTOSO\PattiFuller"
```

This command gets the user or administrator with a user name of PattiFuller in the CONTOSO domain.
If CONTOSO\PattiFuller is both a user and an administrator, the cmdlet gets two entries or **HpcMember** objects for CONTOSO\PattiFuller.

### Example 4: Get all users for a domain
```
PS C:\>Get-HpcMember -Name "CONTOSO\*" -Role "User"
```

This command gets all of the users for the HPC cluster that belong to the domain named CONTOSO.

## PARAMETERS

### -Name
Specifies an array of members for which you want to get information or **HpcMember** objects.
Use the domain\user_name format to specify a member.
If someone belongs to more than one role, the **Get-HpcMember** cmdlet gets entries for each role, unless you also specify the *Role* parameter.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Role
Specifies an array of roles for the members for which you want to get information or **HpcMember** objects.
Valid values are: User, Administrator.

The following additional roles were introduced in HPC Pack 2012 with Service Pack 1 (SP1): JobAdministrator and JobOperator.
These roles are not supported in previous versions.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Scheduler
Specifies the host name or IP address of the head node for the cluster that includes the members.
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

### HpcMember[]

## OUTPUTS

### HpcMember[]

## NOTES
* You must be a cluster administrator to run this cmdlet successfully.
* For information about user roles on the HPC cluster, see Understanding User Roleshttp://technet.microsoft.com/library/ff919445(v=ws.10).aspx.

## RELATED LINKS

[Add-HpcMember](./Add-HpcMember.md)

[Remove-HpcMember](./Remove-HpcMember.md)
