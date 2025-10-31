---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.GroupPolicy.Commands.dll-Help.xml
Module Name: GroupPolicy
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/grouppolicy/get-gppermission?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-GPPermission
---

# Get-GPPermission

## SYNOPSIS

Gets the permission level for one or more security principals on a specified GPO.

## SYNTAX

### SourcebyGUID (Default)

```
Get-GPPermission -Guid <Guid> [-TargetName <String>] [-TargetType <PermissionTrusteeType>]
 [-DomainName <String>] [-Server <String>] [-All] [<CommonParameters>]
```

### SourcebyName

```
Get-GPPermission [-Name] <String> [-TargetName <String>] [-TargetType <PermissionTrusteeType>]
 [-DomainName <String>] [-Server <String>] [-All] [<CommonParameters>]
```

## DESCRIPTION

The `Get-GPPermission` cmdlet gets the permission level for one or more security principals on the
specified Group Policy Object (GPO). You can use the **TargetName** and **TargetType** parameters to
specify a user, security group, or computer for which to get the permission level. You can use the
**All** parameter to get the permission level for each security principal that includes: user,
security group, or computer. This only works for a user, security group, or computer that has
permissions on the GPO. You can specify the GPO by its display name or by its GUID.

## EXAMPLES

### Example 1: Get the permission level for group on the specified GPO

```powershell
Get-GPPermission -Name "TestGpo" -TargetName "Domain Users" -TargetType Group
```

```Output
Trustee         : Domain Users
TrusteeType     : Group
PermissionLevel : GpoRead
Inherited       : False
```

This command gets the permission level for the Domain Users group on the GPO named TestGpo.

### Example 2: Get the permission level for group on the specified GPO with the specified GUID

```powershell
$params = @{
    Domain     = 'sales.contoso.com'
    Server     = 'DC1'
    GUID       = 'fa4a9473-6e2a-4b87-ab78-175e68d97bde'
    TargetName = 'Domain Admins'
    TargetType = 'Group'
}
Get-GPPermission @params
```

This command gets the permission level for the Domain Admins group on the GPO with the GUID
`fa4a9473-6e2a-4b78-175e68d97bde` in the `Sales.Contoso.com` domain. The `DC1.sales.contoso.com`
domain controller is contacted to complete the operation.

If the domain of the user that's running the session (or, for startup and shutdown scripts, the
computer) is different from the `sales.contoso.com` domain, a trust must exist between the two
domains, or the command fails.

### Example 3: Get the permission level for all security principals on the specified GPO

```powershell
Get-GPPermission -Name "TestGPO" -All
```

```Output
Trustee     : Authenticated Users
TrusteeType : WellKnownGroup
Permission  : GpoApply
Inherited   : False

Trustee     : Domain Admins
TrusteeType : Group
Permission  : GpoEditDeleteModifySecurity
Inherited   : False

Trustee     : Enterprise Admins
TrusteeType : Group
Permission  : GpoEditDeleteModifySecurity
Inherited   : False

Trustee     : ENTERPRISE DOMAIN CONTROLLERS
TrusteeType : WellKnownGroup
Permission  : GpoRead
Inherited   : False

Trustee     : SYSTEM
TrusteeType : WellKnownGroup
Permission  : GpoEditDeleteModifySecurity
Inherited   : False
```

This command gets the permission level for each security principal that has permissions on the GPO
named `TestGPO`.

### Example 4: Get the display name of each GPO for a specific permissions

```powershell
Get-GPO -All | ForEach-Object {
    if ( $_ |
            $params = @{
                TargetName  = 'contoso\Domain Admins'
                TargetType  = 'Group'
                ErrorAction = 'SilentlyContinue'
            }
            Get-GPPermission @params) {
            $_.DisplayName
        }
    }
```

```Output
Default Domain Policy
TestGPO-1
TestGPO-2 Default Domain Controllers Policy
Internet Security
TestGPO
```

This command lists the display name of each GPO (in the domain) on which the specified security
principal has permissions.

First, `Get-GPO` is used to retrieve all the GPOs in the domain (`Get-GPO -All`). Then, the
collection is piped into the `Foreach-Object` command. As each GPO is evaluated, it's piped into
`Get-GPPermissions`. If a permission level is returned, the **DisplayName** property of the GPO is
printed.

The **ErrorAction** parameter is set to `SilentlyContinue`. This is because a non-terminating error
occurs if the specified security principal doesn't have permissions on the GPO. Specifying the
**ErrorAction** as `SilentlyContinue` prevents the error messages from being printed for GPOS on
which the security principal doesn't have permissions. For more information about the
**ErrorAction** parameter, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## PARAMETERS

### -All

Indicates that the cmdlet gets the permission level for each user, group, or computer that has
permissions on the GPO.

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

### -DomainName

Specifies the domain for this cmdlet. You must specify the fully qualified domain name (FQDN) of the
domain. The GPO specified must exist in this domain.

If you don't specify the **Domain** parameter, the domain of the user that's running the current
session is used. If the cmdlet is being run from a computer startup or shutdown script, the domain
of the computer is used. For more information, see the Notes section in the full Help.

If you specify a domain that's different from the domain of the user that's running the current
session (or, for a startup or shutdown script, the computer), a trust must exist between that domain
and the domain of the user or the computer.

You can also refer to the **Server** parameter by its built-in alias, domain. For more information,
see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Domain

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Guid

Specifies the GPO from which to retrieve the permission level by its globally unique identifier
(GUID). The `GUID` uniquely identifies the GPO.

You can also refer to the **Guid** parameter by its built-in alias, **Id**. For more information,
see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: Guid
Parameter Sets: SourcebyGUID
Aliases: ID

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name

Specifies the GPO from which to retrieve the permission level by its display name.

The display name isn't guaranteed to be unique in the domain. If another GPO with the same display
name exists in the domain an error occurs. You can use the **Guid** parameter to uniquely identify a
GPO.

You can also refer to the **Name** parameter by its built-in alias, **DisplayName**. For more
information, see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

```yaml
Type: System.String
Parameter Sets: SourcebyName
Aliases: DisplayName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Server

Specifies the name of the domain controller that this cmdlet contacts to complete the operation. You
can specify either the fully qualified domain name (FQDN) or the host name.

If you don't specify the name using the **Server** parameter, the PDC emulator is contacted.

You can also refer to the **Server** parameter by its built-in alias, **DC**. For more information,
see [about_Aliases](/powershell/module/microsoft.powershell.core/about/about_aliases).

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

Specifies the name of the security principal for which to get the permission level. You can specify
a user, a security group, or a computer. You can use either the domain-qualified name of the
security principal (domain\account) or just its name.

For instance, in the `contoso.com` domain, to specify:

- The username, use `contoso\someuser` or `someuser`.
- The Domain Admins security group, use `contoso\Domain Admins` or `Domain Admins`.
- The computer name, use `contoso\computer-01` or `computer-01`.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetType

The type of security principal for which to get the permission level. The acceptable values for this
parameter are:

- Computer
- User
- Group

```yaml
Type: PermissionTrusteeType
Parameter Sets: (All)
Aliases:
Accepted values: Computer, User, Group

Required: False
Position: Named
Default value: None
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

You can pipe a GPO to this cmdlet for which to get the permission level. Collections that contain
GPOs from different domains are not supported.

## OUTPUTS

### Microsoft.GroupPolicy.GPPermissionCollection

### Microsoft.GroupPolicy.GPPermission

This cmdlet returns an object that represents permissions for the specified security principal
(user, group, or computer) on the GPO.

## NOTES

You can use the **DomainName** parameter to explicitly specify the domain for this cmdlet. If you do
not explicitly specify the domain, the cmdlet uses the default domain. The default domain is the
domain that is used to access network resources by the security context under which the current
session is running. This domain is typically the domain of the user that is running the session. For
example, the domain of the user who started the session by opening Windows PowerShell or the domain
of a user that is specified in a runas command. However, computer startup and shutdown scripts run
under the context of the LocalSystem account. The LocalSystem account is a built-in local account,
and it accesses network resources under the context of the computer account. Therefore, when this
cmdlet is run from a startup or shutdown script, the default domain is the domain to which the
computer is joined.

## RELATED LINKS

[Set-GPPermission](./Set-GPPermission.md)
