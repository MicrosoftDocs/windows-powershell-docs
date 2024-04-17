---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-adforest?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ADForest
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
The **Set-ADForest** cmdlet modifies the properties of an Active Directory forest.
You can modify commonly used property values by using the cmdlet parameters.
Property values that are not associated with cmdlet parameters can be modified by using the *Add*, *Replace*, *Clear*, and *Remove* parameters.

The *Identity* parameter specifies the Active Directory forest to modify.
You can identify a forest by its fully qualified domain name (FQDN), GUID, DNS host name, or NetBIOS name.
You can also set the *Identity* parameter to an object variable such as `$<localADForestObject>`, or you can pass an object through the pipeline to the *Identity* parameter.
For example, you can use the **Get-ADForest** cmdlet to retrieve a forest object and then pass the object through the pipeline to the **Set-ADForest** cmdlet.

The *Instance* parameter provides a way to update a forest object by applying the changes made to a copy of the object.
When you set the *Instance* parameter to a copy of an Active Directory forest object that has been modified, the **Set-ADForest** cmdlet makes the same changes to the original forest object.
To get a copy of the object to modify, use the **Get-ADForest** object.
The *Identity* parameter is not allowed when you use the *Instance* parameter.
For more information about the *Instance* parameter, see the *Instance* parameter description.

## EXAMPLES

### Example 1: Update a property for a forest
```
PS C:\> Set-ADForest -Identity fabrikam.com -UPNSuffixes @{replace="fabrikam.com","fabrikam","corp.fabrikam.com"}
```

This command sets the **UPNSuffixes** property for the fabrikam.com forest.

### Example 2: Add a value to a forest property
```
PS C:\> Set-ADForest -Identity fabrikam.com -SPNSuffixes @{add="corp.fabrikam.com"}
```

This command adds corp.fabrikam.com to the **SPNSuffixes** property on the forest fabrikam.com.

### Example 3: Update a property for a forest
```
PS C:\> Get-ADForest | Set-ADForest -SPNSuffixes @{Add="corp.fabrikam.com";Remove="fabrikam"}
```

This command gets the forest of the current logged on user and updates the **SPNSuffixes** property.

### Example 4: Clear a property for a forest
```
PS C:\> Get-ADForest | Set-ADForest -UPNSuffixes $Null
```

This command gets the forest of the current logged on user and clears the **UPNSuffixes** property.

### Example 5: Update a property for a local forest
```
PS C:\> $Forest = Get-ADForest -Identity fabrikam.com
PS C:\> $Forest.UPNSuffixes = "fabrikam.com","fabrikam","corp.fabrikam.com"
PS C:\> Set-ADForest -Instance $Forest
```

This example modifies the **UPNSuffixes** property for the fabrikam.com forest.
The example modifies a local instance of the fabrikam.com forest, and then specifies the *Instance* parameter for the current cmdlet as the local instance.

## PARAMETERS

### -AuthType
Specifies the authentication method to use.
The acceptable values for this parameter are:

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

### -Credential
Specifies the user account credentials to use to perform this task.
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory module for Windows PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name such as User1 or Domain01\User01, or you can specify a **PSCredential** object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a **PSCredential** object by using a script or by using the **Get-Credential** cmdlet.
You can then set the *Credential* parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, Active Directory module for Windows PowerShell returns a terminating error.

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
The identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the attribute.
The acceptable values for this parameter are:

- A fully qualified domain name
- A GUID (objectGUID)
- A DNS host name
- A NetBIOS name

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to a forest object instance.

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
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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
Specifies the Active Directory Domain Services (AD DS) instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following: Active Directory Lightweight Directory Services (AD LDS), AD DS, or Active Directory snapshot instance.

Specify the AD DS instance in one of the following ways:

Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that they are listed:

- By using the *Server* value from objects passed through the pipeline
- By using the server information associated with the AD DS Windows PowerShell provider drive, when the cmdlet runs in that drive
- By using the domain of the computer running Windows PowerShell

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
### -SPNSuffixes
Modifies the list of service principal name (SPN) suffixes of the forest.
This parameter sets the multi-valued **msDS-SPNSuffixes** property of the cross-reference container.
This parameter uses the following syntax to add remove, replace, or clear SPN suffix values.

To add values:

`-SPNSuffixes @{Add=value1,value2,...}`

To remove values:

`-SPNSuffixes @{Remove=value3,value4,...}`

To replace values:

`-SPNSuffixes @{Replace=value1,value2,...}`

To clear all values:

`-SPNSuffixes $Null`

You can specify more than one change by using a list separated by semicolons.
For example, use the following syntax to add and remove SPN suffix values:

`@{Add=value1,value2,...};@{Remove=value3,value4,...}`

The operators are applied in the following sequence:

- Remove
- Add
- Replace

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


### -UPNSuffixes
Modifies the list of user principal name (UPN) suffixes of the forest.
This parameter sets the multi-valued **msDS-UPNSuffixes** property of the cross-reference container.
This parameter uses the following syntax to add remove, replace, or clear UPN suffix values.

To add values:

`-UPNSuffixes  @{Add=value1,value2,...}`

To remove values:

`-UPNSuffixes @{Remove=value3,value4,...}`

To replace values:

`-UPNSuffixes @{Replace=value1,value2,...}`

To clear all values:

`-UPNSuffixes $Null`

You can specify more than one change by using a list separated by semicolons.
For example, use the following syntax to add and remove UPN suffix values:

`@{Add=value1,value2,...};@{Remove=value3,value4,...}`

The operators are applied in the following sequence:

- Remove
- Add
- Replace

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADForest
A forest object is received by the *Identity* parameter.

A forest object that was retrieved by using the **Get-ADForest** cmdlet and then modified is received by the *Instance* parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADForest
Returns the modified forest object when the *PassThru* parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with AD LDS.
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADForest](./Get-ADForest.md)

