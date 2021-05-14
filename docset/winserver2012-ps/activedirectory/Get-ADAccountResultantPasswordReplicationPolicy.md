---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://docs.microsoft.com/powershell/module/activedirectory/get-adaccountresultantpasswordreplicationpolicy?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-ADAccountResultantPasswordReplicationPolicy

## SYNOPSIS
Gets the resultant password replication policy for an Active Directory account.

## SYNTAX

```
Get-ADAccountResultantPasswordReplicationPolicy [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-DomainController] <ADDomainController> [-Identity] <ADAccount> [-Partition <String>] [-Server <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The Get-ADAccountResultantPasswordReplicationPolicy gets the resultant password replication policy for a user, computer or service account on the specified read-only domain controller.

The policy will be one of the following values:

Allow or 1

DenyExplicit or 0

DenyImplicit or 2

Unknown or -1

The Identity parameter specifies the account.
You can identify a user, computer, or service account object by its distinguished name (DN), GUID, security identifier (SID) or Security Account Manager (SAM) account name.
You can also set the Identity parameter to an account object variable, such as $\<localAccountObject\>, or pass an account object through the pipeline to the Identity parameter.
For example, you can use the Get-ADUser, Get-ADComputer, Get-ADServiceAccount or Search-ADAccount cmdlets to retrieve an account object and then pass the object through the pipeline to the Get-ADAccountResultantPasswordReplicationPolicy cmdlet.

The DomainController parameter specifies the read-only domain controller.
You can identify a domain controller by its IPV4Address, global IPV6Address, or DNS host name.
You can also identify a domain controller by the Distinguished Name (DN) of the NTDS settings object or the server object, the GUID of the NTDS settings object or the server object under the configuration partition, or the DN, SamAccountName, GUID, SID of the computer object that represents the domain controller.
You can also set the DomainController parameter to a domain controller object variable, such as $\<localDomainControllerObject\>.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Get-ADAccountResultantPasswordReplicationPolicy BradSu "FABRIKAM-RODC1"
```

Description

-----------

Get the resultant password replication policy on the domain for a given user account.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Get-ADAccountResultantPasswordReplicationPolicy BobKe -DomainController "FABRIKAM-RODC1"
```

Description

-----------

Get the resultant password replication policy on a specific domain controller for a given user account.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Get-ADAccountResultantPasswordReplicationPolicy "CN=Jordao Moreno,OU=Europe,OU=Sales,OU=UserAccounts,DC=FABRIKAM,DC=COM" "FABRIKAM-RODC1"
```

Description

-----------

Get the resultant password replication policy on a specific domain controller for a given user account DN.

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

### -DomainController
Specifies a read-only domain controller (RODC).
The cmdlet returns the password replication policy of the account for this RODC.
You can identify the domain controller by providing one of the following values.

GUID (objectGUID)

Example: 768c44de-f72d-66e0-8a88-0523ca495f20

IPV4Address

Example:157.59.132.61

Global IPV6Address

Example: 2001:4898:0:fff:200:5efe:157.59.132.61

DNS Host Name (dNSHostName)

Example: corp-DC01.corp.contoso.com

Name of the server object

Example: corp-DC01$

Distinguished Name (DN) of the NTDS Settings object

Example: CN=NTDS Settings,CN=CORP-DC12,CN=Servers,CN=NA-CAN-QBC,CN=Sites,CN=Configuration,DC=corp,DC=contoso

Distinguished Name (DN) of the server object that represents the domain controller

Example: CN=CORP-DC12,CN=Servers,CN=NA-CAN-QBC,CN=Sites,CN=Configuration,DC=corp,DC=contoso,DC=com

GUID of NTDS settings object under the configuration partition

Example: 68adaf21-e28d-6012-bca8-320d93450ab0

GUID of server object under the configuration partition

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Distinguished Name (DN) of the computer object that represents the domain controller.

Example: CN=CORP-DC12,OU=Domain Controllers,DC=corp,DC=contoso,DC=com

Note: The identifier in parentheses is the LDAP display name for the attribute.

The following example shows how to set this parameter to the DNS host name of a domain controller.

-DomainController "corp-DC01.corp.contoso.com"

```yaml
Type: ADDomainController
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
Specifies an Active Directory account object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.

Distinguished Name

Example: CN=SaraDavis ,CN=Users,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Security Identifier (objectSid)

Example: S-1-5-21-3165297888-301567370-576410423-1103

SAM Account Name (sAMAccountName)

Example: saradavis

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an account object instance.

Derived types such as the following are also accepted:

Microsoft.ActiveDirectory.Management.ADUser

Microsoft.ActiveDirectory.Management.ADComputer

Microsoft.ActiveDirectory.Management.ADServiceAccount

This example shows how to set the parameter to a distinguished name.

-Identity "CN=saradavis,CN=Users,DC=corp,DC=contoso,DC=com"

This example shows how to set this parameter to an account object instance named "accountInstance".

-Identity $accountInstance

```yaml
Type: ADAccount
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Partition
Specifies the distinguished name of an Active Directory partition.
The distinguished name must be one of the naming contexts on the current directory server.
The cmdlet searches this partition to find the object defined by the Identity parameter.

The following two examples show how to specify a value for this parameter.

-Partition "CN=Configuration,DC=EUROPE,DC=TEST,DC=CONTOSO,DC=COM"

-Partition "CN=Schema,CN=Configuration,DC=EUROPE,DC=TEST,DC=CONTOSO,DC=COM"

In many cases, a default value will be used for the Partition parameter if no value is specified. 
The rules for determining the default value are given below. 
Note that rules listed first are evaluated first and once a default value can be determined, no further rules will be evaluated.

In AD DS environments, a default value for Partition will be set in the following cases:  - If the Identity parameter is set to a distinguished name, the default value of Partition is automatically generated from this distinguished name.

- If running cmdlets from an Active Directory provider drive, the default value of Partition is automatically generated from the current path in the drive.
- If none of the previous cases apply, the default value of Partition will be set to the default partition or naming context of the target domain.

In AD LDS environments, a default value for Partition will be set in the following cases:

- If the Identity parameter is set to a distinguished name, the default value of Partition is automatically generated from this distinguished name.
- If running cmdlets from an Active Directory provider drive, the default value of Partition is automatically generated from the current path in the drive.
- If the target AD LDS instance has a default naming context, the default value of Partition will be set to the default naming context.  To specify a default naming context for an AD LDS environment, set the msDS-defaultNamingContext property of the Active Directory directory service agent (DSA) object (nTDSDSA) for the AD LDS instance.
- If none of the previous cases apply, the Partition parameter will not take any default value.

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

### Microsoft.ActiveDirectory.Management.ADAccount
An account object is received by the Identity parameter.

Derived types, such as the following are also accepted:

Microsoft.ActiveDirectory.Management.ADUser

Microsoft.ActiveDirectory.Management.ADComputer

Microsoft.ActiveDirectory.Management.ADServiceAccount

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADResultantPasswordReplicationPolicy
Returns an ADResultantPasswordReplicationPolicy enum value that represents the resultant password replication policy for an account on the specified domain controller.

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work with an Active Directory Snapshot.

## RELATED LINKS

[Get-ADComputer](./Get-ADComputer.md)

[Get-ADServiceAccount](./Get-ADServiceAccount.md)

[Get-ADUser](./Get-ADUser.md)

[Search-ADAccount](./Search-ADAccount.md)

