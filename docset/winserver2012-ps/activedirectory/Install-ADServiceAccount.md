---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
ms.assetid: 0B1E30A3-7E02-477C-ACA3-9F2A7C3C7552
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
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
The Install-ADServiceAccount cmdlet installs an existing Active Directory managed service account (MSA) on the computer on which the cmdlet is run.
This cmdlet verifies that the computer is eligible to host the MSA.
The cmdlet also makes the required changes locally so that the MSA password can be managed without requiring any user action.

The Identity parameter specifies the Active Directory MSA to install.
You can identify a MSA by its distinguished name Members (DN), GUID, security identifier (SID) or Security Accounts Manager (SAM) account name.
You can also set the parameter to a MSA object variable, such as $\<localServiceaccountObject\> or pass a MSA object through the pipeline to the Identity parameter.
For example, you can use Get-ADServiceAccount to get a MSA object and then pass the object through the pipeline to the Install-ADServiceAccount.

The AccountPassword parameter allows you to pass a SecureString that contains the password of  a standalone MSA and is ignored for group MSAs.
Alternatively you can use PromptForPassword switch parameter to be prompted for the standalone MSA password.
You need to enter the password of a standalone MSA if you want to install an account that you have pre-provisioned early on.
This is required when you are installing a standalone MSA on a server located on a segmented network (site) with no access to writable DCs but only RODCs (e.g.
perimeter network or DMZ).
In this case you should create the standalone MSA, link it with the appropriate computer account and assign a well-known password that needs to be passed when installing the standalone MSA on the server on the RODC-only site with no access to writable DCs.
If you pass both AccountPassword and PromptForPassword parameters the AccountPassword parameter takes precedence.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Install-ADServiceAccount -Identity 'SQL-HR-svc-01'
```

Description

-----------

Install a Managed Service Account with name 'SQL-HR-svc-01' on the local computer.
(If a Group Managed Service Account is used, the service account must have the PrincipalsAllowedToRetrieveManagedPassword property set.)

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>$a = Get-ADServiceAccount -Filter "Name -eq 'SQL-HR-svc-01'"
Install-ADServiceAccount $a
```

Description

-----------

Get a Managed Service Account with name 'SQL-HR-svc-01' from the default directory and install it on the local machine.
(If a Group Managed Service Account is used, the service account must have the PrincipalsAllowedToRetrieveManagedPassword property set.)

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Install-ADServiceAccount -Identity 'SQL-HR-svc-01' -PromptForPassword


Please enter the current password for 'CN=SQL-HR-svc-01,CN=Managed Service Accounts,DC=contoso,DC=com'
Password: *******
```

Description

-----------

Installs a standalone Managed Service Account with name 'SQL-HR-svc-01' in a RODC-only site with not access to writable DCs.
(If a Group Managed Service Account is used, the service account must have the PrincipalsAllowedToRetrieveManagedPassword property set.)

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>Install-ADServiceAccount -Identity 'SQL-HR-svc-01' -AccountPassword (ConvertTo-SecureString -AsPlainText "p@ssw0rd" -Force)
```

Description

-----------

Installs a standalone Managed Service Account with name 'SQL-HR-svc-01' in a RODC-only site with not access to writable DCs passing the account password as a secure string.
(If a Group Managed Service Account is used, the service account must have the PrincipalsAllowedToRetrieveManagedPassword property set.)

## PARAMETERS

### -AccountPassword
The AccountPassword SecureString parameter will allow you to inline pass-in the password of a standalone Managed Service Account (MSA) that you have pre-provisioned early on and is ignored for group MSAs.
This is required when you are installing a standalone MSA on a server located on a segmented network (site) with no access to writable DCs but only RODCs (e.g.
perimeter network or DMZ).
In this case you should create the standalone MSA, link it with the appropriate computer account and assign a well-known password that needs to be passed when installing the standalone MSA on the server on the RODC-only site with no access to writable DCs.
If you pass both AccountPassword and PromptForPassword parameters the AccountPassword parameter takes precedence.

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
Possible values for this parameter include:

Negotiate or 0

Basic or 1

The default authentication method is Negotiate.

A Secure Sockets Layer (SSL) connection is required for the Basic authentication method.

The following example shows how to set this parameter to Basic.

-AuthType Basic

```yaml
Type: ADAuthType
Parameter Sets: (All)
Aliases: 
Accepted values: Negotiate, Basic

Required: False
Position: Named
Default value: Microsoft.ActiveDirectory.Management.AuthType.Negotiate
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
Specifies an Active Directory account object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.

Distinguished Name

Example:  CN=WebAccount,CN=ManagedServiceAccounts,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Security Identifier (objectSid)

Example: S-1-5-21-3165297888-301567370-576410423-1103

SAM Account Name (sAMAccountName)

Example: WebAccount$

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

This example shows how to set the parameter to a distinguished name.

-Identity  "CN=WebAccount,CN=ManagedServiceAccounts,DC=corp,DC=contoso,DC=com"

This example shows how to set this parameter to an account object instance named "AccountInstance".

-Identity   $AccountInstance

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
The PromptForPassword switch parameter will allow you to enter the password of a standalone Managed Service Account (MSA) that you have pre-provisioned early on and ignored for group MSAs.
This is required when you are installing a standalone MSA on a server located on a segmented network (site) with no access to writable DCs but only RODCs (e.g.
perimeter network or DMZ).
In this case you should create the standalone MSA, link it with the appropriate computer account and assign a well-known password that needs to be passed when installing the standalone MSA on the server on the RODC-only site with no access to writable DCs.
If you pass both AccountPassword and PromptForPassword parameters the AccountPassword parameter takes precedence.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADServiceAccount
A managed service account object is received by the Identity parameter.

## OUTPUTS

### None

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

  To successfully install a service account, the service account should have the **-PrincipalsAllowedToRetrieveManagedPassword** parameter option set first by using either the New-ADServiceAccount or Set-ADServiceAccount cmdlet first.
Otherwise, installation will fail.

## RELATED LINKS

[Get-ADServiceAccount](./Get-ADServiceAccount.md)

[New-ADServiceAccount](./New-ADServiceAccount.md)

[Remove-ADServiceAccount](./Remove-ADServiceAccount.md)

[Reset-ADServiceAccountPassword](./Reset-ADServiceAccountPassword.md)

[Set-ADServiceAccount](./Set-ADServiceAccount.md)

[Uninstall-ADServiceAccount](./Uninstall-ADServiceAccount.md)

