---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: kenwith
author: kenwith
ms.assetid: 2CA9FE21-8419-4450-A8E0-7A55B0127268
---

# Get-OBJob

## SYNOPSIS
Gets a list of operations from a server as OBJob objects.

## SYNTAX

```
Get-OBJob [[-Previous] <UInt32>] [[-Status] <CBJobStatusFilter>]
```

## DESCRIPTION
The **Get-OBJob** cmdlet gets a list of operations from a server as OBJob\[\] objects.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-OBJob -Previous 5 -Status "Successful"
```

This example returns a list of successful jobs out of the last five jobs performed.

## PARAMETERS

### -Previous
Specifies a previous number of backup or restore operations to query from the backup events.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Filters the jobs based on their status.
The following three values are supported - "All", "Successful" and "Failed".
If this parameter is not used no filtering is performed.
The **Previous** parameter must be specified to use the **Status** parameter.
The Status parameter is restricted to three string inputs.

```yaml
Type: CBJobStatusFilter
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBJob[]

## NOTES

## RELATED LINKS

[Stop-OBJob](./Stop-OBJob.md)

