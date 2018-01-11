---
external help file: OnlineBackup_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 0CC1B932-074B-4C46-AFA7-0AD6CB31246B
---

# Get-OBRecoverableItem

## SYNOPSIS
Gets the array of OBRecoverableItem objects associated with the server.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-OBRecoverableItem [[-SearchString] <String>] [-Location] <String> [-RecoveryPoint] <CBRecoverableItem>
 [[-PagingContext] <CBPagingContext>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-OBRecoverableItem [-ParentItem] <CBRecoverableItem> [[-PagingContext] <CBPagingContext>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-OBRecoverableItem [-Source] <CBRecoverableSource>
```

## DESCRIPTION
The **Get-OBRecoverableItem** cmdlet gets the list of OBRecoverableItem\[\] objects associated with the specified mob_name_1 server (OBServer object).
The OBRecoverableItem\[\] objects define what items will be recovered from the list of backup items.

ps_mob_user_group_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-OBRecoverableSource | Where-Object -FilterScript {$_.FriendlyName -like "C*"} | Get-OBRecoverableItem



PS C:\>For($i = 0; $i -Lt $sources.Length; $i++) 
{ 
Get-OBRecoverableItem -Source $sources[$i] 
}
```

This example returns a recoverable item from source.

### EXAMPLE 2
```
PS C:\>$parents = Get-OBRecoverableSource | Where-Object -FilterScript {$_.FriendlyName -like "C*"} | Get-OBRecoverableItem



PS C:\>Get-OBRecoverableItem -SearchString stringToSearch* -Location R:\ -RecoveryPoint $parents[0]
```

This example returns a recoverable item based on a search criteria.

### EXAMPLE 3
```
PS C:\>$pc = New-OBPagingContext



PS C:\>$parents = Get-OBRecoverableSource | Where-Object -FilterScript {$_.FriendlyName -like "C*"} | Get-OBRecoverableItem



PS C:\>New-OBPagingContext | Get-OBRecoverableItem -ParentItem $parents[0] -Type FileOnly
```

This example returns a recoverable item based on browse.

## PARAMETERS

### -Location
Specifies the path of the root folder to start searching the OBRecoverableItem\[\] object.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PagingContext
Specifies the OBPagingContext object which contains pagination options to retrieve the OBRecoverableItem\[\] object as part of search, browse, or search and browse.

```yaml
Type: CBPagingContext
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ParentItem
Specifies the parent OBRecoverableItem\[\] object from which to obtain the list of one or more child OBRecoverableItem\[\] objects as part of Recovery.

```yaml
Type: CBRecoverableItem
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -RecoveryPoint
Specifies the RecoveryPoint to get the OBRecoverableItem\[\] object.

```yaml
Type: CBRecoverableItem
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 4
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SearchString
Specifies the file name or pattern to be matched, while searching through the OBRecoverableItem\[\] objects.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Source
Lists all root level OBRecoverableItem\[\] objects of the specified OBRecoverableSource object.

```yaml
Type: CBRecoverableSource
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.Internal.CloudBackup.Commands.OBRecoverableItem[]

## NOTES

## RELATED LINKS

[Where-Object](http://go.microsoft.com/fwlink/?LinkID=113423)

[Get-OBRecoverableSource](./Get-OBRecoverableSource.md)

[New-OBPagingContext](./New-OBPagingContext.md)

