---
external help file: WmsCmdlets.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/06/2017
online version: https://docs.microsoft.com/powershell/module/multipoint/remove-wmsuser?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-WmsUser
---

# Remove-WmsUser

## SYNOPSIS
Removes a local user from the current Windows MultiPoint Server system.

## SYNTAX

```
Remove-WmsUser -Name <String> [-TimeoutInSecond <Int32>] [<CommonParameters>]
```

## DESCRIPTION
The Remove-WmsUser cmdlet removes a local user from the current Windows MultiPoint Server system.

## EXAMPLES

### Example
```
PS C:\> Remove-WmsUser -Name "Student1"
No output.
```

The specified username will be deleted.

### 1:
```
PS C:\>
```

## PARAMETERS

### -Name
The name of the user account to be deleted.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -TimeoutInSecond
The timeout value in seconds before the operation is aborted.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

