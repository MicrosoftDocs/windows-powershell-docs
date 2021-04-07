---
author: Kateyanne
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NanoServerImageGenerator-help.xml
manager: jasgro
Module Name: NanoServerImageGenerator
ms.author: v-kaunu
ms.date: 12/20/2016
ms.mktglfcycl: manage
ms.prod: w10
ms.reviewer: 
ms.sitesec: library
ms.technology: 
ms.topic: reference
online version: https://docs.microsoft.com/powershell/module/nanoserverimagegenerator/new-nanoserverimage?view=windowsserver2016-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NanoServerImage
---

# New-NanoServerImage

## SYNOPSIS
Creates a Nano Server installation image.

## SYNTAX

```
New-NanoServerImage [-DeploymentType] <String> {Host | Guest} [-Edition] <String> {Standard | Datacenter}
 -TargetPath <String> -AdministratorPassword <SecureString> [-MediaPath <String>] [-BasePath <String>]
 [-MaxSize <UInt64>] [-Storage] [-Compute] [-Defender] [-Clustering] [-OEMDrivers] [-Containers]
 [-SetupUI <String[]>] [-Package <String[]>] [-ServicingPackagePath <String[]>]
 [-ComputerName <String>] [-UnattendPath <String>] [-DomainName <String>]
 [-DomainBlobPath <String>] [-ReuseDomainNode] [-DriverPath <String[]>] [-InterfaceNameOrIndex <String>]
 [-Ipv6Address <String>] [-Ipv6Dns <String[]>] [-Ipv4Address <String>] [-Ipv4SubnetMask <String>]
 [-Ipv4Gateway <String>] [-Ipv4Dns <String[]>] [-DebugMethod <String> {Serial | Net | 1394 | USB}]
 [-DebugBaudRate <UInt32>] [-DebugBusParams <String>] [-DebugChannel <UInt16>] [-DebugCOMPort <Byte>] [-DebugKey <String>] [-DebugPort <UInt16>] [-DebugRemoteIP <String>] [-DebugTargetName <String>]
 [-EnableEMS] [-EMSPort <Byte>] [-EMSBaudRate <UInt32>] [-EnableRemoteManagementPort] [-CopyPath <Object>]
 [-SetupCompleteCommand <String[]>] [-Development] [-LogPath <String>] [-OfflineScriptPath <String[]>]
 [-OfflineScriptArgument <Hashtable>] [-Internal <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-NanoServerImage** cmdlet makes a local copy of the necessary files from the installation media and converts the included Nano Server Windows image (.wim) file into a VHD or VHDX image, or reuses the existing .wim file. It then makes a copy of the converted VHD or VHDX image in the specified path. You can subsequently perform the following operations:

- Add packages.
- Add drivers.
- Add servicing packages (updates).
- Add an unattended setup file (unattend.xml).
- Add files.
- Add setup scripts.
- Set the computer name.
- Set the administrator password.
- Configure network settings.
- Join a domain.
- Enable debugging.
- Enable Emergency Management Services (EMS).
- Enable remote management.
- Enable development options.

## EXAMPLES

### Example 1: Create a Nano Server installation image
```
PS C:\> New-NanoServerImage -DeploymentType Guest -Edition Datacenter -MediaPath D:\ -BasePath .\Base -TargetPath .\NanoServer.vhd
```

This command copies the necessary files from D:\ into .\Base. It converts the Nano Server .wim file into a .vhd file. It then moves that VHD to .\NanoServer.vhd and embeds the guest drivers into it.

## PARAMETERS

### -AdministratorPassword
Specifies the password for the built-in Administrator account for the image. If you do not specify this value on the command line, this cmdlet prompts you for the password. To use a blank password, specify $null or press Enter when prompted for the password.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BasePath
Specifies the path where Nano Server files are copied from the source media. These files are not automatically deleted after running Edit-NanoServerImage or New-NanoServerImage. This enables you to copy the Nano Server files from the source media once with the MediaPath parameter and reuse the same files with the BasePath parameter when running Edit-NanoServerImage or New-NanoServerImage again.

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

### -Clustering
Indicates that this operation adds the Clustering package. This package includes Failover Clustering, VM Failover Clustering, Volume Replication Clustering, Storage Spaces Direct (S2D), Storage Quality of Service (QoS), and SMB Witness Service.

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

### -Compute
Indicates that this operation adds the Compute package. This package includes Hyper-V and NetQoS.

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

### -ComputerName
Specifies the computer name of the image.

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

### -Containers
Indicates that this operation adds the Containers package. This package includes host support for Windows Containers.

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

### -CopyPath
Specifies one or more files to copy into the target image. This parameter accepts a path to a single file, an array of paths to multiple files, or a hashtable of file paths and target directories where the keys are the file path names and the values are the target directories. For example, @{"C:\mytool.exe"="windows"} will copy mytool.exe from C:\ on the source machine to the windows directory in the target image.

```yaml
Type: Object
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DebugBaudRate
Specifies the baud rate to use for kernel debugging. This parameter is only applicable when DebugMethod is Serial. The default rate is 115200 bps.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 115200
Accept pipeline input: False
Accept wildcard characters: False
```

### -DebugBusParams
Specifies additional bus parameters to use for network kernel debugging (KDNet). This parameter is only applicable when DebugMethod is Net.

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

### -DebugChannel
Specifies the channel that the computer running the debugger can use to connect to the host. This parameter is only applicable when DebugMethod is 1394.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DebugCOMPort
Specifies the serial port that kernel debugging is enabled on. This parameter is only applicable when DebugMethod is Serial. The default port is 2.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### -DebugKey
Specifies the shared key secret for establishing the debugger connection. This parameter is only applicable when DebugMethod is Net.

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

### -DebugMethod
Specifies the method of kernel debugging for the target image. The acceptable values for this parameter are:

- Serial
- Net (KDNET) 
- 1394 (FireWire) 
- USB

Depending on the value of this parameter, other parameters become available.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Serial, Net, 1394, USB

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DebugPort
Specifies the port that the computer running the debugger can use to connect to the host. This parameter is only applicable when DebugMethod is Net.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DebugRemoteIP
Specifies the IP address of the computer running the debugger. This parameter is only applicable when DebugMethod is Net.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DebugTargetName
Specifies the target name that the computer running the debugger can use to connect to the host. This parameter is only applicable when DebugMethod is USB.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Defender
Indicates that this operation adds the Windows Defender package. This package also includes a default malware definition file for Windows Defender.

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

### -DeploymentType
Specifies the type of Nano Server deployment image. Valid values are Guest and Host. Specify Guest for creating an image for deployment to a virtual machine. Specify Host for creating an image for deployment to physical hardware.

```yaml
Type: String
Parameter Sets: (All)
Aliases:
Accepted values: Host, Guest

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Development
Indicates that this operation enables settings for development and testing scenarios on Nano Server. This includes enabling PowerShell as the default local shell, allowing installation of unsigned drivers, copying debugger binaries into the image, opening a port for debugging, enabling test signing, and enabling installation of AppX packages without a developer license.

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

### -DomainBlobPath
Specifies the path to a domain blob. This cmdlet joins the image to the domain that this parameter specifies. You can harvest a domain blob from a computer that is joined to the domain using the djoin.exe tool with the Provision parameter. Save the blob to a file and specify the path to the blob file using this parameter.

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

### -DomainName
Specifies a domain name. This cmdlet performs an offline join to the domain specified by this parameter. A domain blob is retrieved from the local computer. If the local computer is not a member of the specified domain, the command fails. In this case, harvest a domain blob from a computer that is joined to the domain and use the DomainBlobPath parameter instead.

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

### -DriverPath
Specifies one or more paths to driver .inf files and binary files to add to the image. Paths can be directories containing drivers or paths to individual driver files. For each driver, both the .inf and .sys files must be present. Only 64-bit drivers are supported on Nano Server. If the drivers are not signed, the command fails.

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

### -Edition
Specifies the edition of the operating system. Valid values are Standard and Datacenter.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Standard, Datacenter

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EMSBaudRate
Specifies the baud rate for Emergency Management Services (EMS). The default is 115200 bps.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 115200
Accept pipeline input: False
Accept wildcard characters: False
```

### -EMSPort
Specifies the port on which to enable Emergency Management Services (EMS). The default is 1.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 1
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableEMS
Indicates that this operation enables Emergency Management Services (EMS) and BootEMS on the image.

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

### -EnableRemoteManagementPort
Indicates that this operation opens port 5985 for inbound TCP connections for Windows Remote Management (WinRM) and enable the Remote Event Log Management firewall group.

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

### -InterfaceNameOrIndex
Specifies the network adapter interface name or index to modify. You can get the interface name or index using **Get-NetAdapter**, netsh, or Recovery Console.

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

### -Internal
This parameter is reserved for internal use.

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

### -Ipv4Address
Specifies the given IPv4 static address on the interface specified by the *InterfaceNameOrIndex* parameter.

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

### -Ipv4Dns
Specifies an array of static IPv4 DNS server addresses.

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

### -Ipv4Gateway
Specifies the given IPv4 gateway on the interface specified by the *InterfaceNameOrIndex* parameter.

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

### -Ipv4SubnetMask
Specifies the IPv4 subnet mask on the interface specified by the *InterfaceNameOrIndex* parameter.

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

### -Ipv6Address
Specifies the IPv6 static address on the interface specified by the *InterfaceNameOrIndex* parameter.

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

### -Ipv6Dns
Specifies an array of static IPv6 DNS server addresses.

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

### -LogPath
Specifies the path where log files from the operation will be collected. If LogPath is not specified, all logs are collected into a Logs folder in BasePath.

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

### -MaxSize
Specifies the size, in bytes, of the dynamic image to create. The default value is 4 GB. Note that the default size of 4GB is too small to apply cumulative updates. If you use the default size, prior to installing updates, use Hyper-V Manager, Disk Management, PowerShell, or other tool to expand the size of the virtual hard disk and system volume to at least 10GB, or use the ScratchDir parameter on the DISM tools to set the scratch directory to a volume with at least 10GB of free space when installing updates.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MediaPath
Specifies the path of the source media. If a local copy of the source media already exists, and it is specified using the BasePath parameter, then no copying is performed.

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

### -OEMDrivers
Indicates that this operation adds the OEM Drivers package. This package includes drivers for a variety of network adapters, storage controllers, and other peripherals. This is the same set of drivers included in a Server Core installation of Windows Server.

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

### -OfflineScriptArgument
Use the OfflineScriptPath parameter to specify an array of paths to PowerShell (.ps1) scripts. If those scripts take arguments, use the OfflineScriptArgument parameter to pass a hashtable of additional arguments to the scripts.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OfflineScriptPath
Use the OfflineScriptPath parameter to specify an array of paths to PowerShell (.ps1) scripts. If those scripts take arguments, use the OfflineScriptArgument parameter to pass a hashtable of additional arguments to the scripts.

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

### -Package
Specifies an array of Nano Server packages to add. Packages are stored in the NanoServer\Packages folder on the installation media. You can get a list of Nano Server packages by running the Get-NanoServerPackage cmdlet.

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

### -ReuseDomainNode
Indicates that this operation reuses a node with the same name if it exists when joining a domain.

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

### -ServicingPackagePath
Specifies an array of servicing packages (updates) to add.

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

### -SetupCompleteCommand
Specifies an array of commands to run after setup completes.

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

### -SetupUI
This parameter is reserved for internal use.

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

### -Storage
Indicates that this operation adds the Storage package. This package includes the File Server role, Data Deduplication, Multipath I/O, including a driver for Microsoft Device-Specific Module (MSDSM), ReFS (v1 and v2), iSCSI Initiator (but not iSCSI Target), Storage Replica, Storage Management Service with SMI-S support, SMB Witness Service, Volume Shadow Copy Service (VSS), Dynamic Volumes, and basic Windows storage providers (for Windows Storage Management). Note that when using the Storage parameter to install the File Server role, the role is installed but not enabled. You can enable the File Server role from a remote computer using Server Manager.

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

### -TargetPath
Specifies the path of the final, modified image. The image format is determined based on the file extension. Possible extension values are .vhd, .vhdx, and .wim.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UnattendPath
Specifies the path to an unattended setup file (unattend.xml).

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[Edit-NanoServerImage](./Edit-NanoServerImage.md)

[Get-NanoServerPackage](./Get-NanoServerPackage.md)

