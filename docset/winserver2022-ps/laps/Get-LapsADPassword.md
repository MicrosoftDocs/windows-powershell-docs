---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: lapspsh.dll-Help.xml
Module Name: LAPS
online version: https://learn.microsoft.com/powershell/module/laps/get-lapsadpassword?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
Locale: en-US
ms.date: 04/10/2023
title: Get-LapsADPassword
---

# Get-LapsADPassword

## SYNOPSIS
Queries Windows Local Administrator Password Solution (LAPS) credentials from Active Directory on a
specified AD computer or domain controller object.

## SYNTAX

### NormalMode (Default)

```
Get-LapsADPassword [-Credential <PSCredential>] [-DecryptionCredential <PSCredential>]
 [-IncludeHistory] [-AsPlainText] [-Identity] <String[]> [<CommonParameters>]
```

### DomainMode

```
Get-LapsADPassword [-Credential <PSCredential>] [-DecryptionCredential <PSCredential>]
 [-IncludeHistory] [-AsPlainText] [-Identity] <String[]> -Domain <String> [<CommonParameters>]
```

### DomainControllerMode

```
Get-LapsADPassword [-Credential <PSCredential>] [-DecryptionCredential <PSCredential>] [-IncludeHistory]
 [-AsPlainText] [-Identity] <String[]> -DomainController <String> [<CommonParameters>]
```

### SnapshotBrowserMode

```
Get-LapsADPassword [-Credential <PSCredential>] [-DecryptionCredential <PSCredential>]
 [-IncludeHistory] [-AsPlainText] -Port <Int32> [-Identity] <String[]> [-DomainController <String>]
 [<CommonParameters>]
```

### RecoveryMode

```
Get-LapsADPassword [-IncludeHistory] [-AsPlainText] [-RecoveryMode] [-Identity] <String[]>
 [<CommonParameters>]
```

### SnapshotBrowserRecoveryMode

```
Get-LapsADPassword [-IncludeHistory] [-AsPlainText] [-RecoveryMode] -Port <Int32>
 [-Identity] <String[]> [<CommonParameters>]
```

## DESCRIPTION

The `Get-LapsADPassword` cmdlet allows administrators to retrieve LAPS passwords and password
history for an Active Directory computer or domain controller object. Depending on policy
configuration, LAPS passwords may be stored in either clear-text form or encrypted form. The
`Get-LapsADPassword` cmdlet will automatically perform decryption of encrypted passwords.

The `Get-LapsADPassword` cmdlet may also be used to connected to a mounted Active Directory snapshot.

The **Verbose** may be used to get additional information about the cmdlet's operation.

## EXAMPLES

### Example 1

```powershell
Get-LapsADPassword lapsClient
```

```Output
ComputerName        : LAPSCLIENT
DistinguishedName   : CN=LAPSCLIENT,OU=LapsTestOU,DC=laps,DC=com
Account             : Administrator
Password            : System.Security.SecureString
PasswordUpdateTime  : 4/9/2023 10:03:41 AM
ExpirationTimestamp : 4/14/2023 10:03:41 AM
Source              : CleartextPassword
DecryptionStatus    : NotApplicable
AuthorizedDecryptor : NotApplicable
```

This example demonstrates querying the current LAPS password for the 'lapsClient' computer in the
current domain. The password was stored in Active Directory in clear-text form and did not require
decryption. The password was returned wrapped in a SecureString object.

### Example 2

```powershell
Get-LapsADPassword -Identity lapsClient -DomainController lapsDC -AsPlainText

ComputerName        : LAPSCLIENT
DistinguishedName   : CN=LAPSCLIENT,OU=LapsTestOU,DC=laps,DC=com
Account             : Administrator
Password            : k8P]Xl5T-ky!aj4s21el3S#.x44!e{8+,{L!M
PasswordUpdateTime  : 4/9/2023 10:03:41 AM
ExpirationTimestamp : 4/14/2023 10:03:41 AM
Source              : CleartextPassword
DecryptionStatus    : NotApplicable
AuthorizedDecryptor : NotApplicable
```

This example demonstrates querying the current LAPS password on a specific domain controller
('lapsDC'), for the 'lapsClient' computer, requesting that the password be displayed in clear-text
form. The password was stored in Active Directory in clear-text form and did not require decryption.
The password was returned in clear-text form.

### Example 3

```powershell
Get-LapsADPassword -Identity $lapsClient2 -Domain laps.com -AsPlainText -IncludeHistory

ComputerName        : LAPSCLIENT2
DistinguishedName   : CN=LAPSCLIENT2,OU=LapsTestEncryptedOU,DC=laps,DC=com
Account             : Administrator
Password            : q64!7KI3BOe/&S%buM0nBaW{B]261zN5L0{;{
PasswordUpdateTime  : 4/9/2023 9:39:38 AM
ExpirationTimestamp : 4/14/2023 9:39:38 AM
Source              : EncryptedPassword
DecryptionStatus    : Success
AuthorizedDecryptor : LAPS\LAPS Admins

ComputerName        : LAPSCLIENT2
DistinguishedName   : CN=LAPSCLIENT2,OU=LapsTestEncryptedOU,DC=laps,DC=com
Account             : Administrator
Password            : O{P61q6bu(3kZ6&#p2y.&F$cWd;0dm8!]Wl5j
PasswordUpdateTime  : 4/9/2023 9:38:10 AM
ExpirationTimestamp :
Source              : EncryptedPasswordHistory
DecryptionStatus    : Success
AuthorizedDecryptor : LAPS\LAPS Admins
```

This example demonstrates querying the current LAPS password for the 'lapsClient2' computer, in a
specific Active Directory domain ('laps.com'), requesting that the password be displayed in
clear-text form. The password was stored in Active Directory in encrypted form and was successfully
decrypted.

Note that ExpirationTimestamp will always be empty for any older LAPS passwords returned.

### Example 4

```powershell
Get-LapsADPassword -Identity lapsDC.laps.com -AsPlainText

ComputerName        : LAPSDC
DistinguishedName   : CN=LAPSDC,OU=Domain Controllers,DC=laps,DC=com
Account             : Administrator
Password            : 118y$rsw.3y58yG]on$Hii
PasswordUpdateTime  : 4/9/2023 10:17:51 AM
ExpirationTimestamp : 4/19/2023 10:17:51 AM
Source              : EncryptedDSRMPassword
DecryptionStatus    : Success
AuthorizedDecryptor : LAPS\Domain Admins
```

This example demonstrates querying the current LAPS password for the 'lapsDC.laps.com' domain
controller, requesting that the password be displayed in clear-text form. The password was stored in
Active Directory in encrypted form and was successfully decrypted.

### Example 5

```powershell
Get-LapsADPassword lapsClient2

ComputerName        : LAPSDC
DistinguishedName   : CN=LAPSDC,OU=Domain Controllers,DC=laps,DC=com
Account             :
Password            :
PasswordUpdateTime  : 4/9/2023 10:17:51 AM
ExpirationTimestamp : 4/19/2023 10:17:51 AM
Source              : EncryptedDSRMPassword
DecryptionStatus    : Unauthorized
AuthorizedDecryptor : LAPS\Domain Admins
```

This example demonstrates querying the current LAPS password for the 'lapsDC' domain controller when
the user does not have permissions to decrypt the LAPS DSRM password.

### Example 6

```powershell
Get-LapsADPassword lapsLegacyClient -AsPlainText

ComputerName        : LAPSLEGACYCLIENT
DistinguishedName   : CN=LAPSLEGACYCLIENT,OU=LegacyLapsOU,DC=laps,DC=com
Account             :
Password            : Z#x}&7BluHf3{r+C218
PasswordUpdateTime  :
ExpirationTimestamp : 5/14/2023 1:55:39 PM
Source              : LegacyLapsCleartextPassword
DecryptionStatus    : NotApplicable
AuthorizedDecryptor : NotApplicable
```

This example demonstrates querying the current LAPS password for the 'lapsLegacyClient' machine
which is currently running in legacy LAPS emulation mode. Note that when querying legacy LAPS-style
passwords, the Account and PasswordUpdateTime fields will always be unavailable.

### Example 7

```powershell
Get-LapsADPassword -Identity lapsClient -Port 50000 -AsPlainText

ComputerName        : LAPSCLIENT
DistinguishedName   : CN=LAPSCLIENT,OU=LapsTestOU,DC=laps,DC=com
Account             : Administrator
Password            : H6UycL[vj#zzTNVpS//G2{j&t9aO}k[K5l4)X
PasswordUpdateTime  : 4/15/2023 6:51:45 AM
ExpirationTimestamp : 4/20/2023 6:51:45 AM
Source              : CleartextPassword
DecryptionStatus    : NotApplicable
AuthorizedDecryptor : NotApplicable
```

This example demonstrates querying an Active Directory Snapshot browser instance for the current
LAPS password for the 'LAPSCLIENT' machine. This example assumes that that the snapshot browser has
been previously started on the local machine listening on an LDAP port of 50000.

## PARAMETERS

### -AsPlainText

Specify this parameter to return the LAPS passwords in clear-text format. The default behavior is to
return the LAPS passwords wrapped in a .NET SecureString object.

> [!IMPORTANT]
> Using this parameter exposes the returned clear-text password to casual viewing and may pose a
> security risk. This parameter should be used with caution and only in support or testing
> situations.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential

Specifies a set of credentials to use when querying Active Directory for the LAPS credentials. If
not specified the current user's credentials will be used.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: NormalMode, DomainMode, DomainControllerMode, SnapshotBrowserMode
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DecryptionCredential

Specifies a set of credentials to use when decrypting encrypted LAPS credentials. If not specified
the current user's credentials will be used.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: NormalMode, DomainMode, DomainControllerMode, SnapshotBrowserMode
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Domain

Specifies which Active Directory domain to connect to.

```yaml
Type: System.String
Parameter Sets: DomainMode
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainController

Specifies which Active Directory domain controller to connect to, or the remote server on which an
Active Directory snapshot browser is running.

```yaml
Type: System.String
Parameter Sets: DomainControllerMode
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: SnapshotBrowserMode
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity

Specifies which Active Directory computer or domain controller object to retrieve LAPS credentials
from.

This parameter accepts several different name formats which influence the criteria used when
searching Active Directory for the target device. The supported name formats are as follows:

distinguishedName (begins with a "CN=")
samAccountName (begins with a '$")
dnsHostName (contains at least one '.' character)
name (for all other inputs)

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -IncludeHistory

Specifies that any older LAPS credentials on the computer object should also be displayed.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Port

Specifies which Active Directory Snapshot Browser port to connect to.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: SnapshotBrowserMode, SnapshotBrowserRecoveryMode
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryMode

This parameter provides a last-ditch option when it is no longer possible to decrypt a given LAPS
credential via the normal mechanisms. For example, this might be necessary if a LAPS credential was
encrypted against a group which has since been deleted.

>[!IMPORTANT]
>When specifying this parameter, you MUST be logged-in locally as a Domain Administrator on a writable domain controller.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RecoveryMode, SnapshotBrowserRecoveryMode
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable,
-InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose,
-WarningAction, and -WarningVariable. For more information, see
[about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Windows LAPS Overview](https://go.microsoft.com/fwlink/?linkid=2233901)

[Get started with Windows LAPS and Windows Server Active Directory](https://go.microsoft.com/fwlink/?linkid=2233705)
