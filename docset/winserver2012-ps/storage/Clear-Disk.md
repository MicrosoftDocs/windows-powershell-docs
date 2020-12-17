---
external help file: Storage2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 4084251C-5301-45DD-B710-20A7ED67799B
manager: dansimp
---

# Clear-Disk

## SYNOPSIS
Cleans a disk by removing all partition information and un-initializing it, erasing all data on the disk.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Clear-Disk [-Number] <UInt32[]> [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-RemoveData] [-RemoveOEM]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Clear-Disk [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-RemoveData] [-RemoveOEM]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Clear-Disk [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-RemoveData] [-RemoveOEM]
 [-ThrottleLimit <Int32>] -UniqueId <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Clear-Disk [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-RemoveData] [-RemoveOEM]
 [-ThrottleLimit <Int32>] -Path <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Clear-Disk [-AsJob] [-CimSession <CimSession[]>] [-FriendlyName <String[]>] [-PassThru] [-RemoveData]
 [-RemoveOEM] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Clear-Disk** cmdlet clears the disk by removing the partition and volume information.

If the disk contains active data volumes, then the **RemoveData** parameter is required as this will delete all data from the specified disk.
This cmdlet will not clear OEM recovery partitions unless **ForceOEM** parameter is also specified.

## EXAMPLES

### Example 1: Clear a blank disk
```
PS C:\>Clear-Disk -Number 1
```

This example clears disk number one only if it does not contain both data or OEM partitions.

### Example 2: Clear a disk with data partitions
```
PS C:\>Clear-Disk -Number 1 -RemoveData
```

This example clears the disk if it has data partitions, but not if it also has OEM partitions.

### 1: Clear a disk with data and OEM partitions
```
PS C:\>Clear-Disk -Number 1 -RemoveData -RemoveOEM
```

This example clears the disk regardless of whether it contains data or OEM partitions.

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

### -FriendlyName
Specifies a friendly name of the disk to clear.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Specifies the disk object to clear.
Enter a Disk CIM object, which you can get by using the Get-Disk cmdlet.

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

### -Number
Specifies the disk number of the disk on which to perform the clear operation.
For a list of available disks, see the Get-Disk cmdlet.

```yaml
Type: UInt32[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Specifies that the cmdlet should output an object representing a disk.
By default, this cmdlet does not generate any output.

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
Specifies the path of the disk to clear.

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

### -RemoveData
Enables the removal of all of the data on the disk.

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

### -RemoveOEM
Enables the removal of any OEM recovery partitions from the disk.

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

### -UniqueId
Specifies the UniqueID of the disk to clear.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

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
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Disk
You can pipe a Disk object to the **InputObject** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Disk
When you specify the **Passthru** parameter, this cmdlet outputs an object representing the disk that you cleared.

## NOTES

## RELATED LINKS

[Format-Volume](./Format-Volume.md)

[Get-Disk](./Get-Disk.md)

[Initialize-Disk](./Initialize-Disk.md)

[New-Partiton](./New-Partition.md)

[Set-Disk](./Set-Disk.md)

[Update-Disk](./Update-Disk.md)

