---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.HyperV.PowerShell.Cmdlets.dll-Help.xml
Module Name: Hyper-V
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/hyper-v/set-vmfirmware?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-VMFirmware
---

# Set-VMFirmware

## SYNOPSIS
Sets the firmware configuration of a virtual machine.

## SYNTAX

### VMName (Default)
```
Set-VMFirmware [-CimSession <CimSession[]>] [-ComputerName <String[]>] [-Credential <PSCredential[]>]
 [-VMName] <String[]> [-BootOrder <VMComponentObject[]>] [-FirstBootDevice <VMComponentObject>]
 [-EnableSecureBoot <OnOffState>] [-SecureBootTemplate <String>] [-SecureBootTemplateId <Guid>]
 [-PreferredNetworkBootProtocol <IPProtocolPreference>] [-ConsoleMode <ConsoleModeType>]
 [-PauseAfterBootFailure <OnOffState>] [-Passthru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### VMObject
```
Set-VMFirmware [-VM] <VirtualMachine[]> [-BootOrder <VMComponentObject[]>]
 [-FirstBootDevice <VMComponentObject>] [-EnableSecureBoot <OnOffState>] [-SecureBootTemplate <String>]
 [-SecureBootTemplateId <Guid>] [-PreferredNetworkBootProtocol <IPProtocolPreference>]
 [-ConsoleMode <ConsoleModeType>] [-PauseAfterBootFailure <OnOffState>] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### VMFirmware
```
Set-VMFirmware [-VMFirmware] <VMFirmware[]> [-BootOrder <VMComponentObject[]>]
 [-FirstBootDevice <VMComponentObject>] [-EnableSecureBoot <OnOffState>] [-SecureBootTemplate <String>]
 [-SecureBootTemplateId <Guid>] [-PreferredNetworkBootProtocol <IPProtocolPreference>]
 [-ConsoleMode <ConsoleModeType>] [-PauseAfterBootFailure <OnOffState>] [-Passthru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Set-VMFirmware** cmdlet sets the firmware configuration of a Generation 2 virtual machine.

## EXAMPLES

### Example 1
```
PS C:\> Set-VMFirmware "Test VM" -EnableSecureBoot On
```

This example enables secure boot functionality on the virtual machine "Test VM".

### Example 2
```
PS C:\> Set-VMFirmware "Test VM" -FirstBootDevice $vmNetworkAdapter
```

This example sets the virtual machine "Test VM" to boot off of the VM network adapter object stored in $vmNetworkAdapter.
This object was acquired using get-VMNetworkAdapter.

### Example 3
```
PS C:\> Set-VMFirmware "Test VM" -BootOrder $vmNetworkAdapter, $vmHardDiskDrive
```

Sets the boot order for the virtual machine "Test VM".
$vmNetworkAdapter contains a VM Network Adapter object (acquired using get-VMNetworkAdapter) and $vmHardDiskDrive contains a VM hard disk object (acquired using get-VMHardDiskDrive).
Any existing boot entries not specified by this command will be removed from the virtual machine.

## PARAMETERS

### -BootOrder
Specifies an array of devices.
The boot order determines the order of the devices from which to boot.
The acceptable values for this parameter are:


  -- VMBootSource

  -- VMNetworkAdapter

  -- HardDiskDrive

  -- DVDDrive


The VMBootSource value describes a boot entry in firmware nonvolatile Random Access Memory (NVRAM).

```yaml
Type: VMComponentObject[]
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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the names of the Hyper-V hosts whose firmware configuration you want to modify.

```yaml
Type: String[]
Parameter Sets: VMName
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConsoleMode
Specifies the console mode type for the virtual machine.
This parameter allows a virtual machine to run without graphical user interface.

```yaml
Type: ConsoleModeType
Parameter Sets: (All)
Aliases:
Accepted values: Default, COM1, COM2, None

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies one or more user accounts that have permission to perform this action.
The default is the current user.

```yaml
Type: PSCredential[]
Parameter Sets: VMName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableSecureBoot
Specifies whether to enable secure boot.
The acceptable values for this parameter are:


  -- On

  -- Off


Secure boot uses a public key infrastructure that protects the integrity of the operating system.

```yaml
Type: OnOffState
Parameter Sets: (All)
Aliases:
Accepted values: On, Off

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FirstBootDevice
Specifies the device from which to attempt to boot from first.
The acceptable values for this parameter are:


  -- VMBootSource

  -- VMNetworkAdapter

  -- HardDiskDrive

  -- DVDDrive


The VMBootSource value describes a boot entry in firmware NVRAM.

```yaml
Type: VMComponentObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Passthru
Returns an object representing the item with which you are working.
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

### -PauseAfterBootFailure
Specifies the behavior of the virtual machine after a start failure.
For a value of On, if the virtual machine fails to start correctly from a device, the virtual machine is paused.

```yaml
Type: OnOffState
Parameter Sets: (All)
Aliases:
Accepted values: On, Off

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PreferredNetworkBootProtocol
Specifies the IP protocol version to use during a network boot.

```yaml
Type: IPProtocolPreference
Parameter Sets: (All)
Aliases:
Accepted values: IPv4, IPv6

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecureBootTemplate
Specifies the name of the secure boot template.
If secure boot is enabled, you must have a valid secure boot template for the guest operating system to start.

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

### -SecureBootTemplateId
Specifies the ID of the secure boot template.

```yaml
Type: Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Specifies the virtual machine objects for which want to modify the firmware configuration.
To obtain a virtual machine object, use the **Get-VM** cmdlet.

```yaml
Type: VirtualMachine[]
Parameter Sets: VMObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMFirmware
Specifies an array of virtual machine firmware configurations.
The cmdlet sets the firmware configurations you specify.

```yaml
Type: VMFirmware[]
Parameter Sets: VMFirmware
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMName
Specifies an array of names of virtual machines for which you want to modify the firmware configuration.

```yaml
Type: String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.HyperV.Powershell.VMFirmware

## NOTES
* Note: This cmdlet is supported only when run against Generation 2 virtual machines.

## RELATED LINKS

[Get-VMFirmware](./Get-VMFirmware.md)

