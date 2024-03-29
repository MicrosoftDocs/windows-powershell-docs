---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 10/30/2017
online version: https://learn.microsoft.com/powershell/module/activedirectory/sync-adobject?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Sync-ADObject
---

# Sync-ADObject

## SYNOPSIS
Replicates a single object between any two domain controllers that have partitions in common.

## SYNTAX

```
Sync-ADObject [-AuthType <ADAuthType>] [-Credential <PSCredential>] [-Destination] <String>
 [-Object] <ADObject> [-PassThru] [-PasswordOnly] [[-Source] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Sync-ADObject** cmdlet replicates a single object between any two domain controllers that have partitions in common.
The two domain controllers do not need to be direct replication partners.
You can also use this cmdlet to populate passwords in a read-only domain controller (RODC) cache.

## EXAMPLES

### Example 1: Replicate an object to another location
```
PS C:\>Sync-ADObject -Object "CN=AccountManagers,OU=AccountDeptOU,DC=corp,DC=contoso,DC=com" -Source "corp-DC01" -Destination "corp-DC02"
```

This command replicates an object with the distinguished name CN=AccountManagers,OU=AccountDeptOU,DC=corp,DC=contoso,DC=com from corp-DC01 to corp-DC02.

### Example 2: Pre-cache a password to a domain controller
```
PS C:\>Get-ADUser -Identity pattifuller | Sync-ADObject -Destination "corp-RODC01" -PasswordOnly
```

This command pre-caches the password of Patti Fuller to the read-only domain controller corp-RODC01 using the SAM account name of the user.

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

### -Credential
Specifies a user account that has permission to perform this action.
The default is the current user.

Type a user name, such as User01 or Domain01\User01, or enter a **PSCredential** object, such as one generated by the Get-Credentialhttp://go.microsoft.com/fwlink/?LinkID=293936 cmdlet.
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

### -Destination
Specifies the identity of the Active Directory server that acts as the destination for synchronizing this data.
This parameter works similarly to the **Server** parameter as used on the Set-ADObject cmdlet with some restrictions.
It does not allow domain or forest names to be used.
Valid formats for specifying the destination server are:

- Host name
- Host name and port
- Fully qualified directory server name and port
- IP address
- IP address and port

```yaml
Type: String
Parameter Sets: (All)
Aliases: Server, HostName, IPv4Address

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Object
Specifies an Active Directory object by providing one of the following property values.
The identifier in parentheses is the Lightweight Directory Access Protocol (LDAP) display name for the attribute.
The acceptable values for this parameter are:

- A distinguished name
- A GUID (objectGUID)

The cmdlet searches the default naming context or partition to find the object.
If two or more objects are found, the cmdlet returns a non-terminating error.

This parameter can also get this object through the pipeline or you can set this parameter to an object instance.

Derived types, such as the following, are also accepted: 

- **Microsoft.ActiveDirectory.Management.ADGroup**
- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADServiceAccount**
- **Microsoft.ActiveDirectory.Management.ADOrganizationalUnit**
- **Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy**
- **Microsoft.ActiveDirectory.Management.ADDomain**

```yaml
Type: ADObject
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -PasswordOnly
Indicates that this cmdlet populates a read-only domain controller (RODC) password cache with the password of the account specified in the **Object** parameter.
If specified, no data other than the password is replicated.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source
Specifies the identity of the Active Directory server that acts as the source for synchronizing this data.
This parameter works similarly to the **Server** parameter as used on the **Set-ADObject** cmdlet with some restrictions.
You cannot use domain or forest names.

Valid formats for specifying the destination server are the following:

- Host name
- Host name and port
- Fully qualified directory server name and port
- IP address
- IP address and port

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.ActiveDirectory.Management.ADObject
Derived types, such as the following are also accepted:

- **Microsoft.ActiveDirectory.Management.ADGroup**
- **Microsoft.ActiveDirectory.Management.ADUser**
- **Microsoft.ActiveDirectory.Management.ADComputer**
- **Microsoft.ActiveDirectory.Management.ADServiceAccount**
- **Microsoft.ActiveDirectory.Management.ADOrganizationalUnit**
- **Microsoft.ActiveDirectory.Management.ADFineGrainedPasswordPolicy**
- **Microsoft.ActiveDirectory.Management.ADDomain**

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-ADObject](./Get-ADObject.md)

[Move-ADObject](./Move-ADObject.md)

[New-ADObject](./New-ADObject.md)

[Remove-ADObject](./Remove-ADObject.md)

[Rename-ADObject](./Rename-ADObject.md)

[Restore-ADObject](./Restore-ADObject.md)

[Set-ADObject](./Set-ADObject.md)

