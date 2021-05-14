---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://docs.microsoft.com/powershell/module/activedirectory/get-adfinegrainedpasswordpolicysubject?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ADFineGrainedPasswordPolicySubject

## SYNOPSIS
Gets the users and groups to which a fine grained password policy is applied.

## SYNTAX

```
Get-ADFineGrainedPasswordPolicySubject [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADFineGrainedPasswordPolicy> [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The Get- ADFineGrainedPasswordPolicySubject cmdlet gets users and groups that are subject to a fine grained password policy.

The Identity parameter specifies the fine grained password policy.
You can identify a fine grained password policy by its distinguished name, GUID or name.
You can also set the Identity parameter to a fine grained password policy object variable, such as $\<localPasswordPolicyObject\>, or pass a fine grained password policy object through the pipeline to the Identity parameter.
For example, you can use the Get-ADFineGrainedPasswordPolicy cmdlet to retrieve a fine grained password policy object and then pass the object through the pipeline to the Get- ADFineGrainedPasswordPolicySubject cmdlet.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-ADFineGrainedPasswordPolicySubject -Identity DomainUsersPSO | FT Name,ObjectClass,DistinguishedName -AutoSize


Name         ObjectClass DistinguishedName
----         ----------- -----------------
Domain Users group       CN=Domain Users,CN=Users,DC=FABRIKAM,DC=COM
```

Description

-----------

Get the Fine Grained Password Policy subject of the Password Policy named 'DomainUsersPSO'.

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

### -Credential
Specifies the user account credentials to use to perform this task.
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as "User1" or "Domain01\User01" or you can specify a PSCredential object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a PSCredential object by using a script or by using the Get-Credential cmdlet.
You can then set the Credential parameter to the PSCredential object The following example shows how to create credentials.

$AdminCredentials = Get-Credential "Domain01\User01"

The following shows how to set the Credential parameter to these credentials.

-Credential $AdminCredentials

If the acting credentials do not have directory-level permission to perform the task, Active Directory PowerShell returns a terminating error.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
Specifies an Active Directory fine-grained password policy object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.

Distinguished Name (distinguishedName)

Example: CN=Strict Password Policy,CN=Password Settings Container,CN=System,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Name (name)

Example: PasswordPolicyLevel1

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to a fine-grained password policy object instance.

This example shows how to set the parameter to a distinguished name.

-Identity "CN=Strict Password Policy,CN=Password Settings Container,CN=System,DC=corp,DC=contoso,DC=com"

This example shows how to set this parameter to a fine-grained password policy object instance named "fineGrainedPasswordPolicyInstance".

-Identity $fineGrainedPasswordPolicyInstance

```yaml
Type: ADFineGrainedPasswordPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Server
Specifies the Active Directory Domain Services instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following:  Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory Snapshot instance.

Domain name values:

Fully qualified domain name

Examples: corp.contoso.com

NetBIOS name

Example: CORP

Directory server values:

Fully qualified directory server name

Example: corp-DC12.corp.contoso.com

NetBIOS name

Example: corp-DC12

Fully qualified directory server name and port

Example: corp-DC12.corp.contoso.com:3268

The default value for the Server parameter is determined by one of the following methods in the order that they are listed:

-By using Server value from objects passed through the pipeline.

-By using the server information associated with the Active Directory PowerShell provider drive, when running under that drive.

-By using the domain of the computer running Windows PowerShell.

The following example shows how to specify a full qualified domain name as the parameter value.

-Server "corp.contoso.com"

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy
A fine grained password policy object is received by the Identity parameter.

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADPrincipal
Returns principal objects that represent the users and groups to which the fine grained password policy is applied.

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work when targeting a snapshot using the Server parameter.

## RELATED LINKS

[Get-ADFineGrainedPasswordPolicy](./Get-ADFineGrainedPasswordPolicy.md)

