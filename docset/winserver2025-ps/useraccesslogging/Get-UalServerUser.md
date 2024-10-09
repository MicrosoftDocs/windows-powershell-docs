---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MsftUal_ServerUser.cdxml-help.xml
Module Name: UserAccessLogging
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/useraccesslogging/get-ualserveruser?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UalServerUser
---

# Get-UalServerUser

## SYNOPSIS
Gets UAL records for a server per user.

## SYNTAX

```
Get-UalServerUser [-ChassisSerialNumber <String[]>] [-UUID <String[]>] [-Username <String[]>]
 [-ActivityCount <UInt32[]>] [-FirstSeen <DateTime[]>] [-LastSeen <DateTime[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-UalServerUser** cmdlet gets User Access Logging (UAL) records for client requests, by user, for services on a server.
Use the *CimSession* parameter to run the cmdlet on a remote server.

This cmdlet organizes information by user.
For each user that accesses a service on a server, the cmdlet returns a record that specifies the user, the chassis serial number for the server, and Universally Unique Identifier (UUID) for the server.
The record also includes the first time the client accessed the service, the most recent time the client accessed the service, and the total number of times the client accessed the service.

You can specify parameter values to narrow the records that this cmdlet returns.
For instance, you can get records for only a specified user.

For more information about UAL, see the [User Access Logging Overview](https://technet.microsoft.com/library/hh849634.aspx) topic in the TechNet library at http://technet.microsoft.com/library/hh849634.aspx.

## EXAMPLES

### Example 1: Get access records for a specified user
```
PS C:\>Get-UalServerUser -Username "western\sarahjones"
ActivityCount       : 1

ChassisSerialNumber : 4550-1195-7960-9223-8899-0403-95

FirstSeen           : 8/17/2012 12:37:30 PM

LastSeen            : 8/17/2012 12:37:30 PM

UserName            : western\sarahjones

UUID                : A9258570-6931-405C-8DB5-1A351A82B278

PSComputerName      :
```

This command gets the UAL records for a server for a client with a specified user name.
The results show this client accessed a service on this server only once on 8/17/2012.

## PARAMETERS

### -ActivityCount
Specifies an array of the number of access requests by a client for a service.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -ChassisSerialNumber
Specifies an array of strings.
Each member contains the UUID of a server.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FirstSeen
Specifies an array of dates, as **DateTime** objects.
A time represents when the client accessed the service for the first time.

```yaml
Type: DateTime[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LastSeen
Specifies an array of dates, as **DateTime** objects.
A time represents when the client accessed the service for the most recent time.

```yaml
Type: DateTime[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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

### -UUID
Specifies an UUID for the server.
UAL gets this identifier from the SMBIOS.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Username
Specifies an array of user names that request a service.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-UalDailyDeviceAccess](./Get-UalDailyDeviceAccess.md)

[Get-UalOverview](./Get-UalOverview.md)

[Get-UalServerDevice](./Get-UalServerDevice.md)

[Get-UalDeviceAccess](./Get-UalDeviceAccess.md)

