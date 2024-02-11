---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/remove-adcentralaccesspolicymember?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ADCentralAccessPolicyMember
---

# Remove-ADCentralAccessPolicyMember

## SYNOPSIS
Removes central access rules from a central access policy in Active Directory.

## SYNTAX

```
Remove-ADCentralAccessPolicyMember [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADCentralAccessPolicy> [-Members] <ADCentralAccessRule[]> [-PassThru] [-Server <String>]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-ADCentralAccessPolicyMember** cmdlet removes central access rules from a central access policy in Active Directory.

## EXAMPLES

### Example 1: Remove a resource property from a central access policy
```
PS C:\> Remove-ADCentralAccessPolicyMember -Identity "Finance Policy" -Members "Finance Documents Rule"
```

This command removes the resource property named Finance Documents Rule from the central access policy named Finance Policy.

### Example 2: Remove central access rules from a central access policy
```
PS C:\> Remove-ADCentralAccessPolicyMember -Identity "Finance Policy" -Members "Finance Documents Rule","Corporate Documents Rule"
```

This command removes the central access rules named Finance Documents Rule and Corporate Documents Rule from the central access policy Finance Policy.

### Example 3: Get central access policies using a filter then remove specified central access rules from those policies
```
PS C:\> Get-ADCentralAccessPolicy -Filter "Name -like 'Corporate*'" | Remove-ADCentralAccessPolicyMember -Members "Finance Documents Rule","Corporate Documents Rule"
```

This command gets the central access policies that begin with Corporate in its name, and then pipes that result to the **Remove-ADCentralAccessPolicyMember**, which then removes the central access rules named Finance Documents Rule and Corporate Documents Rule from the policies.

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

### -Identity
Specifies an Active Directory object by providing one of the following property values.
The identifier in parentheses is the Lightweight Directory Access Protocol  (LDAP) display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)
- A security identifier (objectSid)
- A SAM account name (sAMAccountName)

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

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
Specifies a set of central access rule (CAR) objects in a comma-separated list to add to a central access policy.

To identify each object, use one of the following property values:

- Name
- A distinguished name
- GUID (objectGUID)

Note: The identifier in parentheses is the LDAP display name.

You can also provide objects to this parameter directly.

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
An **ADCentralAccessPolicy** object is received by the *Identity* parameter.

## OUTPUTS

### None or Microsoft.ActiveDirectory.ADCentralAccessPolicy
This cmdlet returns the modified **ADCentralAccessPolicy** object when the *PassThru* parameter is specified.
By default, this cmdlet does not generate any output.

## NOTES
* This cmdlet does not work with a read-only domain controller.
* This cmdlet does not work with an Active Directory snapshot.
* By default, this cmdlet has the *Confirm* parameter set, which prompts you to confirm before a removal of the specified object type can occur. To bypass prompting for confirmation before removal, you can specify `-Confirm:$False` when using this cmdlet.

## RELATED LINKS

[Add-ADCentralAccessPolicyMember](./Add-ADCentralAccessPolicyMember.md)

[AD DS Administration Cmdlets in Windows PowerShell](./activedirectory.md)

