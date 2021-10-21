---
description: Moves or copies net intent across different hosts or clusters.
external help file: NetworkAtc-help.xml
Module Name: NetworkATC
ms.date: 10/21/2021
online version: https://docs.microsoft.com/powershell/module/netwnv/copy-netintent?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Copy-NetIntent
---

# Copy-NetIntent

## SYNOPSIS
Moves or copies net intent across different hosts or clusters.

## SYNTAX

### ComputerName (Default)
```
Copy-NetIntent [-Name] <String> [-SourceComputerName] <String> [-DestinationComputerName] <String>
 [-RemoveSource <Boolean>] [<CommonParameters>]
```

### ClusterName
```
Copy-NetIntent [-Name] <String> [-SourceClusterName] <String> [-DestinationClusterName] <String>
 [-RemoveSource <Boolean>] [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### EXAMPLE 1
```
Copy-NetIntent
```

-SourceClusterName / SourceComputerName source for the intent to by copied from
    -DestinationClusterName / DestinationComputerName destination for the intent to be copied to.
    -Name : Name of the intent to be copied over
    -RemoveSource : Indicates if the source needs to be removed after the copy

## PARAMETERS

### -DestinationClusterName
{{ Fill DestinationClusterName Description }}

```yaml
Type: String
Parameter Sets: ClusterName
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationComputerName
{{ Fill DestinationComputerName Description }}

```yaml
Type: String
Parameter Sets: ComputerName
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
{{ Fill Name Description }}

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RemoveSource
{{ Fill RemoveSource Description }}

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceClusterName
{{ Fill SourceClusterName Description }}

```yaml
Type: String
Parameter Sets: ClusterName
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceComputerName
{{ Fill SourceComputerName Description }}

```yaml
Type: String
Parameter Sets: ComputerName
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
The copy & removal operation of the intent is not a transacted operation\`.

## RELATED LINKS
