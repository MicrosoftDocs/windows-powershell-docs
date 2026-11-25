---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-adauthenticationpolicysilo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ADAuthenticationPolicySilo
---

# Set-ADAuthenticationPolicySilo

## SYNOPSIS
Modifies an Active Directory Domain Services authentication policy silo object.

## SYNTAX

### Identity
```
Set-ADAuthenticationPolicySilo [-WhatIf] [-Confirm] [-Add <Hashtable>] [-AuthType <ADAuthType>]
 [-Clear <String[]>] [-ComputerAuthenticationPolicy <ADAuthenticationPolicy>] [-Credential <PSCredential>]
 [-Description <String>] [-Enforce <Boolean>] [-Identity] <ADAuthenticationPolicySilo> [-PassThru]
 [-ProtectedFromAccidentalDeletion <Boolean>] [-Remove <Hashtable>] [-Replace <Hashtable>] [-Server <String>]
 [-ServiceAuthenticationPolicy <ADAuthenticationPolicy>] [-UserAuthenticationPolicy <ADAuthenticationPolicy>]
 [<CommonParameters>]
```

### Instance
```
Set-ADAuthenticationPolicySilo [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 -Instance <ADAuthenticationPolicySilo> [-PassThru] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-ADAuthenticationPolicySilo** cmdlet modifies the properties of an Active Directory® Domain Services authentication policy silo.
You can modify commonly used property values by using the cmdlet parameters.
Property values that are not associated with cmdlet parameters can be modified by using the *Add*, *Replace*, *Clear* and *Remove* parameters.

The *Identity* parameter specifies the Active Directory Domain Services authentication policy to modify.
You can specify an authentication policy object by using a distinguished name, a GUID, or a name.
You can also use the *Identity* parameter to specify a variable that contains an authentication policy object, or you can use the pipeline operator to pass an authentication policy object to the *Identity* parameter.
To get an authentication policy object, use the **Get-ADAuthenticationPolicy** cmdlet.

Use the *Instance* parameter to specify an authentication policy object to use as a template for the object being modified.
Do not specify both the *Instance* parameter and the *Identity* parameter.

## EXAMPLES

### Example 1: Modify an authentication policy silo
```
PS C:\> Set-ADAuthenticationPolicySilo -Identity AuthenticationPolicySilo01 -UserAuthenticationPolicy 'AuthenticationPolicy1'
```

This command modifies the user authentication policy for the authentication policy silo named AuthenticationPolicySilo01.

### Example 2: Modify multiple properties of an authentication policy silo
```
PS C:\> $AuthPolicySilo = Get-ADAuthenticationPolicySilo -Identity AuthenticationPolicySilo02
PS C:\> $AuthPolicySilo.Description = 'testDescription'
PS C:\> $AuthPolicySilo.Enforce = $False
PS C:\> Set-ADAuthenticationPolicySilo -Instance $AuthPolicySilo
```

This example first gets an authentication policy silo object and stores it in the variable named $AuthPolicySilo.
Properties of the authentication policy silo are then modified, and finally the contents of the variable are written to the authentication policy silo by using the *Instance* parameter.

### Example 3: Modify multiple authentication policy silo objects by filtering
```
PS C:\> Get-ADAuthenticationPolicySilo -Filter 'UserAuthenticationPolicy -eq "AuthenticationPolicy01"' | Set-ADAuthenticationPolicySilo -UserAuthenticationPolicy AuthenticationPolicy02
```

This example first gets all authentication policy silos that match the filter specified by the Filter parameter for Get-ADAuthenticationPolicySilo.
The results of the filter are then passed to Set-ADAuthenticationPolicySilo by using the pipeline operator.

### Example 4: Replace a value in an authentication policy silo object
```
PS C:\> Set-ADAuthenticationPolicySilo -Identity AuthenticationPolicySilo03 -Replace @{description="New Description"}
```

This command replaces the description for the authentication policy silo object named AuthenticationPolicySilo03.

## PARAMETERS

### -Add
Specifies a list of values to add to an object property.
Use this parameter to add one or more values to a property that cannot be modified using a parameter.
To identify an attribute, specify the Lightweight Directory Access Protocol (LDAP) display name defined for it in the Active Directory Domain Services schema.

Specify the attribute and the value of the attribute in the following format: @{'AttributeLDAPDisplayName'=value}.

To specify multiple values for an attribute, specify a comma separated list the values for the display name.
You can specify values for more than one attribute by using semicolons to separate attribute value pairs.

When specifying the *Add*, *Remove*, *Replace*, and *Clear* parameters together, the operations are performed in the following order:

- **Remove**
- **Add**
- **Replace**
- **Clear**

```yaml
Type: Hashtable
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Clear
Specifies an array of object properties that are cleared in the directory.
Use this parameter to clear one or more values of a property that cannot be modified using a parameter.
To modify an object property, you must specify the LDAP display name.
You can modify more than one property by specifying a comma-separated list.

When specifying the *Add*, *Remove*, *Replace*, and *Clear* parameters together, the operations are performed in the following order:

- **Remove**
- **Add**
- **Replace**
- **Clear**

```yaml
Type: String[]
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerAuthenticationPolicy
Specifies the authentication policy that applies to computer accounts.

```yaml
Type: ADAuthenticationPolicy
Parameter Sets: Identity
Aliases:

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
Specifies a user account that has permission to perform the task.
The default is the current user.
Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the **Get-Credential** cmdlet.

By default, the cmdlet uses the credentials of the currently logged on user unless the cmdlet is run from an Active Directory Domain Services Windows PowerShell provider drive.
If you run the cmdlet in a provider drive, the account associated with the drive is the default.

If you specify credentials that do not have permission to perform the task, the cmdlet returns an error.

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

### -Description
Specifies a description for the object.
This parameter sets the value of the description property for the object.
The LDAP display name (**ldapDisplayName**) for this property is description.

```yaml
Type: String
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enforce
Indicates whether the authentication policy is enforced.
Specify $True to set the authentication policy to enforced.
Specify $False to set the authentication policy to not enforced.

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity
Specifies an Active Directory Domain Services authentication policy silo object.
Specify the authentication policy silo object in one of the following formats:

- A distinguished name
- GUID
- Name

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

The cmdlet searches the default naming context or partition to find the object.
If the cmdlet finds two or more objects, the cmdlet returns a non-terminating error.

```yaml
Type: ADAuthenticationPolicySilo
Parameter Sets: Identity
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Instance
Specifies a modified copy of an **ADAuthenticationPolicySilo** object to use to update the actual **ADAuthenticationPolicySilo** object.
When you specify this parameter, any modifications made to the modified copy of the object are also made to the corresponding **ADAuthenticationPolicySilo** object.
The cmdlet only updates the object properties that have changed.
When you specify the *Instance* parameter, you cannot specify other parameters that set properties on the object.

To get the **ADAuthenticationPolicySilo** object to use to update the **ADAuthenticationPolicySilo** on which the cmdlet runs, use the Get-ADAuthenticationPolicySilo cmdlet.

```yaml
Type: ADAuthenticationPolicySilo
Parameter Sets: Instance
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### -ProtectedFromAccidentalDeletion
Indicates whether to prevent the object from being deleted.
When this property is set to true, you cannot delete the corresponding object without changing the value of the property.
The acceptable values for this parameter are:

- $False or 0
- $True or 1

```yaml
Type: Boolean
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Remove
Specifies that the cmdlet remove the values of an object property.
Use this parameter to remove one or more values of a property that cannot be modified using a cmdlet parameter.
To remove an object property, you must specify the LDAP display name.

Specify the attribute and the value of the attribute in the following format: @{'AttributeLDAPDisplayName'=value}.

To specify multiple values for an attribute, specify a comma separated list the values for the display name.
You can specify values for more than one attribute by using semicolons to separate attribute value pairs.

When specifying the *Add*, *Remove*, *Replace*, and *Clear* parameters together, the operations are performed in the following order:

- **Remove**
- **Add**
- **Replace**
- **Clear**

```yaml
Type: Hashtable
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Replace
Specifies a list of values for an object property that replaces the current values.
Use this parameter to replace one or more values of a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must specify the LDAP display name.

Specify the attribute and the value of the attribute in the following format: @{'AttributeLDAPDisplayName'=value}.

To specify multiple values for an attribute, specify a comma separated list the values for the display name.
You can specify values for more than one attribute by using semicolons to separate attribute value pairs.

When specifying the *Add*, *Remove*, *Replace*, and *Clear* parameters together, the operations are performed in the following order:

- **Remove**
- **Add**
- **Replace**
- **Clear**

```yaml
Type: Hashtable
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Specifies the Active Directory Domain Services instance to which to connect, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following:  Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory snapshot instance.

Specify the Active Directory Domain Services instance in one of the following ways:

Domain name values:

- Fully qualified domain name
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for this parameter is determined by one of the following methods in the order that they are listed:

- By using the *Server* value from objects passed through the pipeline
- By using the server information associated with the Active Directory Domain Services Windows PowerShell provider drive, when the cmdlet runs in that drive
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

### -ServiceAuthenticationPolicy
Specifies the authentication policy that applies to managed service accounts.

```yaml
Type: ADAuthenticationPolicy
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserAuthenticationPolicy
Specifies the authentication policy that applies to user accounts.

```yaml
Type: ADAuthenticationPolicy
Parameter Sets: Identity
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

### Microsoft.ActiveDirectory.Management.ADAccount
This cmdlet accepts an account object.

## OUTPUTS

### System.Object
Returns one or more objects.

## NOTES

## RELATED LINKS

[Get-ADAuthenticationPolicySilo](./Get-ADAuthenticationPolicySilo.md)

[New-ADAuthenticationPolicySilo](./New-ADAuthenticationPolicySilo.md)

[Remove-ADAuthenticationPolicySilo](./Remove-ADAuthenticationPolicySilo.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)

