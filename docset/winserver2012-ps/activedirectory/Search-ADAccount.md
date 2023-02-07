---
external help file: Microsoft.ActiveDirectory.Management.dll-Help.xml
Module Name: ActiveDirectory
online version: https://learn.microsoft.com/powershell/module/activedirectory/search-adaccount?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
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
The Search-ADAccount cmdlet retrieves one or more user, computer, or service accounts that meet the criteria specified by the parameters.
Search criteria include account and password status.
For example, you can search for all accounts that have expired by specifying the AccountExpired parameter.
Similarly, you can search for all accounts with an expired password by specifying the PasswordExpired parameter.
You can limit the search to user accounts by specifying the UsersOnly parameter.
Similarly, when you specify the ComputersOnly parameter, the cmdlet only retrieves computer accounts.

Some search parameters, such as AccountExpiring and AccountInactive use a default time that you can change by specifying the DateTime or TimeSpan parameter.
The DateTime parameter specifies a distinct time.
The TimeSpan parameter specifies a time range from the current time.
For example, to search for all accounts that expire in 10 days, specify the AccountExpiring and TimeSpan parameter and set the value of TimeSpan to "10.00:00:00".
To search for all accounts that expire before December 31, 2012, set the DateTime parameter to "12/31/2012".

## EXAMPLES

### -------------------------- EXAMPLE 1 --------------------------
```
C:\PS>Search-ADAccount -AccountDisabled | FT Name,ObjectClass -A


Name            ObjectClass
----            -----------
Guest           user
krbtgt          user
krbtgt_51399    user
AmyAl-LPTOP     computer
DeepakAn-DSKTOP computer
```

Description

-----------

Returns all users, computers and service accounts that are disabled.

### -------------------------- EXAMPLE 2 --------------------------
```
C:\PS>Search-ADAccount -AccountDisabled -UsersOnly | FT Name,ObjectClass -A


Name         ObjectClass
----         -----------
Guest        user
krbtgt       user
krbtgt_51399 user
```

Description

-----------

Returns all users that are disabled.

### -------------------------- EXAMPLE 3 --------------------------
```
C:\PS>Search-ADAccount -AccountExpired | FT Name,ObjectClass -A


Name            ObjectClass
----            -----------
Greg Chapman    user
Claus Hansen    user
Tomasz Bochenek user
```

Description

-----------

Returns all users, computers and service accounts that are expired.

### -------------------------- EXAMPLE 4 --------------------------
```
C:\PS>Search-ADAccount -AccountExpiring -TimeSpan 6.00:00:00 | FT Name,ObjectClass -A


Name           ObjectClass
----           -----------
Iulian Calinov user
John Campbell  user
Garth Fort     user
```

Description

-----------

Returns all users, computers and service accounts that will expire in the next 6 days.

### -------------------------- EXAMPLE 5 --------------------------
```
C:\PS>Search-ADAccount -AccountInactive -TimeSpan 90.00:00:00 | FT Name,ObjectClass -A


Name                        ObjectClass
----                        -----------
FABRIKAM-RODC1              computer
Guest                       user
krbtgt                      user
krbtgt_51399                user
Almudena Benito             user
Aaron Con                   user
Adina Hagege                user
Aaron Nicholls              user
Aaron M. Painter            user
Jeff Phillips               user
Flemming Pedersen           use
```

Description

-----------

Returns all accounts that have been inactive for the last 90 days.

### -------------------------- EXAMPLE 6 --------------------------
```
C:\PS>Search-ADAccount -PasswordExpired | FT Name,ObjectClass -A


Name                        ObjectClass
----                        -----------
Stan Orme                   user
Danni Ortman                user
Matej Potokar               user
```

Description

-----------

Returns all accounts where the password has expired.

### -------------------------- EXAMPLE 7 --------------------------
```
C:\PS>Search-ADAccount -PasswordNeverExpires | FT Name,ObjectClass -A


Name           ObjectClass
----           -----------
Guest          user
Toni Poe       user
Anders Riis    user
Fabien Hernoux user
```

Description

-----------

Returns all accounts with a password that will never expire.

### -------------------------- EXAMPLE 8 --------------------------
```
C:\PS>Search-ADAccount -LockedOut | FT Name,ObjectClass -A

Name           ObjectClass
----           -----------
Toni Poe       user
```

Description

-----------

Returns all accounts that have been locked out.

### -------------------------- EXAMPLE 9 --------------------------
```
C:\PS>Search-ADAccount -AccountDisabled -ComputersOnly | FT Name,ObjectClass -A

Name           ObjectClass
----           -----------
TPOE-PC1       computer
```

Description

-----------

Returns all disabled computer accounts.

### -------------------------- EXAMPLE 10 --------------------------
```
C:\PS>Search-ADAccount -AccountExpiring -DateTime "3/18/2009" | FT Name,ObjectClass -A

Name         ObjectClass
----         -----------
Anders Riis  user
```

Description

-----------

Returns all accounts which expire on the 18th of March, 2009.

### -------------------------- EXAMPLE 11 --------------------------
```
C:\PS>Search-AdAccount -AccountDisabled -SearchBase "DC=AppNC" -Server "FABRIKAM-SRV1:60000"

Enabled               : False
Name                  : SanjayPatel
UserPrincipalName     :
PasswordNeverExpires  :
LockedOut             : False
ObjectGUID            : d671de28-6e40-42a7-b32c-63d336de296d
ObjectClass           : user
SID                   : S-1-510474493-936115905-2231798853-1260534229-4171027843-767619944
PasswordExpired       : False
LastLogonDate         :
DistinguishedName     : CN=SanjayPatel,OU=AccountDeptOU,DC=AppNC
AccountExpirationDate :
```

Description

-----------

Returns all users, computers and service accounts that are disabled in the LDS instance: "FABRIKAM-SRV1:60000".

## PARAMETERS

### -AccountDisabled
Returns account objects that are disabled.

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
Returns account objects that are expired.

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
Returns account objects that will expire in the specified TimeSpan.

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
Returns all accounts that have been inactive in the specified TimeSpan.

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
The type of authentication to run the cmdlet. Allowed values are
Negotiate
Basic

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
Limits the search only to computer objects.

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
PSCredential object representing the credentials of the user to use to run the cmdlet.

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
Enter a DateTime object, such as one that the Get-Date cmdlet returns, or a string that can be converted to a date and time, such as "April 19, 2012 15:00", "12/31", or "3am". DateTime objects, and strings that are converted to DateTime objects, are automatically adjusted to be compatible with the date and time formats selected for the local computer in Region and Language in Control Panel.

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
Returns all account objects that have been locked out.

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
Returns all account objects that have expired password.

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
Returns all account objects which password never expires.

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
Specifies the maximum number of objects to return for an Active Directory Domain Services query. If you want to receive all of the objects, set this parameter to $Null (null value). You can use Ctrl+C to stop the query and return of objects.

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
Specifies an Active Directory path to search under.

When you run a cmdlet from an Active Directory provider drive, the default value of this parameter is the current path of the drive.

When you run a cmdlet outside of an Active Directory provider drive against an AD DS target, the default value of this parameter is the default naming context of the target domain.

When you run a cmdlet outside of an Active Directory provider drive against an AD LDS target, the default value is the default naming context of the target LDS instance if one has been specified by setting the msDS-defaultNamingContext property of the Active Directory directory service agent (DSA) object (nTDSDSA) for the AD LDS instance. If no default naming context has been specified for the target AD LDS instance, then this parameter has no default value.

When the value of the SearchBase parameter is set to an empty string and you are connected to a GC port, all partitions will be searched. If the value of the SearchBase parameter is set to an empty string and you are not connected to a GC port, an error will be thrown.


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
The service may be any of the following: Active Directory Lightweight Domain Services, Active Directory Domain Services or Active Directory Snapshot instance.

Domain name values:

- Fully qualified domain name (FQDN)
- NetBIOS name

Directory server values:

- Fully qualified directory server name
- NetBIOS name
- Fully qualified directory server name and port

The default value for the *Server* parameter is determined by one of the following methods in the order that they are listed:

- By using *Server* value from objects passed through the pipeline. 
- By using the server information associated with the Active Directory PowerShell provider drive, when running under that drive. 
- By using the domain of the computer running PowerShell.

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
Enter a timespan object, such as one that the New-TimeSpan cmdlet returns or a string that can be converted to a timespan object, such as "30:00:00".

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
Limits the search to only user objects.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.ActiveDirectory.Management.ADAccount
Returns one or more account objects that meet the conditions set by the parameters.

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

