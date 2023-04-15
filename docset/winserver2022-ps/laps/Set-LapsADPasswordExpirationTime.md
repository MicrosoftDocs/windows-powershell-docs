---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: lapspsh.dll-Help.xml
Module Name: LAPS
online version: https://learn.microsoft.com/powershell/module/laps/set-lapsadpasswordexpirationtime?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
Locale: en-US
ms.date: 04/10/2023
title: Set-LapsADPasswordExpirationTime
---

# Set-LapsADPasswordExpirationTime

## SYNOPSIS
Sets the Windows Local Administrator Password Solution (LAPS) password expiration timestamp on an
Active Directory computer or domain controller object.

## SYNTAX

```
Set-LapsADPasswordExpirationTime [-Credential <PSCredential>] -Identity <String[]>
 [-WhenEffective <DateTime>] [-Domain <String>] [-DomainController <String>] [<CommonParameters>]
```

## DESCRIPTION

The `Set-LapsADPasswordExpirationTime` cmdlet is used by administrators to configure the LAPS
password expiration time on an Active Directory computer or domain controller object.

> [!TIP]
> Running this cmdlet sets the LAPS password expiration time on the Active Directory computer or
> domain controller object, but the new expiration time will not be honored until the next time the
> target device executes a LAPS policy processing cycle.

## EXAMPLES

### Example 1

```powershell
Set-LapsADPasswordExpirationTime -Identity lapsClient
```

```Output
DistinguishedName                           Status
-----------------                           ------
CN=LAPSCLIENT,OU=LapsTestOU,DC=laps,DC=com  PasswordReset
```

This examples show setting the LAPS password expiration time to the current time (or in other words,
expiring the password immediately).

### Example 2

```powershell
Set-LapsADPasswordExpirationTime -Identity lapsClient -WhenEffective (Get-Date -Date "07/04/2023 13:00:00")
```

```Output
DistinguishedName                           Status
-----------------                           ------
CN=LAPSCLIENT,OU=LapsTestOU,DC=laps,DC=com  PasswordReset
```

This examples show setting the LAPS password expiration time to a specific date.

### Example 3

```powershell
Set-LapsADPasswordExpirationTime -Identity lapsClient -WhenEffective (DateTime::Now.AddDays(1))
```

```Output
DistinguishedName                           Status
-----------------                           ------
CN=LAPSCLIENT,OU=LapsTestOU,DC=laps,DC=com  PasswordReset
```

This examples show setting the LAPS password expiration time to one day in the future.

## PARAMETERS

### -Credential

Specifies the credentials to use when updating Active Directory. If not specified the current user's
credentials will be used.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainController

Specifies which Active Directory domain controller to connect to.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Identity

Specifies which Active Directory computer or domain controller object to set the LAPS password
expiration time on.

This parameter accepts several different name formats which influence the criteria used when
searching Active Directory for the target device. The supported name formats are as follows:

- distinguishedName (begins with a "CN=")
- samAccountName (begins with a `$`)
- dnsHostName (contains at least one `.` character)
- name (for all other inputs)

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -WhenEffective

Specifies the new LAPS password expiration time. If not specified the current time will be used, in
other words the password is immediately expired.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
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
