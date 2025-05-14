---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/activedirectory/search-adaccount?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Search-ADAccount
---

# Search-ADAccount

## SYNOPSIS
Gets Active Directory user, computer, or service accounts.

## SYNTAX

### AccountDisabled
```
Search-ADAccount [-AccountDisabled] [-AuthType <ADAuthType>] [-ComputersOnly] [-Credential <PSCredential>]
 [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-SearchBase <String>] [-SearchScope <ADSearchScope>]
 [-Server <String>] [-UsersOnly] [<CommonParameters>]
```

### AccountExpired
```
Search-ADAccount [-AccountExpired] [-AuthType <ADAuthType>] [-ComputersOnly] [-Credential <PSCredential>]
 [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-SearchBase <String>] [-SearchScope <ADSearchScope>]
 [-Server <String>] [-UsersOnly] [<CommonParameters>]
```

### AccountExpiring
```
Search-ADAccount [-AccountExpiring] [-AuthType <ADAuthType>] [-ComputersOnly] [-Credential <PSCredential>]
 [-DateTime <DateTime>] [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-SearchBase <String>]
 [-SearchScope <ADSearchScope>] [-Server <String>] [-TimeSpan <TimeSpan>] [-UsersOnly] [<CommonParameters>]
```

### AccountInactive
```
Search-ADAccount [-AccountInactive] [-AuthType <ADAuthType>] [-ComputersOnly] [-Credential <PSCredential>]
 [-DateTime <DateTime>] [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-SearchBase <String>]
 [-SearchScope <ADSearchScope>] [-Server <String>] [-TimeSpan <TimeSpan>] [-UsersOnly] [<CommonParameters>]
```

### LockedOut
```
Search-ADAccount [-AuthType <ADAuthType>] [-ComputersOnly] [-Credential <PSCredential>] [-LockedOut]
 [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-SearchBase <String>] [-SearchScope <ADSearchScope>]
 [-Server <String>] [-UsersOnly] [<CommonParameters>]
```

### PasswordExpired
```
Search-ADAccount [-AuthType <ADAuthType>] [-ComputersOnly] [-Credential <PSCredential>] [-PasswordExpired]
 [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-SearchBase <String>] [-SearchScope <ADSearchScope>]
 [-Server <String>] [-UsersOnly] [<CommonParameters>]
```

### PasswordNeverExpires
```
Search-ADAccount [-AuthType <ADAuthType>] [-ComputersOnly] [-Credential <PSCredential>] [-PasswordNeverExpires]
 [-ResultPageSize <Int32>] [-ResultSetSize <Int32>] [-SearchBase <String>] [-SearchScope <ADSearchScope>]
 [-Server <String>] [-UsersOnly] [<CommonParameters>]
```

## DESCRIPTION
The **Search-ADAccount** cmdlet retrieves one or more user, computer, or service accounts that meet the criteria specified by the parameters.
Search criteria include account and password status.
For example, you can search for all accounts that have expired by specifying the *AccountExpired* parameter.
Similarly, you can search for all accounts with an expired password by specifying the *PasswordExpired* parameter.
You can limit the search to user accounts by specifying the *UsersOnly* parameter.
Similarly, when you specify the *ComputersOnly* parameter, the cmdlet only retrieves computer accounts.

Some search parameters, such as *AccountExpiring* and *AccountInactive* use a default time that you can change by specifying the *DateTime* or *TimeSpan* parameter.
The *DateTime* parameter specifies a distinct time.
The *TimeSpan* parameter specifies a time range from the current time.
For example, to search for all accounts that expire in 10 days, specify the *AccountExpiring* and *TimeSpan* parameter and set the value of *TimeSpan* to 10.00:00:00.
To search for all accounts that expire before December 31, 2012, set the *DateTime* parameter to 12/31/2012.

## EXAMPLES

### Example 1: Get all users, computers, and service accounts that are disabled
```
PS C:\> Search-ADAccount -AccountDisabled | FT Name,ObjectClass -A
Name            ObjectClass
----            -----------
Guest           user
Pattith         user
PattiFul_51399   user
PattyFul-LPTOP   computer
PattyFul-DSKTOP  computer
```

This command returns all users, computers, and service accounts that are disabled.

### Example 2: Get all users that are disabled
```
PS C:\> Search-ADAccount -AccountDisabled -UsersOnly | FT Name,ObjectClass -A
Name         ObjectClass
----         -----------
Guest         user
PattiFul       user
PattiFul_51399 user
```

This command returns all users that are disabled.

### Example 3: Get all users, computers, and service accounts that are expired
```
PS C:\> Search-ADAccount -AccountExpired | FT Name,ObjectClass -A
Name            ObjectClass
----            -----------
Evan Narvaez    user
Patti Fuller    user
David Chew      user
```

This command returns all users, computers, and service accounts that are expired.

### Example 4: Get all users, computers, and service accounts that will expire in a specified time
```
PS C:\> Search-ADAccount -AccountExpiring -TimeSpan 6.00:00:00 | FT Name,ObjectClass -A
Name           ObjectClass
----           -----------
David Chew     user
Evan Narvaez   user
Patti Fuller   user
```

This command returns all users, computers, and service accounts that will expire in the next 6 days.

### Example 5: Get all accounts that have expired
```
PS C:\> Search-ADAccount -PasswordExpired | FT Name,ObjectClass -A
Name                        ObjectClass
----                        -----------
David Chew                  user
Evan Narvaez                user
Patti Fuller                user
```

This command returns all accounts where the password has expired.

### Example 6: Get all accounts that are locked out
```
PS C:\> Search-ADAccount -LockedOut | FT Name,ObjectClass -A
Name           ObjectClass
----           -----------
Patti Fuller       user
```

This command returns all accounts that have been locked out.

## PARAMETERS

### -AccountDisabled
Specifies a search for accounts that are disabled.
An account is disabled when the ADAccount **Enabled** property is set to false.

```yaml
Type: SwitchParameter
Parameter Sets: AccountDisabled
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AccountExpired
Specifies a search for accounts that are expired.
An account is expired when the ADAccount **AccountExpirationDate** property is set to a time in the past.
The Lightweight Directory Access Protocol (LDAP) display name (**ldapDisplayName**) for the **AccountExpirationDate** property is accountExpires.

```yaml
Type: SwitchParameter
Parameter Sets: AccountExpired
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AccountExpiring
Indicates that this cmdlet searches for accounts that are expiring in a given time period or by a specified time.
To specify a time period, use the *AccountExpiring* parameter with the *TimeSpan* parameter.
To specify a specific time, use the *AccountExpiring* parameter with the *DateTime* parameter.

```yaml
Type: SwitchParameter
Parameter Sets: AccountExpiring
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AccountInactive
Indicates that this cmdlet searches for accounts that have not logged in within a given time period or since a specified time.
To specify a time period, use the *TimeSpan* parameter.
To specify a specific time, use the *DateTime* parameter.
Note that this attribute is only used when the domain is in Windows Server 2003 Domain Functional Level or higher, so this parameter will only work in that mode.

```yaml
Type: SwitchParameter
Parameter Sets: AccountInactive
Aliases:

Required: True
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

### -ComputersOnly
Indicates that this cmdlet searches only computer accounts.

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

### -Credential
Specifies the user account credentials to use to perform this task.
The default credentials are the credentials of the currently logged on user unless the cmdlet is run from an Active Directory module for Windows PowerShell provider drive.
If the cmdlet is run from such a provider drive, the account associated with the drive is the default.

To specify this parameter, you can type a user name, such as User1 or Domain01\User01 or you can specify a **PSCredential** object.
If you specify a user name for this parameter, the cmdlet prompts for a password.

You can also create a **PSCredential** object by using a script or by using the **Get-Credential** cmdlet.
You can then set the *Credential* parameter to the **PSCredential** object.

If the acting credentials do not have directory-level permission to perform the task, Active Directory module for Windows PowerShell returns a terminating error.

Specifies the credentials for the security context under which the task is performed.
If this security context doesn't have directory level permissions to perform the task, then an error is returned by the directory.
If running under the context of an Active Directory module for Windows PowerShell provider drive, the credentials information associated with the drive is used as the default value; otherwise, the currently logged on user security context is used.

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

### -DateTime
Specifies a distinct time value for **Search-ADAccount** parameters such as *AccountExpiring*, *AccountInactive*, and *PasswordExpired*.

Time is assumed to be local time unless otherwise specified.
When a time value is not specified, the time is assumed to be midnight local time.
If you do not specify a date, the date is assumed to be the current date.
The following examples show commonly-used syntax to specify a *DateTime* object.

- "4/17/2006"
- "Monday, April 17, 2006"
- "2:22:45 PM"
- "Monday, April 17, 2006 2:22:45 PM"

These examples specify the same date and the time without the seconds.

- "4/17/2006 2:22 PM"
- "Monday, April 17, 2006 2:22 PM"
- "2:22 PM"

The following example shows how to specify a date and time by using the RFC1123 standard.
This example defines time by using Greenwich Mean Time (GMT).

- "Mon, 17 Apr 2006 21:22:48 GMT"

The following example shows how to specify a value as Coordinated Universal Time (UTC).
This example represents Monday, April 17, 2006 at 2:22:48 PM UTC.

- "2006-04-17T14:22:48.0000000"

The following example shows how to set the *AccountExpiring* parameter to a *DateTime* value of June 18, 2012 at 2:00:00 AM.

`-AccountExpiring -DateTime "6/18/2012 2:00:00 AM"`

```yaml
Type: DateTime
Parameter Sets: AccountExpiring, AccountInactive
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LockedOut
Indicates that this cmdlet searches for accounts that are locked out.

```yaml
Type: SwitchParameter
Parameter Sets: LockedOut
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PasswordExpired
Indicates that this cmdlet searches for accounts that have an expired password.

```yaml
Type: SwitchParameter
Parameter Sets: PasswordExpired
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PasswordNeverExpires
Indicates that this cmdlet searches for accounts that have a password that does not expire.

```yaml
Type: SwitchParameter
Parameter Sets: PasswordNeverExpires
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResultPageSize
Specifies the number of objects to include in one page for an Active Directory Domain Services query.

The default is 256 objects per page.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResultSetSize
Specifies the maximum number of objects to return for an Active Directory Domain Services query.
If you want to receive all of the objects, set this parameter to $Null (null value).
You can use Ctrl+C to stop the query and return of objects.
The default is $Null.

The following example shows how to set this parameter so that you receive all of the returned objects:

`-ResultSetSize $Null`

```yaml
Type: Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SearchBase
Specifies an Active Directory path to search.

When you run a cmdlet from an Active Directory provider drive, the default value of this parameter is the current path of the drive.

When you run a cmdlet outside of an Active Directory provider drive against an Active Directory Domain Services (AD DS) target, the default value of this parameter is the default naming context of the target domain.

When you run a cmdlet outside of an Active Directory provider drive against an Active Directory Lightweight Directory Services (AD LDS) target, the default value is the default naming context of the target AD LDS instance if one has been specified by setting the **msDS-defaultNamingContext** property of the Active Directory service agent object **nTDSDSA** for the AD LDS instance.
If no default naming context has been specified for the target AD LDS instance, then this parameter has no default value.

The following example shows how to set this parameter to search under an organizational unit.

`-SearchBase "ou=mfg,dc=noam,dc=corp,dc=contoso,dc=com"`

When the value of the *SearchBase* parameter is set to an empty string and you are connected to a global catalog port, all partitions are searched.
If the value of the *SearchBase* parameter is set to an empty string and you are not connected to a global catalog port, an error is generated.

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

### -SearchScope
Specifies the scope of an Active Directory search.
The acceptable values for this parameter are:

- Base or 0
- OneLevel or 1
- Subtree or 2

A Base query searches only the current path or object.
A OneLevel query searches the immediate children of that path or object.
A Subtree query searches the current path or object and all children of that path or object.

```yaml
Type: ADSearchScope
Parameter Sets: (All)
Aliases:
Accepted values: Base, OneLevel, Subtree

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

### -TimeSpan
Specifies a time interval.
This parameter is used to specify a time value for **Search-ADAccount** parameters such as *AccountExpiring*.
Specify the time interval in the following format:

\[-\]D.H:M:S.F

where:

- D = Days (0 to 10675199)
- H = Hours (0 to 23)
- M = Minutes (0 to 59)
- S = Seconds (0 to 59)
- F = Fractions of a second (0 to 9999999)

Note: Time values must be between the following values: -10675199:02:48:05.4775808 and 10675199:02:48:05.4775807.

The following examples show how to set this parameter.

Set the time to 2 days

`-TimeSpan "2.00:00:00"`

  Set the time span to the previous 2 days

`-TimeSpan "-2.00:00.00"`

  Set the time to 4 hours

`-TimeSpan "4:00"`

For example, to search for all accounts that are expiring in 10 days, specify the *AccountExpiring* and *TimeSpan* parameters as follows.

  `-AccountExpiring -TimeSpan "10.00:00.00"`

```yaml
Type: TimeSpan
Parameter Sets: AccountExpiring, AccountInactive
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UsersOnly
Indicates that this cmdlet searches for user accounts only.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADAccount
This cmdlet returns one or more account objects that meet the conditions set by the parameters.

## NOTES

## RELATED LINKS

[Clear-ADAccountExpiration](./Clear-ADAccountExpiration.md)

[Disable-ADAccount](./Disable-ADAccount.md)

[Enable-ADAccount](./Enable-ADAccount.md)

[Get-ADAccountResultantPasswordReplicationPolicy](./Get-ADAccountResultantPasswordReplicationPolicy.md)

[Set-ADAccountControl](./Set-ADAccountControl.md)

[Set-ADAccountExpiration](./Set-ADAccountExpiration.md)

[Set-ADAccountPassword](./Set-ADAccountPassword.md)

[Unlock-ADAccount](./Unlock-ADAccount.md)

