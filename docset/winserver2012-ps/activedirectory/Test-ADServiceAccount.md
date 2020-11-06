---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
ms.assetid: 19072094-9595-4A07-894D-EA3B28EF8BA4
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Test-ADServiceAccount

## SYNOPSIS
Tests a managed service account from a computer.

## SYNTAX

```
Test-ADServiceAccount [-AuthType <ADAuthType>] [-Identity] <ADServiceAccount> [<CommonParameters>]
```

## DESCRIPTION
The Test-ADServiceAccount cmdlet tests a managed service account (MSA) from a local computer.

The Identity parameter specifies the Active Directory MSA account to test.
You can identify a MSA by its distinguished name (DN), GUID, security identifier (SID), or Security Accounts Manager (SAM) account name.
You can also set the parameter to a MSA object variable, such as $\<localMSA\> or pass a MSA object through the pipeline to the Identity parameter.
For example, you can use the Get-ADServiceAccount to get a MSA object and then pass that object through the pipeline to the Test-ADServiceAccount cmdlet.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Test-ADServiceAccount -Identity MSA1


True
```

Description

-----------

Tests that the specified service account ("MSA1") is ready for use (it is able be authenticated and access the domain using its currently configured credentials) from the local computer.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Test-ADServiceAccount -Identity MSA1


False

WARNING: Test failed for Managed Service Account MSA. If standalone Managed Service Account, the account is linked to another computer object in the Active Directory. If group Managed Service Account, either this computer does not have permission to use the group MSA or this computer does not support all the Kerberos encryption types required for the gMSA. See the MSA operational log for more information.
```

Description

-----------

Test results returned if MsaInfoCannotInstall

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Test-ADServiceAccount -Identity MSA1


False

WARNING: The Managed Service Account MSA is not linked with any computer object in the directory.
```

Description

-----------

Test returns MsaInfoCanInstall

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

### -Identity
Specifies an Active Directory managed service account object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.

Distinguished Name

Example:  CN=MyServiceMSA,CN=Europe,CN=Users,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Security Identifier (objectSid)

Example: S-1-5-21-3165297888-301567370-576410423-1103

SAM account name  (sAMAccountName)

Example: MyServiceMSA

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

This example shows how to set the parameter to a distinguished name.

-Identity  "CN=MyServiceMSA,CN=Europe,CN=Users,DC=corp,DC=contoso,DC=com"

This example shows how to set this parameter to a user object instance named "userInstance".

-Identity   $userInstance

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADServiceAccount
A managed service account object is received by the Identity parameter.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

