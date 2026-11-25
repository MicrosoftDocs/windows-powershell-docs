---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/set-gppermission?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-GPPermission
---

# Set-GPPermission

## SYNOPSIS

Grants a level of permissions to a security principal for one GPO or all the GPOs in a domain.

## SYNTAX

### PermissionOne(GUID) (Default)

```
Set-GPPermission -Guid <Guid> -PermissionLevel <GPPermissionType> -TargetName <String>
 -TargetType <PermissionTrusteeType> [-DomainName <String>] [-Server <String>] [-Replace] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### PermissionOne(Name)

```
Set-GPPermission [-Name] <String> -PermissionLevel <GPPermissionType> -TargetName <String>
 -TargetType <PermissionTrusteeType> [-DomainName <String>] [-Server <String>] [-Replace] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### PermissionAll

```
Set-GPPermission -PermissionLevel <GPPermissionType> -TargetName <String>
 -TargetType <PermissionTrusteeType> [-DomainName <String>] [-Server <String>] [-All] [-Replace]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

The `Set-GPPermission` cmdlet grants a level of permissions to a security principal (user,
security group, or computer) for one Group Policy Object (GPO) or all the GPOs in a domain. You use
the **TargetName** and **TargetType** parameters to specify a user, security group, or computer for
which to set the permission level. You can use the *Name* or the **Guid** parameter to set the
permission level for the security principal on a single GPO, or you can use the **All** parameter to
set the permission level for the security principal on all GPOs in the domain.

By default, if the security principal already has a higher permission level than the specified
permission level, the change is not applied. You can specify the **Replace** parameter, to remove
the existing permission level from the GPO before the new permission level is set. This ensures that
the existing permission level is replaced by the new permission level.

## EXAMPLES

### Example 1: Set the permission level for a security group belonging to a GPO

```powershell
Set-GPPermission -Name TestGpo -TargetName "Domain Users" -TargetType Group -PermissionLevel GpoRead
```

This command sets the permission level for the Domain Users security group to `GpoRead` for the GPO
named `TestGpo`. Because the **Replace** parameter is not specified, if the group already has a
permission level higher than `GpoRead`, such as `GpoEdit`, no action is taken.

### Example 2: Set the permission level for a security group that belongs to all GPOs

```powershell
$params = @{
    All             = $true
    TargetName      = "Marketing Admins"
    TargetType      = 'Group'
    PermissionLevel = 'GpoEdit'
    Replace         = $true
}
Set-GPPermission @params
```

This command sets the permission level for the `Marketing Admins` security group to `GpoEdit` on all
GPOs in the domain. This includes GPOs that are not linked to any site, domain, or OU. Because the
**Replace** parameter is specified, the new permission level overwrites the existing permissions set
for the group.

### Example 3: Replace the permission level of a security group for all GPOs on which the group has permissions

```powershell
Get-GPO -All |
    ForEach-Object {
        $getParams = @{
            TargetName  = "Marketing Admins"
            TargetType  = 'Group'
            ErrorAction = 'SilentlyContinue'
        }
        if ( $_ | Get-GPPermission @getParams) {
            $setParams = @{
                Replace         = $true
                PermissionLevel = 'GpoApply'
                TargetName      = "Marketing Admins"
                TargetType      = 'Group'
            }
            $_ | Set-GPPermission @setParams
        }
    }
```

```Output
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

This command replaces the current permission level of the `Marketing Admins` security group with
GpoApply for all GPOs on which the `Group` has permissions. The command returns each GPO for which
the new permission level is set.

The cmdlet is used to get all the GPOs in the domain. Then, the collection is piped into the
`ForEach-Object` command. As each GPO is evaluated, it is piped into `Get-GPPermission`. If a
permission level for the Marketing Admins group is returned, the GPO is piped into
`Set-GPPermission` to set the permission level for the group. The **Replace** parameter is
specified to make sure that the previous permission level is overwritten.

The **ErrorAction** parameter is set to `SilentlyContinue` for `Get-GPPermissions`. This is
because a non-terminating error occurs if the specified security principal does not have permissions
on the GPO. Specifying **ErrorAction** as `SilentlyContinue` prevents the error messages from being
printed for GPOs on which the security principal does not have permissions. For more information
about the **ErrorAction** parameter, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## PARAMETERS

### -All

Specifies that the permission level is set for the specified security principal for all GPOs in the
domain.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PermissionAll
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
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainName
Specifies the domain for this cmdlet. You must specify the fully qualified domain name (FQDN) of the
domain.

For the `Set-GPPermission` cmdlet, the GPO for which to get the permission level must exist in
this domain.

If you do not specify the **DomainName** parameter, the domain of the user that is running the
current session is used. If the cmdlet is being run from a computer startup or shutdown script, the
domain of the computer is used. For more information, see the Notes section in the full Help.

If you specify a domain that is different from the domain of the user that is running the current
session (or, for a startup or shutdown script, the computer), a trust must exist between that domain
and the domain of the user or the computer.

You can also refer to the **DomainName** parameter by its built-in alias, domain. For more
information, see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Domain

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Guid

Specifies the GPO for which to set the permission level by its globally unique identifier (GUID).
The GUID uniquely identifies the GPO.

You can also refer to the **Guid** parameter by its built-in alias, **Id**.

```yaml
Type: Guid
Parameter Sets: PermissionOne(GUID)
Aliases: ID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Specifies the GPO for which to set the permission level by its display name.

The display name is not guaranteed to be unique in the domain. If another GPO with the same display
name exists in the domain, an error occurs. You can use the **Guid** parameter to uniquely identify
a GPO.

You can also refer to the Name parameter by its built-in alias, **DisplayName**.

```yaml
Type: System.String
Parameter Sets: PermissionOne(Name)
Aliases: DisplayName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PermissionLevel

Specifies the permission level to set for the security principal.

The acceptable values for this parameter are:

- GpoRead
- GpoApply
- GpoEdit
- GpoEditDeleteModifySecurity
- None

```yaml
Type: GPPermissionType
Parameter Sets: (All)
Aliases:
Accepted values: None, GpoApply, GpoRead, GpoEdit, GpoEditDeleteModifySecurity, GpoCustom, WmiFilterEdit, WmiFilterFullControl, WmiFilterCustom, StarterGpoRead, StarterGpoEdit, StarterGpoFullControl, StarterGpoCustom, SomCreateWmiFilter, SomWmiFilterFullControl, SomCreateGpo, SomCreateStarterGpo, SomLogging, SomPlanning, SomLink

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Replace

Specifies that the existing permission level for the group or user is removed before the new
permission level is set. If a security principal is already granted a permission level that is
higher than the specified permission level and you do not use the *Replace* parameter, no change is
made.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server

Specifies the name of the domain controller that this cmdlet contacts to complete the operation. You
can specify either the fully qualified domain name (FQDN) or the host name.

If you do not specify the name by using the **Server** parameter, the primary domain controller
(PDC) emulator is contacted.

You can also refer to the **Server** parameter by its built-in alias, **DC**.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DC

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetName

The name of the security principal for which to set the permission level. You can specify a user, a
security group, or a computer. You can use either the domain-qualified name of the security
principal (domain\account) or just its name.

For instance, in the `contoso.com` domain, to specify:

- The user SomeUser, use `contoso\SomeUser` or `SomeUser`.

- The Domain Admins security group, use `contoso\Domain Admins` or `Domain Admins`.

- The computer computer-01, use `contoso\computer-01` or `computer-01`.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetType

The type of security principal for which to set the permission level. You must specify User, Group,
or Computer.

The acceptable values for this parameter are:

- Computer
- User
- Group

```yaml
Type: PermissionTrusteeType
Parameter Sets: (All)
Aliases:
Accepted values: Computer, User, Group

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf

Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.GroupPolicy.Gpo

You can pipe an object that represents a GPO to this cmdlet. Collections that contain GPOs from
different domains are not supported.

## OUTPUTS

### Microsoft.GroupPolicy.Gpo

This cmdlet returns an object that represents the GPO for which the permission level was set.

## NOTES

* You can use the **DomainName** parameter to explicitly specify the domain for this cmdlet.

  If you do not explicitly specify the domain, the cmdlet uses a default domain. The default domain
  is the domain that is used to access network resources by the security context under which the
  current session is running. This domain is typically the domain of the user that is running the
  session. For example, the domain of the user who started the session by opening Windows PowerShell
  from the Program Files menu, or the domain of a user that is specified in a runas command.
  However, computer startup and shutdown scripts run under the context of the LocalSystem account.
  The LocalSystem account is a built-in local account, and it accesses network resources under the
  context of the computer account. Therefore, when this cmdlet is run from a startup or shutdown
  script, the default domain is the domain to which the computer is joined.

## RELATED LINKS

[Get-GPPermission](./Get-GPPermission.md)

