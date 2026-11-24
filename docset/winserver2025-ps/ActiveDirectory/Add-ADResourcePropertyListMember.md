---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/add-adresourcepropertylistmember?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-ADResourcePropertyListMember
---

# Add-ADResourcePropertyListMember

## SYNOPSIS
Adds one or more resource properties to a resource property list in Active Directory.

## SYNTAX

```
Add-ADResourcePropertyListMember [-WhatIf] [-Confirm] [-AuthType <ADAuthType>]
 [-Credential <PSCredential>] [-Identity] <ADResourcePropertyList>
 [-Members] <ADResourceProperty[]> [-PassThru] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Add-ADResourcePropertyListMember` cmdlet adds one or more resource properties to a resource
property list in Active Directory.

## EXAMPLES

### Example 1: Add members to a resource property list

```powershell
$params = @{
    Identity = 'Global Resource Property List'
    Members = 'Country', 'Authors'
}
Add-ADResourcePropertyListMember @params
```

This command adds the resource members named `Country` and `Authors` to the list named
`Global Resource Property List`.

### Example 2: Add members to a filtered resource property list

```powershell
Get-ADResourcePropertyList -Filter "Name -like 'Corporate*'" |
    Add-ADResourcePropertyListMember -Members Country, Authors
```

This command gets any resource property list that has a name that begins with `Corporate` and then
passes it to `Add-ADResourcePropertyListMember`, which then adds the resource properties `Country`
and `Authors` to it.

## PARAMETERS

### -AuthType

Specifies the authentication method to use. The acceptable values for this parameter are:

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

### -Identity

Specifies an Active Directory object by providing one of the following property values. The
identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the
attribute. The acceptable values for this parameter are:

- A distinguished name
- A GUID (**objectGUID**)

This parameter can also get this object through the pipeline or you can set this parameter to an
object instance.

```yaml
Type: Microsoft.ActiveDirectory.Management.ADResourcePropertyList
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Members

Specifies a set of **ADResourceProperty** objects in a comma-separated list to add to a resource
property list. To identify each object, use one of the following property values:

- Name
- Distinguished name
- GUID (**objectGUID**)

You can also provide objects to this parameter directly.

You cannot pass objects through the pipeline to this parameter.

```yaml
Type: Microsoft.ActiveDirectory.Management.ADResourceProperty[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru

Returns an object representing the item with which you're working. By default, this cmdlet doesn't
generate any output.

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

### -WhatIf

Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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

### None or Microsoft.ActiveDirectory.Management.ADClaimTypeList

An **ADClaimTypeList** object is received by the **Identity** parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADClaimTypeList

Returns the modified **ADClaimTypeList** object when the **PassThru** parameter is specified. By
default, this cmdlet does not generate any output.

## NOTES

- This cmdlet does not work with a read-only domain controller.
- This cmdlet does not work with an Active Directory snapshot.

## RELATED LINKS

[Remove-ADResourcePropertyListMember](./Remove-ADResourcePropertyListMember.md)
