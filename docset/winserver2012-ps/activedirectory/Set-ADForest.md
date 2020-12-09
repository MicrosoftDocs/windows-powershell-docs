---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
ms.assetid: 9982B2C1-685B-4039-9E5C-C00F93FB928D
manager: dansimp
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Set-ADForest

## SYNOPSIS
Modifies an Active Directory forest.

## SYNTAX

```
Set-ADForest [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Identity] <ADForest>
 [-PassThru] [-Server <String>] [-SPNSuffixes <Hashtable>] [-UPNSuffixes <Hashtable>] [<CommonParameters>]
```

## DESCRIPTION
The Set-ADForest cmdlet modifies the properties of an Active Directory forest.
You can modify commonly used property values by using the cmdlet parameters.
Property values that are not associated with cmdlet parameters can be modified by using the Add, Replace, Clear and Remove parameters.

The Identity parameter specifies the Active Directory forest to modify.
You can identify a forest by its fully qualified domain name (FQDN), GUID, DNS host name, or NetBIOS name.
You can also set the Identity parameter to an object variable such as $\<localADForestObject\>, or you can pass an object through the pipeline to the Identity parameter.
For example, you can use the Get-ADForest cmdlet to retrieve a forest object and then pass the object through the pipeline to the Set-ADForest cmdlet.

The Instance parameter provides a way to update a forest object by applying the changes made to a copy of the object.
When you set the Instance parameter to a copy of an Active Directory forest object that has been modified, the Set-ADForest cmdlet makes the same changes to the original forest object.
To get a copy of the object to modify, use the Get-ADForest object.
The Identity parameter is not allowed when you use the Instance parameter.
For more information about the Instance parameter, see the Instance parameter description.

The following examples show how to modify the UPNSuffixes property of a forest object by using three methods:

-By specifying the Identity and the UPNSuffixes parameters

-By passing a forest object through the pipeline and specifying the UPNSuffixes parameter

-By specifying the Instance parameter.

Method 1: Modify the UPNSuffixes property for the fabrikam.com forest by using the Identity and UPNSuffixes parameters.

Set-ADForest -Identity fabrikam.com -UPNSuffixes @{replace="fabrikam.com","fabrikam","corp.fabrikam.com"}

Method 2: Modify the UPNSuffixes property for the fabrikam.com forest by passing the fabrikam.com forest through the pipeline and specifying the UPNSuffixes parameter.

Get-ADForest -Identity fabrikam.com | Set-ADForest -UPNSuffixes @{replace="fabrikam.com","fabrikam","corp.fabrikam.com"}

Method 3: Modify the UPNSuffixes property for the fabrikam.com forest by using the Windows PowerShell command line to modify a local instance of the fabrikam.com forest.
Then set the Instance parameter to the local instance.

$forest = Get-ADForest -Identity fabrikam.com

$forest.UPNSuffixes = "fabrikam.com","fabrikam","corp.fabrikam.com"

Set-ADForest -Instance $forest.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Set-ADForest -Identity fabrikam.com -UPNSuffixes @{replace="fabrikam.com","fabrikam","corp.fabrikam.com"}
```

Description

-----------

Set the UPNSuffixes property on the fabrikam.com forest.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Set-ADForest -Identity fabrikam.com -SPNSuffixes @{add="corp.fabrikam.com"}
```

Description

-----------

Add corp.fabrikam.com to the SPNSuffixes property on the forest fabrikam.com

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Get-ADForest | Set-ADForest -SPNSuffixes @{Add="corp.fabrikam.com";Remove="fabrikam"}
```

Description

-----------

Get the forest of the current logged on user and update the SPNSuffixes property.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>Get-ADForest | Set-ADForest -UPNSuffixes $null
```

Description

-----------

Get the forest of the current logged on user and clear the UPNSuffixes property.

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
Specifies an Active Directory forest object by providing one of the following attribute values.
The identifier in parentheses is the LDAP display name for the attribute.

Fully qualified domain name

Example: corp.contoso.com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

DNS host name

Example: dnsServer.corp.contoso.com

NetBIOS name

Example: corp

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to a forest object instance.

This example shows how to set the parameter to a fully qualified domain name.

-Identity "corp.contoso.com"

This example shows how to set this parameter to a forest object instance named "forestInstance".

-Identity $forestInstance

```yaml
Type: ADForest
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### -SPNSuffixes
Modifies the list of service principal name (SPN) suffixes of the forest.
This parameter sets the multi-valued msDS-SPNSuffixes property of the cross-reference container.
This parameter uses the following syntax to add remove, replace, or clear SPN suffix values.

Syntax:

To add values:

-SPNSuffixes @{Add=value1,value2,...}

To remove values:

-SPNSuffixes @{Remove=value3,value4,...}

To replace values:

-SPNSuffixes @{Replace=value1,value2,...}

To clear all values:

-SPNSuffixes $null

You can specify more than one change by using a list separated by semicolons.
For example, use the following syntax to add and remove SPN suffix values

@{Add=value1,value2,...};@{Remove=value3,value4,...}

The operators will be applied in the following sequence:

..Remove

..Add

..Replace

The following example shows how to add and remove SPNSuffixes for a forest.

-@{Add="ContosoEurope", "ContosoAsia"};@{Remove="Contoso"}

```yaml
Type: Hashtable
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

-By using the domain of the computer running Powershell.

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

### -UPNSuffixes
Modifies the list of user principal name (UPN) suffixes of the forest.
This parameter sets the multi-valued msDS-UPNSuffixes property of the cross-reference container.
This parameter uses the following syntax to add remove, replace, or clear UPN suffix values.

Syntax:

To add values:

-UPNSuffixes  @{Add=value1,value2,...}

To remove values:

-UPNSuffixes @{Remove=value3,value4,...}

To replace values:

-UPNSuffixes @{Replace=value1,value2,...}

To clear all values:

-UPNSuffixes $null

You can specify more than one change by using a list separated by semicolons.
For example, use the following syntax to add and remove UPN suffix values

@{Add=value1,value2,...};@{Remove=value3,value4,...}

The operators will be applied in the following sequence:

..Remove

..Add

..Replace

The following example shows how to add and remove UPN suffixes for a forest.

-UPNSuffixes @{Add="Fabrikam.Com", "Corp.Fabrikam.Com"}; @{Remove="NA.Fabrikam.Com","Europe.Fabrikam.Com"}

```yaml
Type: Hashtable
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

### None or Microsoft.ActiveDirectory.Management.ADForest
A forest object is received by the Identity parameter.

A forest object that was retrieved by using the Get-ADForest cmdlet and then modified is received by the Instance parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADForest
Returns the modified forest object when the PassThru parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with AD LDS.

  This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADForest](./Get-ADForest.md)

[Set-ADForestMode](./Set-ADForestMode.md)

