---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://learn.microsoft.com/powershell/module/activedirectory/add-adcomputerserviceaccount?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-ADComputerServiceAccount

## SYNOPSIS
Adds one or more service accounts to an Active Directory computer.

## SYNTAX

```
Add-ADComputerServiceAccount [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADComputer> [-Partition <String>] [-PassThru] [-Server <String>]
 [-ServiceAccount] <ADServiceAccount[]> [<CommonParameters>]
```

## DESCRIPTION
The Add-ADComputerServiceAccount cmdlet adds one or more computer service accounts to an Active Directory computer.

The Computer parameter specifies the Active Directory computer that will host the new service accounts.
You can identify a computer by its distinguished name (DN), GUID, security identifier (SID) or Security Accounts Manager (SAM) account name.
You can also set the Computer parameter to a computer object variable, such as $\<localComputerobject\>, or pass a computer object through the pipeline to the Computer parameter.
For example, you can use the Get-ADComputer cmdlet to retrieve a computer object and then pass the object through the pipeline to the Add-ADComputerServiceAccount cmdlet.

The ServiceAccount parameter specifies the service accounts to add.
You can identify a service account by its distinguished name (DN), GUID, Security Identifier (SID) or Security Accounts Manager (SAM) account name.
You can also specify service account object variables, such as $\<localServiceAccountObject\>.
If you are specifying more than one account, use a comma-separated list.

Note: Adding a service account is a different operation than installing the service account locally.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Add-ADComputerServiceAccount -Computer ComputerAcct1 -serviceAccount SvcAcct1
```

Description

-----------

Add the service account 'SvcAcct1' to a Computer Account 'ComputerAcct1'

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Add-ADComputerServiceAccount  -Computer ComputerAcct1 -serviceAccount SvcAcct1,SvcAcct2
```

Description

-----------

Add 2 service accounts 'SvcAcct1,SvcAcct2' to a Computer Account 'ComputerAcct1'.

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
Specifies an Active Directory computer object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.

Distinguished Name

Example: CN=SaraDavisDesktop,CN=Europe,CN=Users,DC=corp,DC=contoso,DC=com

GUID  (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Security Identifier (objectSid)

Example: S-1-5-21-3165297888-301567370-576410423-1103

Security Accounts Manager Account Name (sAMAccountName)

Example: SaraDavisDesktop

The cmdlet searches the default naming context or partition to find the object.
If the identifier given is a DN, the partition to search will be computed from that DN.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to a computer object instance.

This example shows how to set the parameter to a distinguished name.

-Identity  "CN=saraDavisDesktop,CN=Europe,CN=Users,DC=corp,DC=contoso,DC=com"

This example shows how to set this parameter to a computer object instance named "computerInstance".

-Identity   $computerInstance

```yaml
Type: ADComputer
Parameter Sets: (All)
Aliases: Computer

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

### -PassThru
Returns the new or modified object.
By default (i.e.
if -PassThru is not specified), this cmdlet does not generate any output.

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

-By using the domain of the computer running Windows Powershell.

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

### -ServiceAccount
Specifies one or more Active Directory service accounts.
You can identify a service account by using one of the following property values:

Distinguished Name

Example: CN=serviceadmin,CN=Europe,CN=Users,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

Security Identifier (objectSid)

Example: S-1-5-21-3165297888-301567370-576410423-1103

SAM Account Name (sAMAccountName)

Example: serviceadmin

The following example shows how to specify a service account for this parameter using the SAM Account Name.

-ServiceAccount "serviceAdminEurope"

```yaml
Type: ADServiceAccount[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

### Microsoft.ActiveDirectory.Management.ADComputer
A computer object is received by the Computer parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADComputer
Returns the modified computer object when the PassThru parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work with a read-only domain controller.

  This cmdlet does not work when targeting a snapshot using the Server parameter.

## RELATED LINKS

[Get-ADComputer](./Get-ADComputer.md)

[Get-ADComputerServiceAccount](./Get-ADComputerServiceAccount.md)

[Remove-ADComputerServiceAccount](./Remove-ADComputerServiceAccount.md)

