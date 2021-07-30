---
external help file: Storage2_Cmdlets.xml
Module Name: Storage
online version: https://docs.microsoft.com/powershell/module/storage/initialize-disk?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Initialize-Disk

## SYNOPSIS
Initializes a RAW disk for first time use, enabling the disk to be formatted and used to store data.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Initialize-Disk [-Number] <UInt32[]> [-AsJob] [-CimSession <CimSession[]>] [-PartitionStyle <PartitionStyle>]
 [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Initialize-Disk [-AsJob] [-CimSession <CimSession[]>] [-PartitionStyle <PartitionStyle>] [-PassThru]
 [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Initialize-Disk [-AsJob] [-CimSession <CimSession[]>] [-FriendlyName <String[]>]
 [-PartitionStyle <PartitionStyle>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Initialize-Disk [-AsJob] [-CimSession <CimSession[]>] [-PartitionStyle <PartitionStyle>] [-PassThru]
 [-ThrottleLimit <Int32>] -UniqueId <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_5
```
Initialize-Disk [-AsJob] [-CimSession <CimSession[]>] [-PartitionStyle <PartitionStyle>] [-PassThru]
 [-ThrottleLimit <Int32>] -Path <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_6
```
Initialize-Disk [-AsJob] [-CimSession <CimSession[]>] [-PartitionStyle <PartitionStyle>] [-PassThru]
 [-ThrottleLimit <Int32>] [-VirtualDisk <CimInstance>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Initialize-Disk** cmdlet initializes a Disk object with the RAW partition style to either the MBR or GPT partition styles.
The default partition style is GPT.
Disks must be initialized before they can be formatted and used to store data.

## EXAMPLES

### Example 1: Initialize a disk using default values
```
PS C:\>Initialize-Disk -Number 1
```

This example initializes the first disk in the computer (disk number 1), using the default values, which initializes the disk using the GPT partition style.

### Example 2: Initialize a disk using the MBR partition style
```
PS C:\> Initialize-Disk -Number 1 -PartitionStyle MBR
```

This example initializes a disk using the MBR partition style.

### Example 3: Initialize a virtual disk
```
PS C:\>Initialize-Disk -VirtualDisk (Get-VirtualDisk -FriendlyName UserData)
```

This example uses the **VirtualDisk** parameter with the **Get-VirtualDisk** cmdlet to get a virtual disk with the friendly name UserData, and initialize the Disk object associated with the virtual disk.

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttps://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
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
Specifies the friendly name of the disk to initialize.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -InputObject
Initializes the specified Disk object.

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
Specifies the disk number of the disk to initialize.

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

### -PartitionStyle
Specifies the type of the partition.
The acceptable values for this parameter are: **MBR** or **GPT**.
The disk must be set to read-write (`IsReadOnly $false$false` ) before this cmdlet will work.

```yaml
Type: PartitionStyle
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: GPT
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Sends items from the interactive window down the pipeline as input to other cmdlets.
By default, this cmdlet does not generate any output. 
 
                        
To send items from the interactive window down the pipeline, click to select the items and then click OK.
Shift-click and Ctrl-click are supported.

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
Specifies the path of the disk to initialize.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
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
Specifies the UniqueID of the disk to initialize

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -VirtualDisk
Specifies the VirtualDisk object for which you want to initialize the associated Disk object.
The Virtual Disk CIM object is exposed by the Get-VirtualDisk cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_6
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can pipe an MSFT_VirtualDisk object to the **VirtualDisk** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Disk
You can pipe an MSFT_Disk object to the **InputObject** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_Disk
If you specify the **Passthru** parameter, this cmdlet returns an object representing the newly initialized disk.

## NOTES

## RELATED LINKS

[Clear-Disk](./Clear-Disk.md)

[Get-Disk](./Get-Disk.md)

[Get-Partition](./Get-Partition.md)

[Set-Disk](./Set-Disk.md)

[Update-Disk](./Update-Disk.md)

