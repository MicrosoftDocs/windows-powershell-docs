---
external help file: UnifiedRA_Cmdlets.xml
Module Name: RemoteAccess
online version: https://docs.microsoft.com/powershell/module/remoteaccess/set-remoteaccessinboxaccountingstore?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-RemoteAccessInboxAccountingStore

## SYNOPSIS
Modifies the size of the inbox accounting store.

## SYNTAX

```
Set-RemoteAccessInboxAccountingStore [-StoreLimit] <String> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-RemoteAccessInboxAccountingStore** cmdlet modifies the size of the inbox accounting store.

The store for inbox accounting resides locally on every Remote Access (RA) server.
When inbox accounting is Enabled for the first time the default size of the store is 12 months on every server.
Any subsequent change to the store size can be done using this cmdlet and the change happens at the server level.
Therefore this cmdlet is not impacted by a multi-site deployment.

This cmdlet can be used to modify store size even if inbox accounting is Disabled.
This is because the store exists even when inbox accounting is later Disabled.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-RemoteAccessInboxAccountingStore -StoreLimit 2y -PassThru
InboxAccountingStatus      : Enabled 
StoreLimit                 : 2y 
StoreUsedBytes             : 12648448 
StoreUsedBytesInPercentage : 0.2944946 
StoreFreeBytes             : 4282318848 
StoreFreeBytesInPercentage : 99.70551 
StoreFirstRecordDate       : 29-11-2011 23:54:59 
StoreLastRecordDate        : 29-12-2011 15:37:45
```

This example changes the inbox store limit from the configured default to store 2 years of data.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the RA server computer specific tasks should be run.
When this parameter is specified the size limit of the store residing on that RA server is modified.

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

### -StoreLimit
Specifies the limit on the amount of accounting data that can be stored, specifically the size of the store, in terms of time.
Following is the format used: \<duration\>\<time unit\>.
The time unit can be day, week, month or year as specified using the characters `d`, `w`, `m`, or `y`.
Such as `100d` means 100 days, `3m` means 3 months, or `2y` means 2 years.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#RemoteAccessInboxAccounting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The RemoteAccessAccountingStore object consists of the following properties: 

 -- The status of inbox accounting (Enabled or Disabled). 

 -- Time span of the store. 

 -- Number of used bytes. 

 -- Percentage of used bytes. 

 -- Number of free bytes. 

 -- Percentage of free bytes. 

 -- Time stamp of the first record in the database. 

 -- Time stamp of the last record in the database.

## NOTES

## RELATED LINKS

[Clear-RemoteAccessInboxAccountingStore](./Clear-RemoteAccessInboxAccountingStore.md)

