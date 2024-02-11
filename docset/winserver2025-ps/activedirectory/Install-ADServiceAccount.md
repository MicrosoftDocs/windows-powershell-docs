---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/install-adserviceaccount?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Install-ADServiceAccount
---

# Install-ADServiceAccount

## SYNOPSIS
Installs an Active Directory managed service account on a computer or caches a group managed service account on a computer.

## SYNTAX

```
Install-ADServiceAccount [-WhatIf] [-Confirm] [-AccountPassword <SecureString>] [-AuthType <ADAuthType>]
 [-Force] [-Identity] <ADServiceAccount> [-PromptForPassword] [<CommonParameters>]
```

## DESCRIPTION
The **Install-ADServiceAccount** cmdlet installs an existing Active Directory managed service account on the computer on which the cmdlet is run.
This cmdlet verifies that the computer is eligible to host the managed service account.
The cmdlet also makes the required changes locally so that the managed service account password can be managed without requiring any user action.

The *Identity* parameter specifies the Active Directory managed service account to install.
You can identify a managed service account by its distinguished name, GUID, security identifier (SID), or security accounts manager (SAM) account name.
You can also set the parameter to a managed service account object variable, such as `$<localServiceAccountObject>` or pass a managed service account object through the pipeline to the *Identity* parameter.
For example, you can use Get-ADServiceAccount to get a managed service account object and then pass the object through the pipeline to the Install-ADServiceAccount.

The *AccountPassword* parameter allows you to pass a secure string that contains the password of a standalone managed service account and is ignored for group managed service accounts.
Alternatively, you can use *PromptForPassword* parameter to prompt for the standalone managed service account password.
You must enter the password of a standalone managed service account if you want to install an account that you have provisioned.
This is required when you are installing a standalone managed service account on a server located on a segmented network (site) with read-only domain controllers (for example, a perimeter network or DMZ).
In this case you should create the standalone managed service account, link it with the appropriate computer account, and assign a well-known password that must be passed when installing the standalone managed service account on the server on the read-only domain controller site.
If you pass both *AccountPassword* and *PromptForPassword* parameters, the *AccountPassword* parameter takes precedence.

## EXAMPLES

### Example 1: Install a managed service account on the local computer
```
PS C:\> Install-ADServiceAccount -Identity 'SQL-HR-svc-01'
```

This command installs a managed service account with name SQL-HR-svc-01 on the local computer.
If a group managed service account is used, the service account must have the **PrincipalsAllowedToRetrieveManagedPassword** property set.

### Example 2: Get a managed service account and install it on the local computer
```
PS C:\> $Account = Get-ADServiceAccount -Filter "Name -eq 'SQL-HR-svc-01'"
PS C:\> Install-ADServiceAccount $Account
```

This command gets a managed service account with name SQL-HR-svc-01 from the default directory and installs it on the local computer.
If a group managed service account is used, the service account must have the **PrincipalsAllowedToRetrieveManagedPassword** property set.

### Example 3: Install a standalone managed service account for a read-only domain controller site
```
PS C:\> Install-ADServiceAccount -Identity 'SQL-HR-svc-01' -PromptForPassword
Please enter the current password for 'CN=SQL-HR-svc-01,CN=Managed Service Accounts,DC=contoso,DC=com'
Password: *******
```

This command installs a standalone managed service account identified as SQL-HR-svc-01 in a read-only domain controller site.
If a group managed service account is used, the service account must have the **PrincipalsAllowedToRetrieveManagedPassword** property set.

### Example 4: Install a standalone managed service account with the specified password
```
PS C:\> Install-ADServiceAccount -Identity 'SQL-HR-svc-01' -AccountPassword (ConvertTo-SecureString -AsPlainText "p@ssw0rd" -Force)
```

This command installs a standalone managed service account with the name SQL-HR-svc-01 in a read-only domain controller site, and passes the account password as a secure string.
If a group managed service account is used, the service account must have the **PrincipalsAllowedToRetrieveManagedPassword** property set.

## PARAMETERS

### -AccountPassword
Specifies the account password as a secure string.
This parameter enables you to specify the password of a standalone managed service account that you have provisioned and is ignored for group managed service accounts.
This is required when you are installing a standalone managed service account on a server located on a segmented network (site) with read-only domain controllers (for example, a perimeter network or DMZ).
In this case you should create the standalone managed service account, link it with the appropriate computer account, and assign a well-known password that must be passed when installing the standalone managed service account on the server on the read-only domain controller site with no access to writable domain controllers.
If you pass both *AccountPassword* and *PromptForPassword* parameters, the *AccountPassword* parameter takes precedence.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AuthType
Specifies the authentication method to use.
Possible values for this parameter include: The acceptable values for this parameter are:

- Negotiate or 0
- Basic or 1

The default authentication method is Negotiate.

A Secure Sockets Layer (SSL) connection is required for the Basic authentication method.

```yaml
Type: ADAuthType
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Forces installation of the service account.

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

### -Identity
Specifies an Active Directory group object by providing one of the following values.
The identifier in parentheses is the LDAP display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)
- A security identifier (objectSid)
- A security accounts manager account name (sAMAccountName)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

```yaml
Type: ADServiceAccount
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PromptForPassword
Indicates that you can enter the password of a standalone managed service account that you have pre-provisioned and ignored for group managed service accounts.
This is required when you are installing a standalone managed service account on a server located on a segmented network (site) with no access to writable domain controllers, but only read-only domain controllers (RODCs) (e.g.
perimeter network or DMZ).
In this case you should create the standalone managed service account, link it with the appropriate computer account, and assign a well-known password that must be passed when installing the standalone managed service account on the server on the RODC-only site.
If you pass both *AccountPassword* and *PromptForPassword* parameters the *AccountPassword* parameter takes precedence.

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

### Microsoft.ActiveDirectory.Management.ADServiceAccount
A managed service account object is received by the *Identity* parameter.

## OUTPUTS

### None

## NOTES
* This cmdlet does not work with Active Directory Lightweight Directory Services (AD LDS).
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.
* This cmdlet must be run from an elevated PowerShell session.
* To successfully install a managed service account, the service account should have the *PrincipalsAllowedToRetrieveManagedPassword* parameter option set first by using either the New-ADServiceAccount or Set-ADServiceAccount cmdlet first. Otherwise, installation will fail.

## RELATED LINKS

[Get-ADServiceAccount](./Get-ADServiceAccount.md)

[New-ADServiceAccount](./New-ADServiceAccount.md)

[Remove-ADServiceAccount](./Remove-ADServiceAccount.md)

[Reset-ADServiceAccountPassword](./Reset-ADServiceAccountPassword.md)

[Set-ADServiceAccount](./Set-ADServiceAccount.md)

[Uninstall-ADServiceAccount](./Uninstall-ADServiceAccount.md)
