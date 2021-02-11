---
external help file:
Module Name: hpc
online version:
schema: 2.0.0
title: Remove-HpcMember
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

# Remove-HpcMember

## SYNOPSIS
Removes members from the HPC cluster or from specified roles.

## SYNTAX

```
Remove-HpcMember [-Name] <String[]> [-Role <String[]>]
 [-Scheduler <String[]>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-HpcMember** cmdlet removes one or more specified members from the HPC cluster or from the specified roles.
If you do not specify a role, the members are removed from all roles to which they belong.

## EXAMPLES

### Example 1: Remove a member by name
```
PS C:\>Remove-HpcMember -Name "CONTOSO\PattiFuller"
```

This command removes the user or administrator with a user name of PattiFuller in the CONTOSO domain from the HPC cluster.
If CONTOSO\PattiFuller belongs to both the user and administrator roles, the **Remove-HpcMember** cmdlet removes CONTOSO\PattiFuller from both roles.

### Example 2: Remove a member from a role
```
PS C:\>Remove-HpcMember -Name "CONTOSO\PattiFuller" -Role "Administrator"
```

This command removes the account with a user name of PattiFuller in the CONTOSO domain from the administrator role for the HPC cluster.
If CONTOSO\PattiFuller also belongs to the user role, then CONTOSO\PattiFuller remains a member of the HPC cluster in that role.

### Example 3: Remove multiple members
```
PS C:\>Remove-HpcMember -Name "CONTOSO\user1,CONTOSO\user2"
```

This command removes the users or administrators with user names of user1 and user2 in the CONTOSO domain from the HPC cluster.
If CONTOSO\user1 or CONTOSO\user2 belongs to both the user and administrator roles, the **Remove-HpcMember** cmdlet removes that account from both roles.

### Example 4: Get a member by name and remove it
```
PS C:\>Get-HpcMember -Name "CONTOSO\PattiFuller" | Remove-HpcMember
```

Gets the **HpcMember** object or objects for the member with a user name of someone in the CONTOSO domain, and then removes that member from all roles to which the member belongs and from the HPC cluster by redirecting the Name property of the **HpcMember** object or objects to the **Remove-HpcMember** cmdlet.

### Example 5: Get members by role and remove them
```
PS C:\>Get-HpcMember -Role "User" | Remove-HpcMember
```

This command gets the **HpcMember** objects for all the members of the user role for the HPC cluster, and then removes those members from the user role by redirecting the Name and Roles properties of the **HpcMember** objects to the **Remove-HpcMember** cmdlet.

## PARAMETERS

### -Name
Specifies an array of names for the members that you want to remove from the HPC cluster, or from the role that the *Role* parameter specifies.
Use the domain\user_name format to specify a member.

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
Specifies an array of roles from which you want to remove the members.
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

### HpcMember[]

## OUTPUTS

### None

## NOTES
* The built-in ConfirmImpact setting for this cmdlet is Medium. If this ConfirmImpact setting is equal to or higher than the value of the $ConfirmPreference variable for your environment, the cmdlet prompts for confirmation unless you specify `-Confirm:$False`. If this ConfirmImpact setting is lower than the value of the $ConfirmPreference variable for your environment, the cmdlet does not prompt for confirmation unless you specify `-Confirm` or `-Confirm:$True`.
* You must be a cluster administrator to run this cmdlet successfully.
* For information about user roles on the HPC cluster, see Understanding User Roleshttp://technet.microsoft.com/library/ff919445(v=ws.10).aspx (http://technet.microsoft.com/library/ff919445(v=ws.10).aspx) in the TechNet library.

## RELATED LINKS

[Add-HpcMember](./Add-HpcMember.md)

[Get-HpcMember](./Get-HpcMember.md)
