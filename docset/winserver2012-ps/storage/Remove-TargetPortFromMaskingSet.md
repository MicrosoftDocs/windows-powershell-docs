---
author: Kateyanne
external help file: Storage2_Cmdlets.xml
manager: dansimp
Module Name: Storage
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/storage/remove-targetportfrommaskingset?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-TargetPortFromMaskingSet

## SYNOPSIS
Removes a specified target port from a masking set.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Remove-TargetPortFromMaskingSet [-MaskingSetFriendlyName] <String[]> [-AsJob] [-CimSession <CimSession[]>]
 [-PassThru] [-TargetPortAddresses <String[]>] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Remove-TargetPortFromMaskingSet [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-TargetPortAddresses <String[]>] [-ThrottleLimit <Int32>] -MaskingSetUniqueId <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Remove-TargetPortFromMaskingSet [-AsJob] [-CimSession <CimSession[]>] [-PassThru]
 [-TargetPortAddresses <String[]>] [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-TargetPortFromMaskingSet** cmdlet removes a specified target port from a masking set.

ps_storage_spacesubsystem_not_remark

## EXAMPLES

### EXAMPLE 1
```
PS C:\>$masksfname = "MyFirstMaskingSet"



PS C:\>$targetpaddress = (Get-TargetPort).PortAddress



PS C:\>Remove-TargetPortFromMaskingSet -MaskingSetFriendlyName $masksfname -TargetPortAddresses $targetpaddress
```

This example removes a target port from a masking set.
And prevents any of the VirtualDisk or InitiatorId objects defined in the masking set from utilizing the target port.

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

### -InputObject
Accepts an object from the pipeline as input.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MaskingSetFriendlyName
Specifies the friendly name of a masking set.
The friendly name may be defined by a user.

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
Specifies an ID used to uniquely identify a masking set in the system.
The ID persists through reboots.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -TargetPortAddresses
Specifies one or more target port addresses.
The target port addresses to be removed from the masking set.

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

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_MaskingSet
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-TargetPort](./Get-TargetPort.md)

[Get-MaskingSet](./Get-MaskingSet.md)

