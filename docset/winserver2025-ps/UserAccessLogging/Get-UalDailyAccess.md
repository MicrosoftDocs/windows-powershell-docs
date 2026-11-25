---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MsftUal_DailyAccess.cdxml-help.xml
Module Name: UserAccessLogging
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/useraccesslogging/get-ualdailyaccess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UalDailyAccess
---

# Get-UalDailyAccess

## SYNOPSIS
Gets UAL records of client requests for each day.

## SYNTAX

```
Get-UalDailyAccess [-ProductName <String[]>] [-RoleName <String[]>] [-RoleGuid <String[]>]
 [-TenantIdentifier <String[]>] [-IPAddress <String[]>] [-Username <String[]>] [-AccessDate <DateTime[]>]
 [-AccessCount <UInt32[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-UalDailyAccess** cmdlet gets User Access Logging (UAL) records for client requests by device for services on a server.
This cmdlet provides information by day.
Use the *CimSession* parameter to run the cmdlet on a remote server.

For each client that accesses a service, the cmdlet returns a record that specifies IP address of the device, the user name, the server role that the client requested, and the name of the server product.
If the service uses a tenant client, the record includes a tenant identifier.
The record also includes the date that the client accessed the service and how many times the client accessed the service during that day.

You can specify parameter values to narrow the records that this cmdlet returns.
For instance, you can get records for only a specified IP address, user name, or role.

For more information about UAL, see the [User Access Logging Overview](https://technet.microsoft.com/library/hh849634.aspx) topic in the TechNet library at http://technet.microsoft.com/library/hh849634.aspx.

## EXAMPLES

### Example 1: Get daily access for specific IP address
```
PS C:\>Get-UalDailyAccess -IPAddress 10.17.44.6

AccessCount      : 2

AccessDate       : 9/19/2012

IPAddress        : 10.17.44.6

UserName         : western\_sersvc

TenantIdentifier : 00000000-0000-0000-0000-000000000000

ProductName      : Windows Server 2012 Datacenter

RoleGuid         : 10a9226f-50ee-49d8-a393-9a501d47ce04

RoleName         : File Server

PSComputerName   :



AccessCount      : 2

AccessDate       : 9/26/2012

IPAddress        : 10.17.44.6

UserName         : western\_sersvc

TenantIdentifier : 00000000-0000-0000-0000-000000000000

ProductName      : Windows Server 2012 Datacenter

RoleGuid         : 10a9226f-50ee-49d8-a393-9a501d47ce04

RoleName         : File Server

PSComputerName   :
```

This command gets UAL daily access requests for a client with the specified IP address.
This request returns two client request objects.

## PARAMETERS

### -AccessCount
Specifies an array of the number of access requests by a client during a single day.

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
A client can make one or more access requests per date.

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

### -IPAddress
Specifies an array of IP addresses for clients that request a service.

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

### -TenantIdentifier
Specifies an array of GUIDs.
Each GUID identifies a tenant associated with the client of an installed role or product, if a tenant GUID exists.

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

[Get-UalDailyDeviceAccess](./Get-UalDailyDeviceAccess.md)

[Get-UalDailyUserAccess](./Get-UalDailyUserAccess.md)

[Get-UalDeviceAccess](./Get-UalDeviceAccess.md)

[Get-UalUserAccess](./Get-UalUserAccess.md)

