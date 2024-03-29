---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/activedirectory/remove-adauthenticationpolicy?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-ADAuthenticationPolicy
---

# Remove-ADAuthenticationPolicy

## SYNOPSIS
Removes an Active Directory Domain Services authentication policy object.

## SYNTAX

```
Remove-ADAuthenticationPolicy [-WhatIf] [-Confirm] [-AuthType <ADAuthType>] [-Credential <PSCredential>]
 [-Identity] <ADAuthenticationPolicy> [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-ADAuthenticationPolicy** cmdlet removes an Active Directory® Domain Services authentication policy.

The **Identity** parameter specifies the Active Directory Domain Services authentication policy to remove.
You can identify an authentication policy by its distinguished name, GUID or name.
You can also use the **Identity** parameter to specify a variable that contains an authentication policy object, or you can use the pipeline operator to pass an authentication policy object to the **Identity** parameter.

## EXAMPLES

### Example 1: Remove an authentication policy by specifying a name
```
PS C:\> Remove-ADAuthenticationPolicy -Identity AuthenticationPolicy01
```

This command removes the authentication policy specified by the **Identity** parameter.

### Example 2: Remove multiple authentication policies
```
PS C:\> Get-ADAuthenticationPolicy -Filter 'Enforce -eq $false' | Remove-ADAuthenticationPolicy
```

This command uses the Get-ADAuthenticationPolicy cmdlet with the **Filter** parameter to get all authentication policies that are not enforced.
The pipeline operator then passes the result of the filter to the **Remove-ADAuthenticationPolicy** cmdlet.

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
Specifies a user account that has permission to perform the task.
The default is the current user.
Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the Get-Credentialhttp://go.microsoft.com/fwlink/?LinkID=293936 cmdlet.

By default, the cmdlet uses the credentials of the currently logged on user unless the cmdlet is run from an Active Directory Domain ServicesWindows PowerShell provider drive.
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

### -Identity
Specifies an Active Directory Domain Services authentication policy object.
Specify the authentication policy object in one of the following formats: 

- A distinguished name
- GUID
- Name

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

The cmdlet searches the default naming context or partition to find the object.
If the cmdlet finds two or more objects, the cmdlet returns a non-terminating error.

```yaml
Type: ADAuthenticationPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

- By using the **Server** value from objects passed through the pipeline
- By using the server information associated with the Active Directory Domain ServicesWindows PowerShell provider drive, when the cmdlet runs in that drive
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None or Microsoft.ActiveDirectory.Management.ADAuthenticationPolicy
This cmdlet accepts an authentication policy object.

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-ADAuthenticationPolicy](./Get-ADAuthenticationPolicy.md)

[New-ADAuthenticationPolicy](./New-ADAuthenticationPolicy.md)

[Set-ADAuthenticationPolicy](./Set-ADAuthenticationPolicy.md)

[AD DS Administration Cmdlets in Windows PowerShell](./ActiveDirectory.md)

