---
external help file: Storage2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: D5C2DCD1-0959-455C-A983-EBED0B84C1D9
manager: dansimp
---

# Get-SupportedFileSystems

## SYNOPSIS

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-SupportedFileSystems [-DriveLetter] <Char[]> [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-SupportedFileSystems [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] -Path <String[]>
```

### UNNAMED_PARAMETER_SET_3
```
Get-SupportedFileSystems [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]>
```

### UNNAMED_PARAMETER_SET_4
```
Get-SupportedFileSystems [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 -FileSystemLabel <String[]>
```

### UNNAMED_PARAMETER_SET_5
```
Get-SupportedFileSystems [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] -ObjectId <String[]>
```

## DESCRIPTION

## EXAMPLES

### 1:
```
PS C:\>
```

### 2:
```
PS C:\>
```

## PARAMETERS

### -AsJob


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

### -DriveLetter


```yaml
Type: Char[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -FileSystemLabel


```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject


```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ObjectId


```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path


```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit


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

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

