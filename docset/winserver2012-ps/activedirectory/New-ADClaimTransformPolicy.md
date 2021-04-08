---
author: Kateyanne
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
manager: dansimp
Module Name: ActiveDirectory
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/activedirectory/new-adclaimtransformpolicy?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
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
The New-ADClaimTransformPolicy cmdlet creates a new claims transformation policy object in Active Directory.
A claims transformation policy object contains a set of rules authored in the transformation rule language.
After creating a policy object, you can link it with a forest trust to apply the claims transformation to the trust.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>New-ADClaimTransformPolicy DenyAllPolicy -DenyAll
```

Description

-----------

Create a new claims transformation policy named 'DenyAllPolicy' that denies all claims, both those that are sent as well as those that are received.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>New-ADClaimTransformPolicy AllowAllExceptCompanyAndDepartmentPolicy -AllowAllExcept Company,Department
```

Description

-----------

Create a new claims transformation policy named 'AllowAllExceptCompanyAndDepartmentPolicy' that allows all claims to be sent or received except for the claims 'Company' and 'Department'.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>New-ADClaimTransformPolicy HumanResourcesToHrPolicy -Rule 'C1:[Type=="ad://ext/Department:88ceb0fe88a125db", Value=="Human Resources", ValueType=="string"] => issue(Type=C1.Type, Value="HR", ValueType=C1.ValueType);'
```

Description

-----------

Create a new claims transformation policy named 'HumanResourcesToHrPolicy' that transforms the value 'Human Resources' to 'HR' in the claim 'Department'.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>$rule = Get-Content C:\rule.txt;
New-ADClaimTransformPolicy MyRule -Rule $rule
```

Description

-----------

Create a new claims transformation policy named 'MyRule' with the rule specified in C:\rule.txt.

## PARAMETERS

### -AllowAll
When this parameter is specified, the policy sets a claims transformation rule that would allow all claims to be sent or received.

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
Specifies a user account that has permission to perform this action.
The default is the current user.

Type a user name, such as "User01" or "Domain01\User01", or enter a PSCredential object, such as one generated by the Get-Credential cmdlet.
If you type a user name, you will be prompted for a password.

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
When this parameter is specified, the policy sets a claims transformation rule that would deny all claims to be sent or received.

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
This parameter sets the value of the Description property for the object.
The LDAP Display Name (ldapDisplayName) for this property is "description".

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
The following examples show how to use these two methods to create a new claims transformation policy object.

Method 1: Use an existing claims transformation policy object as a template for a new object.
To retrieve an instance of an existing claims transformation policy object, use a cmdlet such as Get-ADClaimsTransformationPolicy.
Then provide this object to the Instance parameter of the New-ADClaimsTransformationPolicy cmdlet to create a new claims transformation policy object.
You can override property values of the new object by setting the appropriate parameters.

$objectInstance = Get-ADClaimsTransformationPolicy -Identity "Allow All except Finance Policy"

New-ADClaimsTransformationPolicy -Name "Allow All Except Pii Policy"  -Instance $ObjectInstance

Method 2: Create a new ADClaimsTransformationPolicy and set the property values by using the Windows PowerShell command line interface.
Then pass this object to the Instance parameter of the New-ADClaimsTransformationPolicy cmdlet to create the new Active Directory object.

$objectInstance = new-object Microsoft.ActiveDirectory.Management.ADClaimsTransformationPolicy $objectInstance.Description = "For finance only."

New-ADClaimsTransformationPolicy -Name "Deny All except  Finance Policy" -Instance $ObjectInstance

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
This parameter sets the Name property of the Active Directory object.
The LDAP Display Name (ldapDisplayName) of this property is "name".

The following example shows how to set this parameter to a name string.

-Name "Allow All Policy"

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

### -ProtectedFromAccidentalDeletion
Specifies whether to prevent the object from being deleted.
When this property is set to true, you cannot delete the corresponding object without changing the value of the property.
Possible values for this parameter include:

$false or 0

$true or 1

The following example shows how to set this parameter to true.

-ProtectedFromAccidentalDeletion $true

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
Represents the claims transformation rule.
To specify the rule, you can either (1) type the rule in a text file, and then pass the file to the cmdlet (recommended), or (2) type the rule inline.

For example, the following commands demonstrate how to create a new claims transformation policy object with the rule specified in a text file named Rule.txt located in a temporary folder C:\temp.

$rule = Get-Content C:\temp\rule.txt;

New-ADClaimTransformPolicy MyRule -Rule $rule

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

### None or Microsoft.ActiveDirectory.Management.ADClaimTransformPolicy
A claims transformation policy object that is a template for the new claims transformation policy object is received by the Instance parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADClaimTransformPolicy

## NOTES
* This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

