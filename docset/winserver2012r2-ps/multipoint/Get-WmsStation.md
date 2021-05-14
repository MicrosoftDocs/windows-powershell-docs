---
external help file: WmsCmdlets.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/06/2017
online version: https://docs.microsoft.com/powershell/module/multipoint/get-wmsstation?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WmsStation
---

# Get-WmsStation

## SYNOPSIS
Returns station information.

## SYNTAX

```
Get-WmsStation [-SerializeString] [-Id <UInt32>] [-TimeoutInSecond <Int32>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The Get-WmsStation cmdlet returns station information for the specified station.
If no station is specified, it returns station information for all stations.

## EXAMPLES

### Example
```
PS C:\> Get-WmsStation
Id                : 1

Name              : 1

IsAutoLogOn       : False

IsSplit           : False

CollabId          : 0

AutoLogOnUserName : 

AutoLogOnPassword : 

Status            : SS_Active

DeviceTypes       : {DT_Keyboard, DT_Mouse, DT_Audio, DT_Image...} 

DeviceCounts      : {1, 0, 0, 0...} 

ComputerName      : Test1

SessionId         : 3
```

The Get-WmsStation cmdlet returns all MultiPoint Server station information, along with the RDS Session ID, if a session is associated with it. 

If no session is associated with the station, 4294967295 will be returned as the session ID.

### 1:
```
PS C:\>
```

## PARAMETERS

### -Id
Specifies a Remote Desktop Session (RDS) using SessionID.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SerializeString
Returns data in XML format.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

###  
Returns WmsStation collection as PSObject collection.

## NOTES

## RELATED LINKS

