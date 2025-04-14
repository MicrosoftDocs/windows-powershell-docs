---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MultiPoint.dll-Help.xml
Module Name: MultiPoint
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/multipoint/set-wmsweblimiting?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WmsWebLimiting
---

# Set-WmsWebLimiting

## SYNOPSIS
Configures web limiting for standard user sessions.

## SYNTAX

### AllowList
```
Set-WmsWebLimiting [-Allow] [-Sites] <String[]> [-Server <String>] [<CommonParameters>]
```

### BlockList
```
Set-WmsWebLimiting [-Block] [-Sites] <String[]> [-Server <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WmsWebLimiting** cmdlet configures web limiting for standard user sessions on the current Windows MultiPoint Server system.

## EXAMPLES

### Example 1: Block access to web sites
```
PS C:\> Set-WmsWebLimiting -Sites "www.test.com", "www.test1.com" -Block
```

This command blocks access to the specified URLs.

## PARAMETERS

### -Allow
Indicates that this operation allows the specified web sites.

```yaml
Type: SwitchParameter
Parameter Sets: AllowList
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Block
Indicates that this operation blocks the specified web sites.

```yaml
Type: SwitchParameter
Parameter Sets: BlockList
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Server
Specifies the fully qualified host name of the MultiPoint Server that is the target of the command.
The default is localhost.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ComputerName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Sites
Specifies an array of web sites.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String[]

### System.String

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Disable-WmsWebLimiting](./Disable-WmsWebLimiting.md)

[Enable-WmsWebLimiting](./Enable-WmsWebLimiting.md)

[Get-WmsWebLimiting](./Get-WmsWebLimiting.md)

