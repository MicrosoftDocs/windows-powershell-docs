---
author: Kateyanne
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
manager: dansimp
Module Name: ActiveDirectory
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/activedirectory/add-adcentralaccesspolicymember?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-ADCentralAccessPolicyMember

## SYNOPSIS
Adds central access rules to a central access policy in Active Directory.

## SYNTAX

```
Add-ADCentralAccessPolicyMember [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADCentralAccessPolicy> [-Members] <ADCentralAccessRule[]> [-PassThru] [-Server <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The Add-ADCentralAccessPolicyMember cmdlet adds central access rules to a central access policy in Active Directory.

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Add-ADCentralAccessPolicyMember "Finance Policy" -Member "Finance Documents Rule","Corporate Documents Rule"
```

Description

-----------

Adds the central access rules 'Finance Documents Rule' and 'Corporate Documents Rule' to the central access policy 'Finance Policy'.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Add-ADCentralAccessPolicyMember

cmdlet Add-ADCentralAccessPolicyMember at command pipeline position 1
Supply values for the following parameters:
Identity: Finance Policy
Members[0]: Finance Documents Rule
Members[1]: Corporate Documents Rule
Members[2]:
```

Description

-----------

Demonstrates default behavior for this cmdlet (no parameters specified).
Adds central access rules 'Finance Documents Rule' and 'Corporate Documents Rule' to the central access policy 'Finance Policy'.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Get-ADCentralAccessPolicy -Filter "Name -like 'Corporate*'" | Add-ADCentralAccessPolicyMember -Members "Corporate Documents Rule"
```

Description

-----------

Gets all central access policies that have a name that starts with "Corporate" and then pipes it to Add-ADCentralAccessPolicyMember, which then adds the central access rule with the name 'Corporate Documents Rule' to it.

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
Specifies an Active Directory object by providing one of the following property values.
The identifier in parentheses is the LDAP display name for the attribute.

Distinguished Name

Example: CN=Finance Documents Policy,CN=Central Access Policies,CN=Claims Configuration,CN=Services,CN=Configuration,DC=corp,DC=contoso,DC=com

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

This example shows how to set this parameter to an ADObject object instance named "ADObjectInstance".

-Identity   $ADObjectInstance

```yaml
Type: ADCentralAccessPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Members
Specifies a set of central access rule (CAR) objects in a comma-separated list to add to a central access policy (CAP).
To identify each object, use one of the following property values.
Note: The identifier in parentheses is the LDAP display name.

Name

Example: Finance Documents Rule

Distinguished Name

Example:  CN=Finance Documents Rule,CN=Central Access Rules,CN=Claims Configuration,CN=Services,CN=Configuration,DC=corp,DC=contoso,DC=com

Example: 599c3d2e-f72d-4d20-8a88-030d99495f20

You can also provide objects to this parameter directly.

The following examples show how to specify this parameter.

This example specifies two CARs to add by specifying the distinguished name and the name properties.

-Members "CN=Finance Documents Rule,CN=Central Access Rules,CN=Claims Configuration,CN=Services,CN=Configuration,DC=corp,DC=contoso,DC=com", "Corporate Documents Rule"

This example specifies two CARs that are defined in the current Windows PowerShell session as input for the parameter.

-Members $carObject, $carObject2

You cannot pass objects through the pipeline to this parameter.

```yaml
Type: ADCentralAccessRule[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
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

### None or Microsoft.ActiveDirectory.Management.ADCentralAccessPolicy
A ADCentralAccessPolicy object is received by the Identity parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.ADCentralAccessPolicy
Returns the modified ADCentralAccessPolicy object when the PassThru parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with a read-only domain controller.

  This cmdlet does not work with an Active Directory Snapshot.

## RELATED LINKS

