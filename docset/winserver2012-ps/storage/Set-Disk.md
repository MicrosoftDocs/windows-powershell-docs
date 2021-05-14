---
external help file: Storage2_Cmdlets.xml
Module Name: Storage
online version: https://docs.microsoft.com/powershell/module/storage/set-disk?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-Disk

## SYNOPSIS
Takes a Disk object or unique disk identifiers and a set of attributes, and updates the physical disk on the system.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Set-Disk [-Number] <UInt32> [-AsJob] [-CimSession <CimSession[]>] [-Guid <String>] [-IsReadOnly <Boolean>]
 [-Signature <UInt32>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Set-Disk [-AsJob] [-CimSession <CimSession[]>] [-Guid <String>] [-IsReadOnly <Boolean>] [-Signature <UInt32>]
 [-ThrottleLimit <Int32>] -Path <String>
```

### UNNAMED_PARAMETER_SET_3
```
Set-Disk [-AsJob] [-CimSession <CimSession[]>] [-Guid <String>] [-IsReadOnly <Boolean>] [-Signature <UInt32>]
 [-ThrottleLimit <Int32>] -UniqueId <String>
```

### UNNAMED_PARAMETER_SET_4
```
Set-Disk [-AsJob] [-CimSession <CimSession[]>] [-Guid <String>] [-IsReadOnly <Boolean>] [-Signature <UInt32>]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]>
```

### UNNAMED_PARAMETER_SET_5
```
Set-Disk [-Number] <UInt32> [-AsJob] [-CimSession <CimSession[]>] [-IsOffline <Boolean>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_6
```
Set-Disk [-AsJob] [-CimSession <CimSession[]>] [-IsOffline <Boolean>] [-ThrottleLimit <Int32>] -Path <String>
```

### UNNAMED_PARAMETER_SET_7
```
Set-Disk [-AsJob] [-CimSession <CimSession[]>] [-IsOffline <Boolean>] [-ThrottleLimit <Int32>]
 -UniqueId <String>
```

### UNNAMED_PARAMETER_SET_8
```
Set-Disk [-AsJob] [-CimSession <CimSession[]>] [-IsOffline <Boolean>] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]>
```

### UNNAMED_PARAMETER_SET_9
```
Set-Disk [-Number] <UInt32> [-AsJob] [-CimSession <CimSession[]>] [-PartitionStyle <PartitionStyle>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_10
```
Set-Disk [-AsJob] [-CimSession <CimSession[]>] [-PartitionStyle <PartitionStyle>] [-ThrottleLimit <Int32>]
 -Path <String>
```

### UNNAMED_PARAMETER_SET_11
```
Set-Disk [-AsJob] [-CimSession <CimSession[]>] [-PartitionStyle <PartitionStyle>] [-ThrottleLimit <Int32>]
 -UniqueId <String>
```

### UNNAMED_PARAMETER_SET_12
```
Set-Disk [-AsJob] [-CimSession <CimSession[]>] [-PartitionStyle <PartitionStyle>] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]>
```

## DESCRIPTION
The **Set-Disk** cmdlet takes a Disk object or unique disk identifiers and a set of attributes, and updates the physical disk on the system.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-Disk -Number 5 -IsOffline $False
```

This example takes a disk that is offline and makes it online.

### EXAMPLE 2
```
PS C:\>Set-Disk -Number 5 -IsReadonly $False
```

This example takes a disk that is read-only and makes it writeable.

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

### -Guid
Contains a globally unique ID (GUID).

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Accepts an object from the pipeline as input.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_4, UNNAMED_PARAMETER_SET_8, UNNAMED_PARAMETER_SET_12
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsOffline
Specifies that the disk is offline.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_7, UNNAMED_PARAMETER_SET_8
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsReadOnly
Sets the disk to be read-only, or read-write (read-only = false).
Note: If the disk is set to read-only, then the disk must be set to read-only = false before using this cmdlet to set the **PartitionStyle** parameter.

```yaml
Type: Boolean
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Number
Specifies a disk number on which the cmdlet acts.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_5, UNNAMED_PARAMETER_SET_9
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PartitionStyle
Specifies the type of the partition.
The acceptable values for this parameter are: **MBR** or **GPT**.
The disk must be initialized (such as using theInitialize-Diskhttp://technet.microsoft.com/library/e5369347-7ee0-4cb7-a063-cf1f355d095e cmdlet) and set to read-write (`IsReadOnly $false`) before this cmdlet will work.
The disk must be set to read-only = false before this cmdlet will work.

```yaml
Type: PartitionStyle
Parameter Sets: UNNAMED_PARAMETER_SET_9, UNNAMED_PARAMETER_SET_10, UNNAMED_PARAMETER_SET_11, UNNAMED_PARAMETER_SET_12
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Path
Contains the device instance path.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_6, UNNAMED_PARAMETER_SET_10
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Signature
Contains the signature of the disk.

```yaml
Type: UInt32
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2, UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_4
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
Specifies an ID used to uniquely identify a Disk object in the system.
The ID persists through restarts.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_3, UNNAMED_PARAMETER_SET_7, UNNAMED_PARAMETER_SET_11
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Disk
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Clear-Disk](./Clear-Disk.md)

[Get-Disk](./Get-Disk.md)

[Initialize-Disk](./Initialize-Disk.md)

[Update-Disk](./Update-Disk.md)

