---
author: Kateyanne
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
manager: dansimp
Module Name: ActiveDirectory
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/activedirectory/uninstall-adserviceaccount?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Uninstall-ADServiceAccount

## SYNOPSIS
Uninstalls an Active Directory managed service account from a computer or removes a cached group managed service account from a computer.

## SYNTAX

```
Uninstall-ADServiceAccount [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-ForceRemoveLocal]
 [-Identity] <ADServiceAccount> [<CommonParameters>]
```

## DESCRIPTION
The Uninstall-ADServiceAccount cmdlet removes an Active Directory standalone managed service account (MSA) on the computer on which the cmdlet is run.
For group MSAs, the cmdlet removes the group MSA from the cache, however, if a service is still using the group MSA and the host has permission to retrieve the password a new cache entry will be created.
The specified MSA must be installed on the computer.

The Identity parameter specifies the Active Directory MSA to uninstall.
You can identify a MSA by its distinguished name (DN), GUID, security identifier (SID), or Security Accounts Manager (SAM) account name.
You can also set the parameter to a MSA object variable, such as $\<localServiceAccountObject\> or pass a MSA object through the pipeline to the Identity parameter.
For example, you can use the Get-ADServiceAccount to get a MSA object and then pass that object through the pipeline to the Uninstall-ADServiceAccount cmdlet.

For standalone MSA, the ForceRemoveLocal switch parameter will allow you to remove the account from the local LSA without failing the command if an access to a writable DC is not possible.
This is required if you are uninstalling the standalone MSA from a server that is placed in a segmented network (i.e.
perimeter network) with access only to an RODC.
If you pass this parameter and the server has access to a writable DC the standalone MSA will be un-linked from the computer account in the directory as well.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Uninstall-ADServiceAccount -Identity SQL-SRV1
```

Description

-----------

Uninstall the managed service account SQL-SRV1 from the local machine.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Uninstall-ADServiceAccount sql-hr-01 -ForceRemoveLocal
```

Description

-----------

Uninstall a standalone Managed Service Account from a server located in a RODC-only site with no access to writable DCs such as a perimeter network.

## PARAMETERS

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

### -ForceRemoveLocal
The ForceRemoveLocal switch parameter will allow you to remove the account from the local LSA without failing the command if an access to a writable DC is not possible.
This is required if you are uninstalling the MSA from a server that is placed in a segmented network (i.e.
perimeter network) with access only to an RODC.
If you pass this parameter and the server has access to a writable DC the account will be un-linked from the computer account in the directory as well.

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

### None or Microsoft.ActiveDirectory.Management.ADServiceAccount
A managed service account object is received by the Identity parameter.
A switch parameter with name ForceRemoveLocal is provided to un-install standalone MSAs on a RODC only site.

## OUTPUTS

### None

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADServiceAccount](./Get-ADServiceAccount.md)

[Install-ADServiceAccount](./Install-ADServiceAccount.md)

[New-ADServiceAccount](./New-ADServiceAccount.md)

[Remove-ADServiceAccount](./Remove-ADServiceAccount.md)

[Set-ADServiceAccount](./Set-ADServiceAccount.md)

