---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MsftUal_DailyUserAccess.cdxml-help.xml
Module Name: UserAccessLogging
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/useraccesslogging/get-ualdailyuseraccess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UalDailyUserAccess
---

# Get-UalDailyUserAccess

## SYNOPSIS
Gets UAL records for client requests per user for each day.

## SYNTAX

```
Get-UalDailyUserAccess [-ProductName <String[]>] [-RoleName <String[]>] [-RoleGuid <String[]>]
 [-Username <String[]>] [-AccessDate <DateTime[]>] [-AccessCount <UInt32[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-UalDailyUserAccess** cmdlet gets User Access Logging (UAL) records for client requests by user for services on a server.
Use the *CimSession* parameter to run the cmdlet on a remote server.

This cmdlet organizes information by user for each day.
For each user that accesses a service on a server, the cmdlet returns a record that specifies the user, the server role that the client requested, and the name of the server product.
The record also includes the date that the user accessed the service and how many times the user accessed the service during that day.

For more information about UAL, see the [User Access Logging Overview](https://technet.microsoft.com/library/hh849634.aspx) topic in the TechNet library at http://technet.microsoft.com/library/hh849634.aspx.

## EXAMPLES

### Example 1: Get daily usage for a specific user
```
PS C:\>Get-UalDailyUserAccess -Username "western\sarahjones"
AccessCount    : 1

AccessDate     : 8/17/2012

UserName       : western\sarahjones

ProductName    : Windows Server 2012 Datacenter

RoleGuid       : 10a9226f-50ee-49d8-a393-9a501d47ce04

RoleName       : File Server

PSComputerName :


AccessCount    : 1

AccessDate     : 8/27/2012

UserName       : western\sarahjones

ProductName    : Windows Server 2012 Datacenter

RoleGuid       : 10a9226f-50ee-49d8-a393-9a501d47ce04

RoleName       : File Server

PSComputerName :
```

This command gets the UAL records for a client user with a specified name.
The results show access requests on sample dates 8/17/2012 and 8/27/2012.

## PARAMETERS

### -AccessCount
Specifies an array of the number of access requests by a client for a service during a single day.

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

### -AccessDate
Specifies an array of dates, as **DateTime** objects.
A client can make one or more access requests per day.

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

### -ProductName
Specifies an array of names of products.
The installed role or specific product in the request is a component of this product.

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

### -RoleGuid
Specifies an array of GUIDs for roles that clients access.

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

### -RoleName
Specifies an array of names for roles that clients access.

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

[Get-UalDailyAccess](./Get-UalDailyAccess.md)

[Get-UalDailyDeviceAccess](./Get-UalDailyDeviceAccess.md)

[Get-UalDeviceAccess](./Get-UalDeviceAccess.md)

[Get-UalUserAccess](./Get-UalUserAccess.md)

