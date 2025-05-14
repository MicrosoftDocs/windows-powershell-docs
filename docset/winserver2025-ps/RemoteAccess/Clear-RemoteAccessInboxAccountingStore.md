---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_RemoteAccessInboxAccountingStore_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/clear-remoteaccessinboxaccountingstore?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Clear-RemoteAccessInboxAccountingStore
---

# Clear-RemoteAccessInboxAccountingStore

## SYNOPSIS
Clears the inbox accounting store for the specified time period.

## SYNTAX

```
Clear-RemoteAccessInboxAccountingStore [-ComputerName <String>] [[-StartDateTime] <DateTime>]
 [[-EndDateTime] <DateTime>] [-Force] [-PassThru] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Clear-RemoteAccessInboxAccountingStore** cmdlet clears the inbox accounting store for the specified time period.

The store for inbox accounting resides locally on every Remote Access server and the clearing operation happens at the server level.
Therefore this cmdlet is not impacted by a multi-site deployment.

Note: If neither a start date nor an end date is specified, then the entire inbox accounting store is cleared.

When a store is cleared more space becomes available to record accounting data.

This cmdlet can be used to clear portions of the store even if inbox accounting is Disabled.
This is because the store exists even when inbox accounting is later disabled.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>$startdate = Get-Date -Date "1/1/2011"



PS C:\>$startdate
Saturday, January 01, 2011 12:00:00AM


PS C:\>$enddate = Get-Date -Date "1/3/2011"



PS C:\>$enddate
Tuesday, March 01, 2011 12:00:00AM


PS C:\>Clear-RemoteAccessInboxAccountingStore -StartDateTime $startdate -EndDateTime $enddate -PassThru
Confirm
Emptying the store will delete the accounting data in accordance with the specified settings. Do you want to continue?

[Y] Yes  [N] No  [S] Suspend  [?] Help  (default is ꞌYꞌ): Y

InboxAccountingStatus      : Enabled
StoreLimit                 : 12m
StoreUsedBytes             : 12648448
StoreUsedBytesInPercentage : 0.2944946
StoreFreeBytes             : 4282318848
StoreFreeBytesInPercentage : 99.70551
StoreFirstRecordDate       : 12/31/2010 11:17:00 PM
StoreLastRecordDate        : 8/9/2011 12:17:00 AM
```

This example deletes the data between the specific dates provided.
The remaining data will be preserved.

### EXAMPLE 2
```
PS C:\>Clear-RemoteAccessInboxAccountingStore
Confirm
Emptying the store will delete the accounting data in accordance with the specified settings. Do you want to continue?

[Y] Yes  [N] No  [S] Suspend  [?] Help  (default is ꞌYꞌ): Y

InboxAccountingStatus      : Enabled
StoreLimit                 : 12m
StoreUsedBytes             : 12648448
StoreUsedBytesInPercentage : 0.2944946
StoreFreeBytes             : 4282318848
StoreFreeBytesInPercentage : 99.70551
StoreFirstRecordDate       : 12/29/2011 4:39:41 PM
StoreLastRecordDate        : 12/29/2011 4:39:41 PM
```

This example clears the accounting store and removes all data.

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
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the remote access server computer specific tasks should be run.
When this parameter is specified the store residing on that Remote Access server is cleared.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndDateTime
Specifies the time duration for which the store should be emptied and indicates the end date.
If no start date is specified, then the time stamp of the last record entry in the accounting store is used by default.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

When this parameter is specified, the cmdlet assumes user confirmation for the clearing of the store.

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

### -PassThru
Returns an object representing the item with which you are working.
By default, this cmdlet does not generate any output.

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

### -StartDateTime
Specifies the time duration for which the store should be emptied and indicates the start date.
If no start date is specified, then the time stamp of the first record entry in the accounting store is used by default.

```yaml
Type: DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.DateTime

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#RemoteAccessInboxAccounting

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The RemoteAccessInboxAccounting object consists of the following properties:

 -- Status of inbox accounting (**Enabled** or **Disabled**).

 -- Time span of the store.

 -- Number of used bytes.

 -- Percentage of used bytes.

 -- Number of free bytes.

 -- Percentage of free bytes.

 -- Time stamp of the first record in the database.

 -- Time stamp of the last record in the database.

## NOTES

## RELATED LINKS

[Get-Date](https://go.microsoft.com/fwlink/p/?LinkId=113313)

[Set-RemoteAccessInboxAccountingStore](./Set-RemoteAccessInboxAccountingStore.md)

