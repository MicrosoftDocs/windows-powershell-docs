---
external help file: Storage2_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 066B34B3-0B16-427E-B437-D6F3BD8A0AB7
manager: dansimp
---

# Show-VirtualDisk

## SYNOPSIS
Makes a virtual disk available to a host.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Show-VirtualDisk [-FriendlyName] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-HostType <HostType>]
 [-InitiatorAddress <String>] [-PassThru] [-TargetPortAddresses <String[]>] [-ThrottleLimit <Int32>] [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Show-VirtualDisk [-AsJob] [-CimSession <CimSession[]>] [-HostType <HostType>] [-InitiatorAddress <String>]
 [-PassThru] [-TargetPortAddresses <String[]>] [-ThrottleLimit <Int32>] -UniqueId <String[]> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Show-VirtualDisk [-AsJob] [-CimSession <CimSession[]>] [-HostType <HostType>] [-InitiatorAddress <String>]
 [-PassThru] [-TargetPortAddresses <String[]>] [-ThrottleLimit <Int32>] -Name <String[]> [-Confirm] [-WhatIf]
```

### UNNAMED_PARAMETER_SET_4
```
Show-VirtualDisk [-AsJob] [-CimSession <CimSession[]>] [-HostType <HostType>] [-InitiatorAddress <String>]
 [-PassThru] [-TargetPortAddresses <String[]>] [-ThrottleLimit <Int32>] -InputObject <CimInstance[]> [-Confirm]
 [-WhatIf]
```

## DESCRIPTION
The **Show-VirtualDisk** cmdlet makes a virtual disk available to a host (by initiator and target ports).
This cmdlet is equivalent to a VDS unmask operation.

## EXAMPLES

### Example 1: Make a virtual disk available to the local computer
```
PS C:\>$initaddress = (Get-InitiatorPort)



PS C:\>$tarport = (Get-TargetPort)



PS C:\>Show-VirtualDisk -FriendlyName "SQLData_27a" -TargetPortAddresses $tarport.NodeAddress -InitiatorAddress $initaddress.NodeAddress
```

This example makes the "SQLData_27a" virtual disk available to all initiators and target ports of the local computer.

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
Specifies the friendly name of the virtual disk to make available to the specified hosts.

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

### -HostType
Specifies the operating system of the host computer.

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

### -InitiatorAddress
Specifies the address for an initiator to which the virtual disk should be unmasked.

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

### -InputObject
Accepts an object from the pipeline as input.

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

### -Name
Specifies the name of the virtual disk to make available to the specified hosts.

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

### -PassThru
Specifies that the cmdlet should output an object representing the virtual disk it unmasked.
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

### -TargetPortAddresses
Specifies one or more target port addresses to which the virtual disk should be unmasked.

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

### -UniqueId
Specifies the UniqueID of the virtual disk to make available to the specified host.

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
You can pipe an MSFT_VirtualDisk object to the **InputObject** parameter.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/Microsoft/Windows/Storage/MSFT_VirtualDisk
If you specify the **Passthru** parameter, this cmdlet outputs an object representing the virtual disk you made available to a host computer.

## NOTES

## RELATED LINKS

[Connect-VirtualDisk](./Connect-VirtualDisk.md)

[Disconnect-VirtualDisk](./Disconnect-VirtualDisk.md)

[Get-InitiatorPort](./Get-InitiatorPort.md)

[Get-TargetPort](./Get-TargetPort.md)

[Get-VirtualDisk](./Get-VirtualDisk.md)

[Hide-VirtualDisk](./Hide-VirtualDisk.md)

[New-VirtualDisk](./New-VirtualDisk.md)

[Remove-VirtualDisk](./Remove-VirtualDisk.md)

[Repair-VirtualDisk](./Repair-VirtualDisk.md)

[Resize-VirtualDisk](./Resize-VirtualDisk.md)

[Set-VirtualDisk](./Set-VirtualDisk.md)

