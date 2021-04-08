---
author: Kateyanne
external help file: Storage2_Cmdlets.xml
manager: dansimp
Module Name: Storage
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/storage/get-supportedclustersizes?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-SupportedClusterSizes

## SYNOPSIS

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-SupportedClusterSizes [-DriveLetter] <Char[]> [-AsJob] [-CimSession <CimSession[]>] [-FileSystem <String>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-SupportedClusterSizes [-AsJob] [-CimSession <CimSession[]>] [-FileSystem <String>] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]>
```

### UNNAMED_PARAMETER_SET_3
```
Get-SupportedClusterSizes [-AsJob] [-CimSession <CimSession[]>] [-FileSystem <String>] [-ThrottleLimit <Int32>]
 -Path <String[]>
```

### UNNAMED_PARAMETER_SET_4
```
Get-SupportedClusterSizes [-AsJob] [-CimSession <CimSession[]>] [-FileSystem <String>] [-ThrottleLimit <Int32>]
 -ObjectId <String[]>
```

### UNNAMED_PARAMETER_SET_5
```
Get-SupportedClusterSizes [-AsJob] [-CimSession <CimSession[]>] [-FileSystem <String>] [-ThrottleLimit <Int32>]
 -FileSystemLabel <String[]>
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

### -FileSystem


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
Parameter Sets: UNNAMED_PARAMETER_SET_2
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
Parameter Sets: UNNAMED_PARAMETER_SET_4
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
Parameter Sets: UNNAMED_PARAMETER_SET_3
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

