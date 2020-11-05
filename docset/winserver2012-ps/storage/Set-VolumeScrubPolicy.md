---
external help file: Storage2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: A7EAF6F1-18A0-4A62-889D-5EA5973EA12C
manager: dansimp
---

# Set-VolumeScrubPolicy

## SYNOPSIS

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-VolumeScrubPolicy [-DriveLetter] <Char[]> [[-Enable] <Boolean>] [-AsJob] [-CimSession <CimSession[]>]
 [-PassThru] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Set-VolumeScrubPolicy [[-Enable] <Boolean>] [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-ThrottleLimit <Int32>] -Path <String[]>
```

### UNNAMED_PARAMETER_SET_3
```
Set-VolumeScrubPolicy [[-Enable] <Boolean>] [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-ThrottleLimit <Int32>] -ObjectId <String[]>
```

### UNNAMED_PARAMETER_SET_4
```
Set-VolumeScrubPolicy [[-Enable] <Boolean>] [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]>
```

### UNNAMED_PARAMETER_SET_5
```
Set-VolumeScrubPolicy [[-Enable] <Boolean>] [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-ThrottleLimit <Int32>] -FileSystemLabel <String[]>
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

### -Enable


```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileSystemLabel


```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
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
Parameter Sets: UNNAMED_PARAMETER_SET_4
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru


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

