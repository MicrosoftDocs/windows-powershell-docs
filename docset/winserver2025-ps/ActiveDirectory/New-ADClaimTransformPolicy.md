---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/new-adclaimtransformpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-ADClaimTransformPolicy
---

# New-ADClaimTransformPolicy

## SYNOPSIS
Creates a new claim transformation policy object in Active Directory.

## SYNTAX

### AllowAll
```
New-ADClaimTransformPolicy [-WhatIf] [-Confirm] [-AllowAll] [-AuthType <ADAuthType>]
 [-Credential <PSCredential>] [-Description <String>] [-Name] <String> [-PassThru]
 [-ProtectedFromAccidentalDeletion <Boolean>] [-Server <String>] [<CommonParameters>]
```

### AllowAllExcept
```
New-ADClaimTransformPolicy [-WhatIf] [-Confirm] -AllowAllExcept <ADClaimType[]> [-AuthType <ADAuthType>]
 [-Credential <PSCredential>] [-Description <String>] [-Name] <String> [-PassThru]
 [-ProtectedFromAccidentalDeletion <Boolean>] [-Server <String>] [<CommonParameters>]
```

### DenyAll
```
New-ADClaimTransformPolicy [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-DenyAll] [-Description <String>] [-Name] <String> [-PassThru] [-ProtectedFromAccidentalDeletion <Boolean>]
 [-Server <String>] [<CommonParameters>]
```

### DenyAllExcept
```
New-ADClaimTransformPolicy [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 -DenyAllExcept <ADClaimType[]> [-Description <String>] [-Name] <String> [-PassThru]
 [-ProtectedFromAccidentalDeletion <Boolean>] [-Server <String>] [<CommonParameters>]
```

### Identity
```
New-ADClaimTransformPolicy [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Description <String>] [-Instance <ADClaimTransformPolicy>] [-Name] <String> [-PassThru]
 [-ProtectedFromAccidentalDeletion <Boolean>] -Rule <String> [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-ADClaimTransformPolicy** cmdlet creates a new claims transformation policy object in Active Directory.
A claims transformation policy object contains a set of rules authored in the transformation rule language.
After creating a policy object, you can link it with a forest trust to apply the claims transformation to the trust.

## EXAMPLES

### Example 1: Create a new claims transformation policy by name that denies all claims
```
PS C:\> New-ADClaimTransformPolicy -Name "DenyAllPolicy" -DenyAll
```

This command creates a new claims transformation policy named DenyAllPolicy that denies all claims, both those that are sent as well as those that are received.

### Example 2: Create a new claim transformation policy by name with exclusions
```
PS C:\> New-ADClaimTransformPolicy -Name "AllowAllExceptCompanyAndDepartmentPolicy" -AllowAllExcept Company,Department
```

This command creates a new claims transformation policy named AllowAllExceptCompanyAndDepartmentPolicy that allows all claims to be sent or received except for the claims Company and Department.

### Example 3: Create a new claim transformation policy that changes an existing name to a new name
```
PS C:\> New-ADClaimTransformPolicy -Name "HumanResourcesToHrPolicy" -Rule 'C1:[Type=="ad://ext/Department:88ceb0fe88a125db", Value=="Human Resources", ValueType=="string"] => issue(Type=C1.Type, Value="HR", ValueType=C1.ValueType);'
```

This command creates a new claims transformation policy named HumanResourcesToHrPolicy that transforms the value Human Resources to HR in the claim Department.

### Example 4: Create a new claims transformation policy by name using a rule specified in a file
```
PS C:\> $Rule = Get-Content C:\rule.txt
PS C:\> New-ADClaimTransformPolicy -Name "MyRule" -Rule $Rule
```

This example creates a claims transformation policy named MyRule with the rule specified in C:\rule.txt.

## PARAMETERS

### -AllowAll
Indicates that the policy sets a claims transformation rule that would allow all claims to be sent or received.

```yaml
Type: SwitchParameter
Parameter Sets: AllowAll
Aliases:
Accepted values: true

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AllowAllExcept
Specifies an array of claim types.
When this parameter is specified, the policy sets a claims transformation rule that would allow all claims to be sent or received except for the specified claim types.

```yaml
Type: ADClaimType[]
Parameter Sets: AllowAllExcept
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Specifies a user account that has permission to perform this action.
The default is the current user.

Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the **Get-Credential** cmdlet.
You will be prompted for a password if you type a user name.

This parameter is not supported by any providers installed with Windows PowerShell.

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

### -DenyAll
Indicates that the policy sets a claims transformation rule that would deny all claims to be sent or received.

```yaml
Type: SwitchParameter
Parameter Sets: DenyAll
Aliases:
Accepted values: true

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DenyAllExcept
Specifies an array of claim types.
When this parameter is specified, the policy sets a claims transformation rule that would deny all claims to be sent or received except for the specified claim types.

```yaml
Type: ADClaimType[]
Parameter Sets: DenyAllExcept
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description
Specifies a description of the object.
This parameter sets the value of the **Description** property for the object.
The Lightweight Directory Access Protocol (LDAP) display name (**ldapDisplayName**) for this property is description.

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

### -Instance
Specifies an instance of an Active Directory object to use as a template for a new claims transformation policy object.

You can use an instance of an existing claims transformation policy object as a template or you can construct a new claims transformation policy object by using the Windows PowerShell command line or by using a script.

Method 1: Use an existing claims transformation policy object as a template for a new object.
To retrieve an instance of an existing claims transformation policy object, use  the  Get-ADClaimTransformPolicy cmdlet.
Then provide this object to the *Instance* parameter of the **New-ADClaimTransformPolicy** cmdlet to create a new claims transformation policy object.
You can override property values of the new object by setting the appropriate parameters.

Method 2: Create a new **ADClaimsTransformationPolicy** object and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the Instance parameter of the **New-ADClaimTransformPolicy** cmdlet to create the new Active Directory object.

Note: Specified attributes are not validated, so attempting to set attributes that do not exist or cannot be set will raise an error.

```yaml
Type: ADClaimTransformPolicy
Parameter Sets: Identity
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the name of the object.
This parameter sets the **Name** property of the Active Directory object.
The LDAP display name (**ldapDisplayName**) of this property is name.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
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
Specifies whether to prevent the object from being deleted.
When this property is set to $True, you cannot delete the corresponding object without changing the value of the property.
The acceptable values for this parameter are:

- $False or 0
- $True or 1

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Rule
Specifies the claims transformation rule.
To specify the rule, you can either (1) type the rule in a text file, and then pass the file to the cmdlet (recommended), or (2) type the rule inline.

For instance, the following commands demonstrate how to create a new claims transformation policy object with the rule specified in a text file named Rule.txt located in a temporary folder C:\temp.

`$Rule = Get-Content C:\temp\rule.txt`

`New-ADClaimTransformPolicy MyRule -Rule $Rule`

```yaml
Type: String
Parameter Sets: Identity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Server
Specifies the Active Directory Domain Services instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
The service may be any of the following: Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory snapshot instance.

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

### None or Microsoft.ActiveDirectory.Management.ADClaimTransformPolicy
Specifies a claims transformation policy object that is a template for the new claims transformation policy object is received by the *Instance* parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADClaimTransformPolicy

## NOTES
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADClaimTransformPolicy](./Get-ADClaimTransformPolicy.md)

[Remove-ADClaimTransformPolicy](./Remove-ADClaimTransformPolicy.md)

[Set-ADClaimTransformPolicy](./Set-ADClaimTransformPolicy.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)

