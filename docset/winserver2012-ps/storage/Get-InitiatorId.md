---
external help file: Storage2_Cmdlets.xml
Module Name: Storage
online version: https://docs.microsoft.com/powershell/module/storage/get-initiatorid?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-InitiatorId

## SYNOPSIS
Gets the InitiatorID objects for the specified iSCSI initiators.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-InitiatorId [[-InitiatorAddress] <String[]>] [-AsJob] [-CimSession <CimSession[]>] [-HostType <HostType[]>]
 [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-InitiatorId [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-UniqueId <String[]>]
```

### UNNAMED_PARAMETER_SET_3
```
Get-InitiatorId [-AsJob] [-CimSession <CimSession[]>] [-MaskingSet <CimInstance>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_4
```
Get-InitiatorId [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-VirtualDisk <CimInstance>]
```

### UNNAMED_PARAMETER_SET_5
```
Get-InitiatorId [-AsJob] [-CimSession <CimSession[]>] [-StorageSubSystem <CimInstance>]
 [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-InitiatorId** cmdlet gets the InitiatorID objects for the specified iSCSI initiators.

## EXAMPLES

### Example 1: Get all InitiatorIDs
```
PS C:\>Get-InitiatorID
```

This example gets and displays all iSCSI initiator IDs on the computer.

### Example 2: Get the storage providers for each InitiatorID
```
PS C:\>Get-InitiatorId | Get-StorageSubSystem | Get-StorageProvider
```

This example gets and displays the storage providers for each InitiatorID by piping the output from the **Get-InitiatorId** cmdlet to the **Get-StorageSubSystem** cmdlet, and then piping that cmdlet's output to the **Get-StorageProvider** cmdlet.

### Example 3:Get the InitiatorID objects for a masking set
```
PS C:\>Get-InitiatorId -MaskingSet (Get-MaskingSet -FriendlyName *EQLV1)
```

This example uses the **Get-MaskingSet** cmdlet to get the masking set with a friendly name that ends with EQLV1, and then gets all associated InitiatorID objects.

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

### -HostType
Specifies the host operating system or other host environmental factors that may influence the behavior that the storage system should have when showing a virtual disk to an initiator.
If the HostType property is blank for the object you want to get, omit this parameter.

```yaml
Type: HostType[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InitiatorAddress
Specifies the address of the InitiatorID object you want to get.
These are the port addresses of the hosts to which the virtual disks will be made available.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaskingSet
Gets the InitiatorID objects associated with the specified MaskingSet object.
Enter a MaskingSet CIM object, which is exposed by the Get-MaskingSet cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageSubSystem
Gets the InitiatorID objects associated with the specified StorageSubsystem object.
Enter a StorageSubsystem CIM object, which is exposed by the Get-StorageSubSystem cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_5
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Specifies the UniqueID(s) of the InitiatorID(s) you want to get.
Separate multiple UniqueIDs with commas, and enclose brackets in quotation marks.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: Id

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualDisk
Gets the InitiatorID objects associated with the specified VirtualDisk object.
Enter a VirtualDisk CIM object, which is exposed by the Get-VirtualDisk cmdlet.

```yaml
Type: CimInstance
Parameter Sets: UNNAMED_PARAMETER_SET_4
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
You can pipe a MaskingSet object to the **MaskingSet** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_StorageSubsystem
You can pipe a StorageSubsystem object to the **StorageSubsystem** parameter.

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
You can pipe a VirtualDisk object to the **VirtualDisk** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_InitiatorId
This cmdlet returns an object that represents an initiator ID.

## NOTES

## RELATED LINKS

[Connect-iSCSITarget](../iscsi/Connect-IscsiTarget.md)

[Get-InitiatorPort](./Get-InitiatorPort.md)

[Remove-InitiatorId](./Remove-InitiatorId.md)

