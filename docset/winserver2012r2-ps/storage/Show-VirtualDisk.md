---
external help file: VirtualDisk.cdxml-help.xml
Module Name: Storage
online version: 
schema: 2.0.0
title: Show-VirtualDisk
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 066B34B3-0B16-427E-B437-D6F3BD8A0AB7
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Show-VirtualDisk

## SYNOPSIS
Makes a virtual disk available to a host.

## SYNTAX

### ByFriendlyName (Default)
```
Show-VirtualDisk [-FriendlyName] <String[]> [-TargetPortAddresses <String[]>] [-InitiatorAddress <String>]
 [-HostType <HostType>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByUniqueId
```
Show-VirtualDisk -UniqueId <String[]> [-TargetPortAddresses <String[]>] [-InitiatorAddress <String>]
 [-HostType <HostType>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ByName
```
Show-VirtualDisk -Name <String[]> [-TargetPortAddresses <String[]>] [-InitiatorAddress <String>]
 [-HostType <HostType>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Show-VirtualDisk -InputObject <CimInstance[]> [-TargetPortAddresses <String[]>] [-InitiatorAddress <String>]
 [-HostType <HostType>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Show-VirtualDisk** cmdlet makes a virtual disk available to a host (by initiator and target ports).
This cmdlet is equivalent to a VDS unmask operation.

## EXAMPLES

### Example 1: Make a virtual disk available to the local computer
```
PS C:\> $initaddress = (Get-InitiatorPort)
PS C:\> $tarport = (Get-TargetPort)
PS C:\> Show-VirtualDisk -FriendlyName "SQLData_27a" -TargetPortAddresses $tarport.NodeAddress -InitiatorAddress $initaddress.NodeAddress
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

### -FriendlyName
Specifies the friendly name of the virtual disk to make available to the specified hosts.

```yaml
Type: String[]
Parameter Sets: ByFriendlyName
Aliases: 

Required: True
Position: 0
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
Accepted values: Unknown, Other, Standard, Solaris, HPUX, OpenVMS, Tru64, Netware, Sequent, AIX, DGUX, Dynix, Irix, CiscoISCSIStorageRouter, Linux, MicrosoftWindows, OS400, TRESPASS, HIUX, VMwareESXi, MicrosoftWindowsServer2008, MicrosoftWindowsServer2003

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
Parameter Sets: InputObject (cdxml)
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
Parameter Sets: ByName
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
Parameter Sets: ByUniqueId
Aliases: Id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

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

