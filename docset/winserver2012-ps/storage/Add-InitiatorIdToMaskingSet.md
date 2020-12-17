---
external help file: Storage2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 71993626-1CD8-4187-BE8E-AFD54B280F4E
manager: dansimp
---

# Add-InitiatorIdToMaskingSet

## SYNOPSIS
Adds an initiator ID to an existing masking set, granting the host associated with the initiator ID access to the virtual disk and target port resources defined in the masking set.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Add-InitiatorIdToMaskingSet [-MaskingSetFriendlyName] <String[]> [-AsJob] [-CimSession <CimSession[]>]
 [-HostType <HostType>] [-InitiatorIds <String[]>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Add-InitiatorIdToMaskingSet [-AsJob] [-CimSession <CimSession[]>] [-HostType <HostType>]
 [-InitiatorIds <String[]>] [-PassThru] [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Add-InitiatorIdToMaskingSet [-AsJob] [-CimSession <CimSession[]>] [-HostType <HostType>]
 [-InitiatorIds <String[]>] [-PassThru] [-ThrottleLimit <Int32>] -MaskingSetUniqueId <String[]> [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Add-InitiatorIdToMaskingSet** cmdlet adds an initiator ID to an existing masking set, granting the host associated with the initiator ID access to the virtual disk and target port resources defined in the masking set.

ps_storage_spacesubsystem_not_remark

## EXAMPLES

### Example 1: Adding an InitiatorID to a masking set by masking set object
```
PS C:\>$fcPorts = Get-InitiatorPort -CimSession Srv1 -ConnectionType FibreChannel
PS C:\>$maskingSet = Get-MaskingSet Cluster1MaskingSet
PS C:\>$fcPorts.NodeAddress 2000001b328d33cd2001001b32ad33cd
PS C:\>$maskingSet | Add-InitiatorIdToMaskingSet -InitiatorIds $fcPorts.NodeAddress
```

This example shows getting Fibre Channel initiator ports from the Srv1 computer, then getting the masking set object for the Cluster1MaskingSet, then enabling Srv1 access to all virtual disks defined in the masking set.

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

```yaml
Type: HostType
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InitiatorIds
Specifies one or more initiator IDs on which this cmdlet acts.
The initiator IDs will be added to this masking set.
Note: The initiator IDs do not need to be displayed in the output of the Get-InitiatorId cmdlet to be added to a masking set.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Accepts a MaskingSet object from the pipeline as input.

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

### -MaskingSetFriendlyName
Specifies the friendly name of the masking set to which you want to add an initiator ID.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaskingSetUniqueId
Specifies the unique ID of the masking set to which you want to add an initiator ID.

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
Specifies that the cmdlet should output an object representing the masking set to which it added an initiator ID.
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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/ MSFT_MaskingSet
You can pipe one or more MSFT_MaskingSet objects to the **InputObject** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
If you specify the **Passthru** parameter, this cmdlet outputs an object that represents the masking set to which you added an initiator ID.

## NOTES

## RELATED LINKS

[Get-InitiatorID](./Get-InitiatorId.md)

[Get-InitiatorPort](./Get-InitiatorPort.md)

