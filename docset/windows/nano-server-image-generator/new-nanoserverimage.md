---
author: brianlic-msft
description: 
external help file: NanoServerImageGenerator-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 2016-12-20
ms.prod: powershell
ms.technology: powershell
ms.topic: reference
online version: 
schema: 2.0.0
title: New-NanoServerImage
ms.assetid: 590470EA-3945-45D9-9FE4-EABE33A1823E
---

# New-NanoServerImage

## SYNOPSIS
Creates a Nano Server installation image.

## SYNTAX

```
New-NanoServerImage [-DeploymentType] <String> [-Edition] <String> [-MediaPath <String>] [-BasePath <String>]
 -TargetPath <String> [-MaxSize <UInt64>] [-Storage] [-Compute] [-Defender] [-Clustering] [-OEMDrivers]
 [-Containers] [-SetupUI <String[]>] [-Package <String[]>] [-ServicingPackagePath <String[]>]
 [-ComputerName <String>] -AdministratorPassword <SecureString> [-UnattendPath <String>] [-DomainName <String>]
 [-DomainBlobPath <String>] [-ReuseDomainNode] [-DriverPath <String[]>] [-InterfaceNameOrIndex <String>]
 [-Ipv6Address <String>] [-Ipv6Dns <String[]>] [-Ipv4Address <String>] [-Ipv4SubnetMask <String>]
 [-Ipv4Gateway <String>] [-Ipv4Dns <String[]>] [-DebugMethod <String>] [-EnableEMS] [-EMSPort <Byte>]
 [-EMSBaudRate <UInt32>] [-EnableRemoteManagementPort] [-CopyPath <Object>] [-SetupCompleteCommand <String[]>]
 [-Development] [-LogPath <String>] [-OfflineScriptPath <String[]>] [-OfflineScriptArgument <Hashtable>]
 [-Internal <String>] [<CommonParameters>]
```

## DESCRIPTION
The **New-NanoServerImage** cmdlet makes a local copy of the necessary files from the installation media and converts the included Nano Server Windows image (.wim) file into a VHD or VHDX image, or reuses the existing .wim file.
It then makes a copy of the converted VHD or VHDX image in the specified path.
You can subsequently perform the following operations: 


- Add packages.

- Add drivers. 

- Set the computer name.

- Set the administrator password.

- Join a domain.

- Enable debugging.

- Enable Emergency Management Services (EMS).

- Set the static IP address.

## EXAMPLES

### Example 1: Create a Nano Server installation image
```
PS C:\>New-NanoServerImage -MediaPath "D:\" -BasePath ".\Base" -TargetPath ".\Target 1\NanoServer.vhd" -GuestDrivers
```

This command copies the necessary files from D:\ into .\Base.
It converts the Nano Server .wim file into a .vhd file in .\Base\Base.vhd.
It then moves that VHD into .\Target 1\Target 1.vhd and embeds the Guest Drivers package into it.

## PARAMETERS

### -AdministratorPassword
Specifies the administrator password for the image.
If you do not specify this value on the command line, this cmdlet prompts you for the password.

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
Specifies the path for the source media.

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
Indicates that this operation adds the Clustering package.

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
Indicates that this operation adds the Compute (Hyper-V) package.

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
Indicates that this operation adds the Containers package.

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
{{Fill CopyPath Description}}

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

### -DebugMethod
Specifies the method of kernel debugging for the target image.
The acceptable values for this parameter are:

-- Serial
-- Net (KDNET) 
-- 1394 (FireWire) 
-- USB

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

### -Defender
Indicates that this operation adds the Windows Defender package.

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
Specifies the path to a domain blob.
This cmdlet joins the image to the domain that this parameter specifies.

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
Specifies a domain name.
This cmdlet performs an offline join to the domain specified by this parameter.
A domain blob is retrieved from the local computer.
If the local computer is not a member of the specified domain, the command fails.

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
{{Fill DriverPath Description}}

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

### -EMSBaudRate
Specifies the baud rate for EMS.
The default is 115200 bps.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EMSPort
Specifies the port on which to enable EMS.
The default is 1.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Edition
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

### -EnableEMS
Indicates that this operation enables EMS and BootEMS on the image.

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
Indicates that this operation opens port 5985 for inbound TCP connections for Windows Remote Management (WinRM).

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
Specifies the interface name or index to modify.
You can get the interface name or index using **Get-NetAdapter**, netsh, or Recovery Console.

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
{{Fill Internal Description}}

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
{{Fill LogPath Description}}

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
Specifies the size, in bytes, of the dynamic image to create.
The default value is 4 GB.

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
Specifies the path of the source media.
If a local copy of the source media already exists, and it is specified as the base path, then no copying is performed.

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
Indicates that this operation adds the OEM Drivers package.

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
{{Fill OfflineScriptArgument Description}}

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
{{Fill OfflineScriptPath Description}}

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
{{Fill Package Description}}

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
{{Fill ServicingPackagePath Description}}

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
{{Fill SetupCompleteCommand Description}}

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
{{Fill SetupUI Description}}

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
Indicates that this operation adds the Storage package.

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
Specifies the path of the final, modified image.
The image format is determined based on the file extension.
Possible extension values are .vhd, .vhdx, and .wim.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

###  
None.

## OUTPUTS

###  
None.

## NOTES

## RELATED LINKS

[Edit-NanoServerImage](./Edit-NanoServerImage.md)

[Get-NanoServerPackage](./Get-NanoServerPackage.md)

