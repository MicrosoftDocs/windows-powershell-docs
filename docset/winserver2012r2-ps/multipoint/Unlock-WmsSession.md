---
external help file: WmsCmdlets.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/06/2017
online version: https://docs.microsoft.com/powershell/module/multipoint/unlock-wmssession?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Unlock-WmsSession
---

# Unlock-WmsSession

## SYNOPSIS
Unblocks a user for desktop use.

## SYNTAX

```
Unlock-WmsSession -SessionId <UInt32> [-TimeoutInSecond <Int32>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The Unlock-WmsSession cmdlet unblocks a user for desktop use.

## EXAMPLES

### Example
```
PS C:\> Unlock-WmsSession -SessionIdList "3"
No output.
```

Station is unblocked.

Note: If a Multipoint Manager session is running, and the state of the sessions was Block All, the Multipoint Manager may block the station again.

### 1:
```
PS C:\>
```

## PARAMETERS

### -SessionId
Specifies a Remote Desktop Session (RDS) using SessionID.

```yaml
Type: UInt32
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

