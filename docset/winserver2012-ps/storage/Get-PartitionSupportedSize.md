---
external help file: Storage2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
ms.assetid: E4E2A9D1-9E80-463C-BA10-435A45E1040B
manager: dansimp
---

# Get-PartitionSupportedSize

## SYNOPSIS
Returns information on supported partition sizes for the specified Disk object.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-PartitionSupportedSize [[-DiskNumber] <UInt32[]>] [[-PartitionNumber] <UInt32[]>] [-AsJob]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-PartitionSupportedSize [-AsJob] [-CimSession <CimSession[]>] [-DiskId <String[]>] [-Offset <UInt64[]>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-PartitionSupportedSize [-AsJob] [-CimSession <CimSession[]>] [-DriveLetter <Char[]>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_4
```
Get-PartitionSupportedSize [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]>
```

## DESCRIPTION
The **Get-PartitionSupportedSizes** cmdlet returns information on supported partition sizes for the specified Disk object.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-PartitionSupportedSizes -DiskNumber 3 -PartitionNumber 2
MinimumSize                                                 MaximumSize 
-----------                                                 -----------
```

This example is not fully implemented and does not include size values.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

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
Specifies an ID used to identify a disk in the system.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskNumber
Specifies the number of the disk.
The number of the disk on which the partition resides.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DriveLetter
Specifies a letter used to identify a drive or volume in the system.

```yaml
Type: Char[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the Partition object to get.
Enter a Partition CIM object, which you can get by using the Get-Partition cmdlet.

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

### -Offset
Specifies the starting offset, in bytes.

```yaml
Type: UInt64[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartitionNumber
Specifies the number of the partition.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: Number

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Partition
You can pipe a Partition object to the **InputObject** parameter.

## OUTPUTS

### System.UInt64

## NOTES

## RELATED LINKS

[Get-Partition](./Get-Partition.md)

