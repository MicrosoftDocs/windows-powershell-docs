---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Set-Partition

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByNumberAttributes (Default)
```
Set-Partition [-IsReadOnly <Boolean>] [-NoDefaultDriveLetter <Boolean>] [-IsActive <Boolean>]
 [-IsHidden <Boolean>] [-IsShadowCopy <Boolean>] [-IsDAX <Boolean>] [-MbrType <UInt16>] [-GptType <String>]
 [-DiskNumber] <UInt32> [-PartitionNumber] <UInt32> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObjectAccessPath
```
Set-Partition -InputObject <CimInstance[]> [-NewDriveLetter <Char>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObject
```
Set-Partition -InputObject <CimInstance[]> [-IsOffline <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObjectAttributes
```
Set-Partition -InputObject <CimInstance[]> [-IsReadOnly <Boolean>] [-NoDefaultDriveLetter <Boolean>]
 [-IsActive <Boolean>] [-IsHidden <Boolean>] [-IsShadowCopy <Boolean>] [-IsDAX <Boolean>] [-MbrType <UInt16>]
 [-GptType <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByDriveLetterAttributes
```
Set-Partition [-IsReadOnly <Boolean>] [-NoDefaultDriveLetter <Boolean>] [-IsActive <Boolean>]
 [-IsHidden <Boolean>] [-IsShadowCopy <Boolean>] [-IsDAX <Boolean>] [-MbrType <UInt16>] [-GptType <String>]
 -DriveLetter <Char> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByIdAttributes
```
Set-Partition [-IsReadOnly <Boolean>] [-NoDefaultDriveLetter <Boolean>] [-IsActive <Boolean>]
 [-IsHidden <Boolean>] [-IsShadowCopy <Boolean>] [-IsDAX <Boolean>] [-MbrType <UInt16>] [-GptType <String>]
 -DiskId <String> -Offset <UInt64> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByIdAccessPath
```
Set-Partition -DiskId <String> -Offset <UInt64> [-NewDriveLetter <Char>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ById
```
Set-Partition -DiskId <String> -Offset <UInt64> [-IsOffline <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByDriveLetterAccessPath
```
Set-Partition -DriveLetter <Char> [-NewDriveLetter <Char>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByDriveLetter
```
Set-Partition -DriveLetter <Char> [-IsOffline <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByNumberAccessPath
```
Set-Partition [-DiskNumber] <UInt32> [-PartitionNumber] <UInt32> [-NewDriveLetter <Char>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByNumber
```
Set-Partition [-DiskNumber] <UInt32> [-PartitionNumber] <UInt32> [-IsOffline <Boolean>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
{{ Fill in the Description }}

## EXAMPLES

### Example 1
```powershell
PS C:\> {{ Add example code here }}
```

{{ Add example description here }}

## PARAMETERS

### -AsJob
{{ Fill AsJob Description }}

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
{{ Fill CimSession Description }}

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

### -DiskId
{{ Fill DiskId Description }}

```yaml
Type: String
Parameter Sets: ByIdAttributes, ByIdAccessPath, ById
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskNumber
{{ Fill DiskNumber Description }}

```yaml
Type: UInt32
Parameter Sets: ByNumberAttributes, ByNumberAccessPath, ByNumber
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DriveLetter
{{ Fill DriveLetter Description }}

```yaml
Type: Char
Parameter Sets: ByDriveLetterAttributes, ByDriveLetterAccessPath, ByDriveLetter
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -GptType
{{ Fill GptType Description }}

```yaml
Type: String
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByDriveLetterAttributes, ByIdAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
{{ Fill InputObject Description }}

```yaml
Type: CimInstance[]
Parameter Sets: ByObjectAccessPath, ByObject, ByObjectAttributes
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsActive
{{ Fill IsActive Description }}

```yaml
Type: Boolean
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByDriveLetterAttributes, ByIdAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsDAX
{{ Fill IsDAX Description }}

```yaml
Type: Boolean
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByDriveLetterAttributes, ByIdAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsHidden
{{ Fill IsHidden Description }}

```yaml
Type: Boolean
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByDriveLetterAttributes, ByIdAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsOffline
{{ Fill IsOffline Description }}

```yaml
Type: Boolean
Parameter Sets: ByObject, ById, ByDriveLetter, ByNumber
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsReadOnly
{{ Fill IsReadOnly Description }}

```yaml
Type: Boolean
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByDriveLetterAttributes, ByIdAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsShadowCopy
{{ Fill IsShadowCopy Description }}

```yaml
Type: Boolean
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByDriveLetterAttributes, ByIdAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MbrType
{{ Fill MbrType Description }}

```yaml
Type: UInt16
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByDriveLetterAttributes, ByIdAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NewDriveLetter
{{ Fill NewDriveLetter Description }}

```yaml
Type: Char
Parameter Sets: ByObjectAccessPath, ByIdAccessPath, ByDriveLetterAccessPath, ByNumberAccessPath
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoDefaultDriveLetter
{{ Fill NoDefaultDriveLetter Description }}

```yaml
Type: Boolean
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByDriveLetterAttributes, ByIdAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Offset
{{ Fill Offset Description }}

```yaml
Type: UInt64
Parameter Sets: ByIdAttributes, ByIdAccessPath, ById
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartitionNumber
{{ Fill PartitionNumber Description }}

```yaml
Type: UInt32
Parameter Sets: ByNumberAttributes, ByNumberAccessPath, ByNumber
Aliases: Number

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
{{ Fill ThrottleLimit Description }}

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
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

### System.String

### System.UInt64

### System.Char

### System.UInt32

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
