---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MsftUal_Overview.cdxml-help.xml
Module Name: UserAccessLogging
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/useraccesslogging/get-ualoverview?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-UalOverview
---

# Get-UalOverview

## SYNOPSIS
Gets information about products registered with UAL.

## SYNTAX

```
Get-UalOverview [-ProductName <String[]>] [-RoleName <String[]>] [-GUID <String[]>] [-FirstSeen <DateTime[]>]
 [-LastSeen <DateTime[]>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-UalOverview** cmdlet gets information about products registered with User Access Logging (UAL) on a server.
Use the **CimSession** parameter to run the cmdlet on a remote server.

This cmdlet returns records that specify a server role and the name of the server product.
Each record also includes the first time a client accessed the service and a most recent time a client accessed the service.
Only server roles that have data for first client request and most recent client request provide records for this cmdlet.

You can specify parameter values to narrow the records that this cmdlet returns.
For instance, you can get records for only a specified role.

For more information about UAL, see the [User Access Logging Overview](https://technet.microsoft.com/library/hh849634.aspx) topic in the TechNet library at http://technet.microsoft.com/library/hh849634.aspx.

## EXAMPLES

### Example 1: Get overview information
```
PS C:\>Get-UalOverview -RoleName "DHCP Server"



FirstSeen      : 8/17/2012 11:33:04 AM

GUID           : 48eed6b2-9cdc-4358-b5a5-8dea3b2f3f6a

LastSeen       : 9/26/2012 10:15:28 AM

ProductName    : Windows Server 2012 Datacenter

RoleName       : DHCP Server

PSComputerName :
```

This command gets an overview record for the DHCP Server role on the local system.

## PARAMETERS

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
A time represents when a client accessed the service for the first time.

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

### -GUID
Specifies an array of GUIDs for roles that clients can access.

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

### -LastSeen
Specifies an array of dates, as **DateTime** objects.
A time represents when a client accessed the service for the most recent time.

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
The installed role or specific product is a component of this product.

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
Specifies an array of names for roles that clients can access.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-Ual](./Get-Ual.md)

[Get-UalDeviceAccess](./Get-UalDeviceAccess.md)

[Get-UalUserAccess](./Get-UalUserAccess.md)

