---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/get-adclaimtransformpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ADClaimTransformPolicy
---

# Get-ADClaimTransformPolicy

## SYNOPSIS
Returns one or more Active Directory claim transform objects based on a specified filter.

## SYNTAX

### Filter (Default)

```
Get-ADClaimTransformPolicy [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 -Filter <String> [-Properties <String[]>] [-Server <String>] [<CommonParameters>]
```

### Identity

```
Get-ADClaimTransformPolicy [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [[-Identity] <ADClaimTransformPolicy>] [-Properties <String[]>] [-Server <String>]
 [<CommonParameters>]
```

### LdapFilter

```
Get-ADClaimTransformPolicy [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 -LDAPFilter <String> [-Properties <String[]>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Get-ADClaimTransformPolicy` cmdlet returns one or more Active Directory claim transform objects
based on a specified filter.

## EXAMPLES

### Example 1: Get a list of all claims transformation policies

```powershell
Get-ADClaimTransformPolicy -Filter *
```

This command retrieves a list of all claims transformation policies.

### Example 2: Get all the claims transformation policies that are applied to a specific trust

```powershell
$trust = Get-ADTrust -Identity "corp.contoso.com"
$filter = "IncomingTrust -eq '$trust' -or OutgoingTrust -eq '$trust'"
Get-ADClaimTransformPolicy -Filter $filter
```

This example gets all the claims transformation policies that are applied to trusts made with
`corp.contoso.com`.

### Example 3: Get the claims transformation policy with a specify policy name

```powershell
Get-ADClaimTransformPolicy -Identity DenyAllPolicy
```

This command gets the claims transformation policy with the name `DenyAllPolicy`.

### Example 4: Get information on claims using a LDAP based query filter

```powershell
Get-ADClaimTransformPolicy -LDAPFilter "(name=DenyAll*)"
```

This command gets information on any claims transformation policies using an LDAP-based query filter
that looks for matches where policies have a name that starts with the word `DenyAll`.

## PARAMETERS

### -AuthType

Specifies the authentication method to use.
The acceptable values for this parameter are:

- `Negotiate` or `0`
- `Basic` or `1`

The default authentication method is `Negotiate`.

A Secure Sockets Layer (SSL) connection is required for the `Basic` authentication method.

```yaml
Type: Microsoft.ActiveDirectory.Management.ADAuthType
Parameter Sets: (All)
Aliases:
Accepted values: Negotiate, Basic

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies the user account credentials to use to perform this task. The default credentials are the
credentials of the currently logged on user unless the cmdlet is run from an Active Directory module
for Windows PowerShell provider drive. If the cmdlet is run from such a provider drive, the account
associated with the drive is the default.

To specify this parameter, you can type a user name, such as `User1` or `Domain01\User01` or you can
specify a **PSCredential** object. If you specify a user name for this parameter, the cmdlet prompts
for a password.

You can also create a **PSCredential** object by using a script or by using the `Get-Credential`
cmdlet. You can then set the **Credential** parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, Active
Directory module for Windows PowerShell returns a terminating error.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter

Specifies a query string that retrieves Active Directory Domain Services objects. This string uses
the Windows PowerShell expression language syntax. The Windows PowerShell expression language syntax
provides rich type-conversion support for value types received by the **Filter** parameter.

Specify the **Filter** parameter in one of the following formats:

- To match a single filter element: `{Attribute operator "value"}`
- To match multiple filter elements:
  `{(Attribute1 operator1 "value1") joinOperator (Attribute2 operator2 "value2")}`

Windows PowerShell wildcards other than `*`, such as `?`, are not supported by the **Filter**
syntax.

Valid filter operators are:

 `-eq`, `-le`, `-ge`, `-ne`, `-lt`, `-gt`, `-approx`, `-bor`, `-band`, `-recursivematch`, `-like`,
 `-notlike`

Valid join operators are:

`-and`, `-or`

The not operator is `-not`.

For a list of supported types for values, see `about_ActiveDirectory_ObjectModel`. For more
information about the **Filter** parameter, see `about_ActiveDirectory_Filter`.

```yaml
Type: System.String
Parameter Sets: Filter
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity

Specifies an Active Directory object by providing one of the following property values. The
identifier in parentheses is the LDAP display name for the attribute. The acceptable values for this
parameter are:

- A distinguished name

The cmdlet searches the default naming context or partition to find the object. If two or more
objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an
object instance.

```yaml
Type: Microsoft.ActiveDirectory.Management.ADClaimTransformPolicy
Parameter Sets: Identity
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LDAPFilter

Specifies a filter using the LDAP search filter syntax defined in RFC2254 to filter Active Directory
Domain Services objects.

```yaml
Type: System.String
Parameter Sets: LdapFilter
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Properties

Specifies the properties of the output object to get from the server. Use this parameter to get
properties that are not included in the default set.

Specify the properties to get as a comma separated list of names. To display
all of the properties that are set on the object, specify an asterisk (`*`) wildcard.

To specify an individual extended property, use the name of the property. For properties that are
not default or extended properties, you must specify the LDAP display name of the attribute.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Property

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server

Specifies the Active Directory Domain Services instance to connect to, by providing one of the
following values for a corresponding domain name or directory server. The service may be any of the
following: Active Directory Lightweight Domain Services, Active Directory Domain Services or Active
Directory snapshot instance.

Specify the Active Directory Domain Services instance in one of the following ways:

Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that
they are listed:

- By using the **Server** value from objects passed through the pipeline
- By using the server information associated with the Active Directory Domain Services Windows
  PowerShell provider drive, when the cmdlet runs in that drive
- By using the domain of the computer running Windows PowerShell

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

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADClaimTransformPolicy

A claim transform policy object is received by the **Identity** parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADClaimTransformPolicy

## NOTES

## RELATED LINKS

[New-ADClaimTransformPolicy](./New-ADClaimTransformPolicy.md)

[Remove-ADClaimTransformPolicy](./Remove-ADClaimTransformPolicy.md)

[Set-ADClaimTransformPolicy](./Set-ADClaimTransformPolicy.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)
