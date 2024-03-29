---
external help file: GPv2_Cmdlets.xml
Module Name: GroupPolicy
online version: https://learn.microsoft.com/powershell/module/grouppolicy/set-gppermission?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-GPPermission

## SYNOPSIS
Grants a level of permissions to a security principal for one GPO or all the GPOs in a domain.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-GPPermission [-DomainName <String>] [-Replace] [-Server <String>] -Guid <Guid>
 -PermissionLevel <GPPermissionType> -TargetName <String> -TargetType <PermissionTrusteeType> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Set-GPPermission [-DomainName <String>] [-Replace] [-Server <String>] [-All]
 -PermissionLevel <GPPermissionType> -TargetName <String> -TargetType <PermissionTrusteeType> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Set-GPPermission [-Name] <String> [-DomainName <String>] [-Replace] [-Server <String>]
 -PermissionLevel <GPPermissionType> -TargetName <String> -TargetType <PermissionTrusteeType> [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
Grants a level of permissions to a security principal (user, security group, or computer) for one GPO or all the GPOs in a domain.
You use the TargetName and TargetType parameters to specify a user, security group, or computer for which to set the permission level.
You can use the Name or the Guid parameter to set the permission level for the security principal on a single GPO, or you can use the All parameter to set the permission level for the security principal on all GPOs in the domain.

By default, if the security principal already has a higher permission level than the specified permission level, the change is not applied.
You can specify the Replace parameter, to remove the existing permission level from the GPO before the new permission level is set.
This ensures that the existing permission level is replaced by the new permission level.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Set-GPPermission -Name TestGpo -TargetName "Domain Users" -TargetType Group -PermissionLevel GpoRead
```

Description

-----------

This command sets the permission level for the "Domain Users" security group to GpoRead for the GPO named "TestGpo".
Because the Replace parameter is not specified, if the group already has a permission level higher than GpoRead, such as GpoEdit, no action is taken.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Set-GPPermission -All -TargetName "Marketing Admins" -TargetType Group -PermissionLevel GpoEdit -Replace
```

Description

-----------

This command sets the permission level for the "Marketing Admins" security group to GpoEdit on all GPOs in the domain.
This includes GPOs that are not linked to any site, domain, or OU.
Because the Replace parameter is specified, the new permission level overwrites the existing permissions set for the group.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Get-GPO -All | foreach-object { if($_ | Get-GPPermission -TargetName "Marketing Admins" -TargetType Group -ErrorAction SilentlyContinue) {$_ | Set-GPPermission -Replace -PermissionLevel GpoApply -TargetName "Marketing Admins" -TargetType group }}

DisplayName      : TestGPO 
DomainName       : contoso.com 
Owner            : CONTOSO\Domain Admins 
Id               : 24f217d4-1403-4d43-9247-d17eeedb22f0 
GpoStatus        : AllSettingsEnabled 
Description      : 
CreationTime     : 3/1/2009 10:51:34 PM 
ModificationTime : 3/2/2009 12:53:40 AM 
UserVersion      : AD Version: 8, SysVol Version: 8 
ComputerVersion  : AD Version: 0, SysVol Version: 0 
WmiFilter        : 


DisplayName      : TestGPO-1 
DomainName       : contoso.com 
Owner            : CONTOSO\Domain Admins 
Id               : fe2f7402-101b-4b3c-87e4-85d3f47735cb 
GpoStatus        : AllSettingsEnabled 
Description      : 
CreationTime     : 3/1/2009 7:22:03 PM 
ModificationTime : 3/2/2009 12:53:54 AM 
UserVersion      : AD Version: 0, SysVol Version: 0 
ComputerVersion  : AD Version: 0, SysVol Version: 0 
WmiFilter        :
```

Description

-----------

This command replaces the current permission level of the "Marketing Admins" security group with GpoApply for all GPOs on which the group has permissions.
The command returns each GPO for which the new permission level is set.

First, Get-GPO is used to retrieve all the GPOs in the domain (Get-GPO -All).
Then, the collection is piped into the foreach-object command.
As each GPO is evaluated, it is piped into Get-GPPermissions.
If a permission level for the "Marketing Admins" group is returned, the GPO is piped into Set-gppermission to set the permission level for the group.
The Replace parameter is specified to make sure that the previous permission level is overwritten.

Note: The ErrorAction parameter is set to SilentlyContinue for Get-GPPermissions.
This is because a non-terminating error occurs if the specified security principal does not have permissions on the GPO.
Specifying the ErrorAction as SilentlyContinue prevents the error messages from being printed for GPOS on which the security principal does not have permissions.
For more information about the ErrorAction parameter, see about_CommonParameters.

## PARAMETERS

### -All
Specifies that the permission level is set for the specified security principal for all GPOs in the domain.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName
Specifies the domain for this cmdlet.
You must specify the fully qualified domain name (FQDN) of the domain (for example: sales.contoso.com). 

For the Set-GPPermission cmdlet, the GPO for which to get the permission level must exist in this domain. 

If you do not specify the DomainName parameter, the domain of the user that is running the current session is used.
(If the cmdlet is being run from a computer startup or shutdown script, the domain of the computer is used.) For more information, see the Notes section in the full Help. 

If you specify a domain that is different from the domain of the user that is running the current session (or, for a startup or shutdown script, the computer), a trust must exist between that domain and the domain of the user (or the computer).

You can also refer to the Server parameter by its built-in alias, "domain".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: (All)
Aliases: domain

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Guid
Specifies the GPO for which to set the permission level by its globally unique identifier (GUID).
The GUID uniquely identifies the GPO.

You can also refer to the Guid parameter by its built-in alias, "id".
For more information, see about_Aliases.

```yaml
Type: Guid
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the GPO for which to set the permission level by its display name.

The display name is not guaranteed to be unique in the domain.
If another GPO with the same display name exists in the domain, an error occurs.
You can use the Guid parameter to uniquely identify a GPO.

You can also refer to the Name parameter by its built-in alias, "displayname".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: displayname

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue, ByPropertyName)
Accept wildcard characters: False
```

### -PermissionLevel
Specifies the permission level to set for the security principal.
The valid permission levels are: GpoRead, GpoApply, GpoEdit, GpoEditDeleteModifySecurity or None.

```yaml
Type: GPPermissionType
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Replace
Specifies that the existing permission level for the group or user is removed before the new permission level is set.
If a security principal is already granted a permission level that is higher than the specified permission level and you do not use the Replace parameter, no change is made.

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

### -Server
Specifies the name of the domain controller that this cmdlet contacts to complete the operation.
You can specify either the fully qualified domain name (FQDN) or the host name.
For example:

FQDN: DomainController1.sales.contoso.com

Host Name: DomainController1

If you do not specify the name by using the Server parameter, the PDC emulator is contacted.

You can also refer to the Server parameter by its built-in alias, "dc".
For more information, see about_Aliases.

```yaml
Type: String
Parameter Sets: (All)
Aliases: dc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetName
The name of the security principal for which to set the permission level.
You can specify a user, a security group, or a computer.
You can use either the domain-qualified name of the security principal (domain\account) or just its name.

For example, in the contoso.com domain, to specify:

- The user "someuser", use "contoso\someuser" or "someuser".

- The Domain Admins security group, use "contoso\Domain Admins" or "Domain Admins".

- The computer "computer-01", use "contoso\computer-01" or "computer-01".

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetType
The type of security principal for which to set the permission level.
You must specify User, Group, or Computer.

The following values are permitted for this object type. 

- Computer

- User

- Group

```yaml
Type: PermissionTrusteeType
Parameter Sets: (All)
Aliases: 

Required: True
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
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.GroupPolicy.Gpo
An object that represents a GPO.
Collections that contain GPOs from different domains are not supported.

## OUTPUTS

### Microsoft.GroupPolicy.Gpo
Set-GPPermission returns an object that represents the GPO for which the permission level was set.

## NOTES
* You can use the DomainName parameter to explicitly specify the domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain.
The default domain is the domain that is used to access network resources by the security context under which the current session is running.
This domain is typically the domain of the user that is running the session.
For example, the domain of the user who started the session by opening Windows PowerShell from the Program Files menu, or the domain of a user that is specified in a runas command.
However, computer startup and shutdown scripts run under the context of the LocalSystem account.
The LocalSystem account is a built-in local account, and it accesses network resources under the context of the computer account.
Therefore, when this cmdlet is run from a startup or shutdown script, the default domain is the domain to which the computer is joined.

## RELATED LINKS

[Get-GPPermission](./Get-GPPermission.md)

