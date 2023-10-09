---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://learn.microsoft.com/powershell/module/activedirectory/set-adcentralaccessrule?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-ADCentralAccessRule

## SYNOPSIS
Modifies a central access rule in Active Directory.

## SYNTAX

### Identity
```
Set-ADCentralAccessRule [-WhatIf] [-Confirm] [-Add <Hashtable>] [-AuthType <ADAuthType>] [-Clear <String[]>]
 [-Credential <PSCredential>] [-CurrentAcl <String>] [-Description <String>] [-Identity] <ADCentralAccessRule>
 [-PassThru] [-ProposedAcl <String>] [-ProtectedFromAccidentalDeletion <Boolean>] [-Remove <Hashtable>]
 [-Replace <Hashtable>] [-ResourceCondition <String>] [-Server <String>] [<CommonParameters>]
```

### Instance
```
Set-ADCentralAccessRule [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 -Instance <ADCentralAccessRule> [-PassThru] [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The Set-ADCentralAccessRule cmdlet can be used to modify a central access rule in a central access policy that is stored in Active Directory.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>$departmentResourceProperty = Get-ADResourceProperty Department
$resourceCondition = "(@RESOURCE." + $departmentResourceProperty.Name + " Contains {`"Finance`"})"
Set-ADCentralAccessRule "Finance Documents Rule" -ResourceCondition $resourceCondition
```

Description

-----------

Set the central access rule named "Finance Documents Rule" with a new resource condition.
The resource condition scopes the resources to ones containing the value 'Finance' in their 'Department' resource property.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>$countryClaimType = Get-ADClaimType Country;
$departmentClaimType = Get-ADClaimType Department;
$countryResourceProperty = Get-ADResourceProperty Country;
$departmentResourceProperty = Get-ADResourceProperty Department;
$financeException = Get-ADGroup FinanceException;
$financeAdmin = Get-ADGroup FinanceAdmin;

$resourceCondition = "(@RESOURCE." + $departmentResourceProperty.Name + " Contains {`"Finance`"})"

$currentAcl = "O:SYG:SYD:AR(A;;FA;;;OW)(A;;FA;;;BA)(A;;0x1200a9;;;" + $financeException.SID.Value + ")(A;;0x1301bf;;;" + $financeAdmin.SID.Value + ")(A;;FA;;;SY)(XA;;0x1200a9;;;AU;((@USER." + $countryClaimType.Name + " Any_of @RESOURCE." + $countryResourceProperty.Name + ") && (@USER." + $departmentClaimType.Name + " Any_of @RESOURCE." + $departmentResourceProperty.Name + ")))";

Set-ADCentralAccessRule "Finance Documents Rule" -ResourceCondition $resourceCondition -CurrentAcl $currentAcl
```

Description

-----------

Set the central access rule named "Finance Documents Rule" with a new resource condition and new permissions.

The new rule specifies that documents should only be read by members of the Finance department. 
Members of the Finance department should only be able to access documents in their own country/region. 
Only Finance Administrators should have write access. 
The rule allows an exception for members of the FinanceException group.
This group will have read access.

Targeting:

Resource.Department Contains Finance

Access rules:

Allow Read User.Country=Resource.Country AND User.department = Resource.Department

Allow Full control User.MemberOf(FinanceAdmin)

Allow Read User.Country=Resource.Country AND User.department = Resource.Department

Allow Read User.MemberOf(FinanceException)

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Get-ADCentralAccessRule "Finance Documents Rule" | Set-ADCentralAccessRule -Description "For finance documents."
```

Description

-----------

Get the central access rule named "Finance Documents Rule", and set the description to "For finance documents."

## PARAMETERS

### -Add
Specifies values to add to an object property.
Use this parameter to add one or more values to a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the LDAP display name.
You can specify multiple values to a property by specifying a comma-separated list of values and more than one property by separating them using a semicolon..
The format for this parameter is

-Add @{Attribute1LDAPDisplayName=value1, value2, ...;   Attribute2LDAPDisplayName=value1, value2, ...; AttributeNLDAPDisplayName=value1, value2, ...}

For example, if you want to remove the value "555-222-2222" and add the values "555-222-1111" and "555-222-3333" to Phone-Office-Other attribute (LDAP display name 'otherTelephone'), and add the value "555-222-9999" to Phone-Mobile-Other (LDAP display name 'otherMobile'), set the Add and Remove parameters as follows.

-Add @{otherTelephone='555-222-1111', '555-222-3333'; otherMobile='555-222-9999' } -Remove @{otherTelephone='555-222-2222'}

When you use the Add, Remove, Replace and Clear parameters together, the operations will be performed in the following order:

..Remove

..Add

..Replace

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

### -Clear
Specifies an array of object properties that will be cleared in the directory.
Use this parameter to clear one or more values of a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the LDAP display name.
You can modify more than one property by specifying a comma-separated list.
The format for this parameter is

-Clear Attribute1LDAPDisplayName, Attribute2LDAPDisplayName

For example, if you want to clear the value for the Phone-Office-Other attribute (LDAP display name 'otherTelephone') set the Clear parameter as follows.

-Clear otherTelephone

When you use the Add, Remove, Replace and Clear parameters together, the operations will be performed in the following order:

..Remove

..Add

..Replace

..Clear

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

### -CurrentAcl
This parameter specifies the currently effective ACL of the central access rule.
The current ACL grants access to target resources once the central access policy containing this rule is published.

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

### -Description
Specifies a description of the object.
This parameter sets the value of the Description property for the object.
The LDAP Display Name (ldapDisplayName) for this property is "description".

The following example shows how to set this parameter to a sample description.

-Description "Description of the object"

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

### -Identity
Specifies an Active Directory object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.

Distinguished Name

Example: CN=Finance Documents Rule,CN=Central Access Rules,CN=Claims Configuration,CN=Services,CN=Configuration,DC=corp,DC=contoso,DC=com

GUID (objectGUID)

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

This example shows how to set this parameter to an ADObject object instance named "ADObjectInstance".

-Identity   $ADObjectInstance

```yaml
Type: ADCentralAccessRule
Parameter Sets: Identity
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Instance
Specifies a modified copy of an central access rule object to use to update the actual central access rule object.
When this parameter is used, any modifications made to the modified copy of the object are also made to the corresponding central access rule object.
The cmdlet only updates the object properties that have changed.

The Instance parameter can only update central access rule objects that have been retrieved by using the Get-ADCentralAccessRule cmdlet. 
When you specify the Instance parameter, you cannot specify other parameters that set properties on the object.

The following is an example of how to use the Get-ADCentralAccessRule cmdlet to retrieve an instance of the object.
The object is modified by using the Windows PowerShell command line.
Then the Set-ADCentralAccessRule cmdlet saves the changes to the central access rule object.

Step 1: Retrieve a local instance of the object.

$objectInstance = Get-ADCentralAccessRule -Identity  "Finance Documents Rule"

Step 2: Modify one or more properties of the object instance.

$objectInstance.Description = "For finance documents."

Step 3: Save your changes to the object

Set-ADCentralAccessRule -Instance $objectInstance

```yaml
Type: ADCentralAccessRule
Parameter Sets: Instance
Aliases: 

Required: True
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

### -ProposedAcl
Specifies the proposed ACL of the central access rule.
The proposed ACL allows an administrator to audit the results of access requests to target resources specified in the resource condition without affecting the current system.
To view the logs, go to Event Viewer or other audit tools to view the logs.

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
Parameter Sets: Identity
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Remove
Specifies that the cmdlet remove values of an object property.
Use this parameter to remove one or more values of a property that cannot be modified using a cmdlet parameter.
To remove an object property, you must use the LDAP display name.
You can remove more than one property by specifying a semicolon-separated list.
The format for this parameter is

-Remove @{Attribute1LDAPDisplayName=value\[\];   Attribute2LDAPDisplayName=value\[\]}

For example, if you want to add the values blue and green and remove the value pink from a property with a LDAP display name of FavColors, set the Add and Remove parameters as follows.

-Add @{FavColors=Blue,Green} -Remove {FavColors=Pink}

When you use the Add, Remove, Replace and Clear parameters together, the parameters will be applied in the following sequence:

..Remove

..Add

..Replace

..Clear

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
Specifies values for an object property that will replace the current values.
Use this parameter to replace one or more values of a property that cannot be modified using a cmdlet parameter.
To modify an object property, you must use the LDAP display name.
You can modify more than one property by specifying a comma-separated list.
The format for this parameter is

-Replace @{Attribute1LDAPDisplayName=value\[\],   Attribute2LDAPDisplayName=value\[\]}

For example, if you want to replace the value "555-222-2222" with the values "555-222-1111" for Phone-Office-Other attribute (LDAP display name 'otherTelephone') set the Replace parameter as follows.

-Replace @{otherTelephone='555-222-2222', '555-222-1111'}

When you use the Add, Remove, Replace  and Clear parameters together, the operations will be performed in the following order:

..Remove

..Add

..Replace

..Clear

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

### -ResourceCondition
Specifies the resource condition of the central access rule.
The resource condition specifies a list of criteria to scope the resources.

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

### None or Microsoft.ActiveDirectory.Management.ADCentralAccessPolicyEntry
A ADCentralAccessPolicyEntry object is received by the Identity parameter.

A ADCentralAccessPolicyEntry object that was retrieved by using the Get-ADCentralAccessPolicyEntry cmdlet and then modified is received by the Instance parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.Management.ADCentralAccessPolicyEntry
Returns the modified ADCentralAccessPolicyEntry object when the PassThru parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with an Active Directory Snapshot.

  This cmdlet does not work with a read-only domain controller.

## RELATED LINKS

