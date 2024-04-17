---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/new-adcentralaccesspolicy?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-ADCentralAccessPolicy
---

# New-ADCentralAccessPolicy

## SYNOPSIS
Creates a new central access policy in Active Directory containing a set of central access rules.

## SYNTAX

```
New-ADCentralAccessPolicy [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Description <String>] [-Instance <ADCentralAccessPolicy>] [-Name] <String> [-PassThru]
 [-ProtectedFromAccidentalDeletion <Boolean>] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-ADCentralAccessPolicy** cmdlet creates a new central access policy in Active Directory.
A central access policy in Active Directory contains a set of central access rules.

## EXAMPLES

### Example 1: Create a central access policy with a resource condition
```
PS C:\> $DepartmentResourceProperty = Get-ADResourceProperty -Identity Department 
PS C:\> $ResourceCondition = "(@RESOURCE." + $DepartmentResourceProperty.Name + " Contains {`"Finance`"})"
PS C:\> New-ADCentralAccessRule -Name "Finance Documents Rule" -ResourceCondition $ResourceCondition
```

This command creates a central access rule named Finance Documents Rule with a new resource condition.
The resource condition scopes the resources to ones containing the value Finance in their Department resource property.

### Example 2: Create a central access policy with a resource condition and new permissions
```
PS C:\> $CountryClaimType = Get-ADClaimType -Identity Country 
PS C:\> $DepartmentClaimType = Get-ADClaimType -Identity Department 
PS C:\> $CountryResourceProperty = Get-ADResourceProperty -Identity Country 
PS C:\> $DepartmentResourceProperty = Get-ADResourceProperty -Identity Department 
PS C:\> $FinanceException = Get-ADGroup -Identity FinanceException 
PS C:\> $FinanceAdmin = Get-ADGroup -Identity FinanceAdmin 
PS C:\> $ResourceCondition = "(@RESOURCE." + $DepartmentResourceProperty.Name + " Contains {`"Finance`"})" 
PS C:\> $CurrentAcl = "O:SYG:SYD:AR(A;;FA;;;OW)(A;;FA;;;BA)(A;;0x1200a9;;;" + $FinanceException.SID.Value + ")(A;;0x1301bf;;;" + $FinanceAdmin.SID.Value + ")(A;;FA;;;SY)(XA;;0x1200a9;;;AU;((@USER." + $CountryClaimType.Name + " Any_of @RESOURCE." + $CountryResourceProperty.Name + ") && (@USER." + $DepartmentClaimType.Name + " Any_of @RESOURCE." + $DepartmentResourceProperty.Name + ")))" 
PS C:\> Set-ADCentralAccessRule -Identity "Finance Documents Rule" -ResourceCondition $ResourceCondition -CurrentAcl $CurrentAcl
```

This command creates a central access rule named Finance Documents Rule with a new resource condition and new permissions.

The new rule specifies that documents should only be read by members of the Finance department.
Members of the Finance department should only be able to access documents in their own country/region.
Only Finance Administrators should have write access.
The rule allows an exception for members of the FinanceException group.
This group will have read access.

Targeting:

- Resource.Department Contains Finance

Access rules:

- Allow Read User.Country=Resource.Country AND User.department = Resource.Department
- Allow Full control User.MemberOf(FinanceAdmin)
- Allow Read User.Country=Resource.Country AND User.department = Resource.DepartmentAllow Read User.MemberOf(FinanceException)

### Example 3: Create a central access policy using properties from an existing Active Directory object
```
PS C:\> Get-ADCentralAccessPolicy -Identity "Finance Policy" | New-ADCentralAccessPolicy -Name "Human Resources Policy" -Description "For the Human Resources Department."
```

This command creates a central access policy named Human Resources Policy using the property values from Finance Policy, and set the description to For the Human Resources Department.

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

To specify this parameter, you can type a user name, such as User1 or Domain01\User01 or you can specify a **PSCredential** object.
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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Instance
Specifies an instance of an Active Directory object to use as a template for a new Active Directory object.

You can use an instance of an existing Active Directory object as a template or you can construct a new Active Directory object by using the Windows PowerShell command line or by using a script.

Method 1: Use an existing Active Directory object as a template for a new object.
To retrieve an instance of an existing Active Directory object, use a cmdlet such as **Get-ADObject**.
Then provide this object to the Instance parameter of the New-ADObject cmdlet to create a new Active Directory object.
You can override property values of the new object by setting the appropriate parameters.

Method 2: Create a new **ADObject** and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the *Instance* parameter of the **New-ADObject** cmdlet to create the new Active Directory object.

Note: Specified attributes are not validated, so attempting to set attributes that do not exist or cannot be set will raise an error.

```yaml
Type: ADCentralAccessPolicy
Parameter Sets: (All)
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
The Lightweight Directory Access Protocol (LDAP) display name (**ldapDisplayName**) of this property is name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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
When this property is set to true, you cannot delete the corresponding object without changing the value of the property.
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
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Server
Specifies the Active Directory Domain Services instance to connect to, by providing one of the following values for a corresponding domain name or directory server.
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

### None or Microsoft.ActiveDirectory.Management.ADCentralAccessPolicy
An Active Directory object that is a template for the new object is received by the *Instance* parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADCentralAccessPolicy
Returns the new central access policy object when the *PassThru* parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with an Active Directory snapshot.
* This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

[Get-ADCentralAccessPolicy](./Get-ADCentralAccessPolicy.md)

[Remove-ADCentralAccessPolicy](./Remove-ADCentralAccessPolicy.md)

[Set-ADCentralAccessPolicy](./Set-ADCentralAccessPolicy.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)

