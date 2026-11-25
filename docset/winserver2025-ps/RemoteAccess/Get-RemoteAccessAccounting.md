---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RemoteAccessAccounting_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/get-remoteaccessaccounting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-RemoteAccessAccounting
---

# Get-RemoteAccessAccounting

## SYNOPSIS
Displays the accounting configuration for Remote Access, such as the different types of accounting that are enabled and the respective configuration.

## SYNTAX

```
Get-RemoteAccessAccounting [-ComputerName <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-RemoteAccessAccounting** cmdlet displays the accounting configuration for Remote Access, such as the different types of accounting that are enabled and the respective configuration.

The accounting configuration is applicable globally, such as the enabled state of a particular kind of accounting and the resulting enabled state on all DA servers in the corporate network.
The associated configuration is also applicable for all computers in the corporate network.

 -- All Remote Access servers have the same configured Accounting RADIUS servers.

 -- The default limit set for the inbox accounting store size is the same on all Remote Access servers.

Therefore, this cmdlet is not impacted by a multi-site deployment.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-RemoteAccessAccounting -ComputerName Edge2
RadiusAccountingStatus          : Disabled
RemoteRadiusServerList          :
InboxAccountingStatus           : Enabled
InboxStoreLimit                 : 12m
InboxStoreUsedBytes             : 12648448
InboxStoreUsedBytesInPercentage : 0.29449462890625
InboxStoreFreeBytes             : 4282318848
InboxStoreFreeBytesInPercentage : 99.7055053710938
InboxStoreFirstRecordDate       : 11/14/2011 6:53:24 PM
InboxStoreLastRecordDate        : 11/22/2011 12:26:59 PM
```

This example retrieves accounting status for a server configured for Inbox Accounting named edge2.
Inbox accounting is being used and about `99.71`% of inbox accounting store is free.
The accounting is configured to store 12 months of data as shown by InboxStoreLimit.

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

### -ComputerName
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the Remote Access server computer specific tasks should be run.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#RemoteAccessAccounting

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The RemoteAccessAccounting object consists of the following properties:

 -- The status of RADIUS accounting (Disabled, Windows, ExternalRadius) and the list of RADIUS servers in the case of ExternalRadius accounting.
If there is no external radius accounting enabled, then the list of Radius servers is empty.

 -- The status of inbox accounting (Enabled, Disabled) and its properties.

 -- Time span of the store.

 -- Number of used bytes.

 -- Percentage of used bytes.

 -- Number of free bytes.

 -- Percentage of free bytes.

 -- Time stamp of the first record in the database.

 -- Time stamp of the last record in the database.

## NOTES

## RELATED LINKS

[Set-RemoteAccessAccounting](./Set-RemoteAccessAccounting.md)

