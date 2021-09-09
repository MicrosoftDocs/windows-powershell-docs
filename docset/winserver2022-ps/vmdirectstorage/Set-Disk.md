---
external help file: VMDirectStorage-help.xml
Module Name: VMDirectStorage
online version:
schema: 2.0.0
---

# Set-Disk

## SYNOPSIS
{{ Fill in the Synopsis }}

## SYNTAX

### ByNumberAttributes (Default)
```
Set-Disk [-Number] <UInt32> [-IsReadOnly <Boolean>] [-Signature <UInt32>] [-Guid <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectAttributes
```
Set-Disk -InputObject <CimInstance[]> [-IsReadOnly <Boolean>] [-Signature <UInt32>] [-Guid <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObject
```
Set-Disk -InputObject <CimInstance[]> [-IsOffline <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByObjectConvertStyle
```
Set-Disk -InputObject <CimInstance[]> [-PartitionStyle <PartitionStyle>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByNumberConvertStyle
```
Set-Disk [-PartitionStyle <PartitionStyle>] [-Number] <UInt32> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByPathConvertStyle
```
Set-Disk [-PartitionStyle <PartitionStyle>] -Path <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByIdConvertStyle
```
Set-Disk [-PartitionStyle <PartitionStyle>] -UniqueId <String> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByIdAttributes
```
Set-Disk -UniqueId <String> [-IsReadOnly <Boolean>] [-Signature <UInt32>] [-Guid <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ById
```
Set-Disk -UniqueId <String> [-IsOffline <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByPathAttributes
```
Set-Disk -Path <String> [-IsReadOnly <Boolean>] [-Signature <UInt32>] [-Guid <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByPath
```
Set-Disk -Path <String> [-IsOffline <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

### ByNumber
```
Set-Disk [-Number] <UInt32> [-IsOffline <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
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

### -Guid
{{ Fill Guid Description }}

```yaml
Type: String
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByIdAttributes, ByPathAttributes
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
Parameter Sets: ByObjectAttributes, ByObject, ByObjectConvertStyle
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsOffline
{{ Fill IsOffline Description }}

```yaml
Type: Boolean
Parameter Sets: ByObject, ById, ByPath, ByNumber
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
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByIdAttributes, ByPathAttributes
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Number
{{ Fill Number Description }}

```yaml
Type: UInt32
Parameter Sets: ByNumberAttributes, ByNumberConvertStyle, ByNumber
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartitionStyle
{{ Fill PartitionStyle Description }}

```yaml
Type: PartitionStyle
Parameter Sets: ByObjectConvertStyle, ByNumberConvertStyle, ByPathConvertStyle, ByIdConvertStyle
Aliases:
Accepted values: Unknown, MBR, GPT

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
{{ Fill Path Description }}

```yaml
Type: String
Parameter Sets: ByPathConvertStyle, ByPathAttributes, ByPath
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Signature
{{ Fill Signature Description }}

```yaml
Type: UInt32
Parameter Sets: ByNumberAttributes, ByObjectAttributes, ByIdAttributes, ByPathAttributes
Aliases:

Required: False
Position: Named
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

### -UniqueId
{{ Fill UniqueId Description }}

```yaml
Type: String
Parameter Sets: ByIdConvertStyle, ByIdAttributes, ById
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

### System.String

### System.UInt32

## OUTPUTS

### System.Object
## NOTES

## RELATED LINKS
