---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MsftUal_UserAccess.cdxml-help.xml
Module Name: UserAccessLogging
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/useraccesslogging/get-ualuseraccess?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UalUserAccess
---

# Get-UalUserAccess

## SYNOPSIS
Gets UAL records of client requests per user.

## SYNTAX

```
Get-UalUserAccess [-ProductName <String[]>] [-RoleName <String[]>] [-RoleGuid <String[]>]
 [-TenantIdentifier <String[]>] [-Username <String[]>] [-ActivityCount <UInt32[]>] [-FirstSeen <DateTime[]>]
 [-LastSeen <DateTime[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-UalUserAccess** cmdlet gets User Access Logging (UAL) records for client requests, by user, for services on a server.
Use the *CimSession* parameter to run the cmdlet on a remote server.

This cmdlet organizes information by user.
For each user that accesses a service on a server, the cmdlet returns a record that specifies the user, the server role that the client requested, and the name of the server product.
If the service uses a tenant client, the record includes a tenant identifier.
The record also includes the first time the client accessed the service, the most recent time the client accessed the service, and the total number of times the client accessed the service.

You can specify parameter values to narrow the records that this cmdlet returns.
For instance, you can get records for only a specified user or role.

For more information about UAL, see the [User Access Logging Overview](https://technet.microsoft.com/library/hh849634.aspx) topic in the TechNet library at http://technet.microsoft.com/library/hh849634.aspx.

## EXAMPLES

### Example 1: Get access information for a specific user
```
PS C:\>Get-UalUserAccess -Username "western\sarahjones"
ActivityCount    : 30

FirstSeen        : 8/22/2012 12:15:35 AM

LastSeen         : 9/29/2012 10:41:46 AM

ProductName      : Windows Server 2012 Datacenter

RoleGuid         : 10a9226f-50ee-49d8-a393-9a501d47ce04

RoleName         : File Server

TenantIdentifier : 00000000-0000-0000-0000-000000000000

UserName         : western\sarahjones

PSComputerName   :
```

This command gets the UAL records for a client user with a specified name.
The results show a single service that the user accesses for the first time on 8/22/2012 and most recently on 9/29/2012.

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
A time represents when the client most recently accessed the service.

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
Each GUID identifies a tenant client of an installed role or product, if a tenant client exists.

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

[Get-UalDailyUserAccess](./Get-UalDailyUserAccess.md)

[Get-UalDeviceAccess](./Get-UalDeviceAccess.md)

