---
description: Update the account activity for a user account.
external help file: Microsoft.IdentityServer.Management.dll-Help.xml
Module Name: adfs
ms.date: 10/27/2021
online version: https://docs.microsoft.com/powershell/module/adfs/set-adfsaccountactivity?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-AdfsAccountActivity
---

# Set-AdfsAccountActivity

## SYNOPSIS
Update the account activity for a user account.

## SYNTAX

### Identity (Default)
```
Set-AdfsAccountActivity [-Identity] <String> [[-AdditionalFamiliarIps] <String[]>] [-Clear] [-Force]
 [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Upn
```
Set-AdfsAccountActivity -UserPrincipalName <String> [[-AdditionalFamiliarIps] <String[]>] [-Clear] [-Force]
 [-Server <String>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-ADFSAccountActivity** cmdlet updates the account activity for a user account. This can be
used to add new familiar locations or erase state for any account. The familiar IP list has a
maximum of 20 entries, if this is exceeded, the oldest IP in the list will be removed.

The cmdlet automatically connects to the node in the farm that holds the master role. This behavior
can be overridden by passing the **-Server** parameter.

## EXAMPLES

### Example 1: Add a new familiar location for a user account
```powershell
PS> Set-ADFSAccountActivity user@contoso.com -AdditionalFamiliarIps "1.2.3.4"
```

Add a new familiar location **1.2.3.4** for the user account **user@contoso.com**.

## PARAMETERS

### -AdditionalFamiliarIps
Familiar location IP address to add. The familiar IP list has a
maximum of 20 entries, if this is exceeded, the oldest IP in the list will be removed.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Clear
Clears the account activity for the specified user account.

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

### -Force
Forces the command to run without asking for user confirmation.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Identity
Specifies an Active Directory group object by providing one of the following values.
The identifier in parentheses is the LDAP display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID) 
- A security identifier (objectSid) 
- A Security Account Manager account name (sAMAccountName)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an
object instance.

```yaml
Type: String
Parameter Sets: Identity
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Server
Specifies the Active Directory Domain Services instance to connect to, by providing one of the
following values for a corresponding domain name or directory server.

Domain name values:
- Fully qualified domain name. For example, corp.contoso.com
- NetBIOS name. For example, CORP

Directory server values:
- Fully qualified directory server name. For example, corp-DC12.corp.contoso.com
- NetBIOS name. For example, corp-DC12
- Fully qualified directory server name and port. For example: corp-DC12.corp.contoso.com:3268

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserPrincipalName
Specifies a user principal name (UPN) in the format `<user>@<DNS-domain-name>`. A UPN is a friendly
name assigned by an administrator that is shorter than the LDAP distinguished name used by the
system and easier to remember. The UPN is independent of the user object's distinguished name, so a
user object can be moved or renamed without affecting the user logon name. When logging on using a
UPN, users don't have to choose a domain from a list on the logon dialog box.

```yaml
Type: String
Parameter Sets: Upn
Aliases:

Required: True
Position: Named
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.String[]

### System.Management.Automation.SwitchParameter

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
