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
title: Edit-NanoServerImage
ms.assetid: 544FB377-8C33-467E-864B-AC7D0F94C570
---

# Edit-NanoServerImage

## SYNOPSIS
Modifies a Nano Server installation image.

## SYNTAX

```
Edit-NanoServerImage [[-BasePath] <String>] [-TargetPath] <String> [-Storage] [-Compute] [-Defender]
 [-Clustering] [-OEMDrivers] [-Containers] [[-SetupUI] <String[]>] [[-Package] <String[]>]
 [[-ServicingPackagePath] <String[]>] [[-ComputerName] <String>] [[-AdministratorPassword] <SecureString>]
 [[-UnattendPath] <String>] [[-DomainName] <String>] [[-DomainBlobPath] <String>] [-ReuseDomainNode]
 [[-DriverPath] <String[]>] [[-InterfaceNameOrIndex] <String>] [[-Ipv6Address] <String>]
 [[-Ipv6Dns] <String[]>] [[-Ipv4Address] <String>] [[-Ipv4SubnetMask] <String>] [[-Ipv4Gateway] <String>]
 [[-Ipv4Dns] <String[]>] [[-DebugMethod] <String>] [-EnableEMS] [[-EMSPort] <Byte>] [[-EMSBaudRate] <UInt32>]
 [-EnableRemoteManagementPort] [[-CopyPath] <Object>] [[-SetupCompleteCommand] <String[]>] [-Development]
 [[-LogPath] <String>] [[-OfflineScriptPath] <String[]>] [[-OfflineScriptArgument] <Hashtable>]
 [[-Internal] <String>] [<CommonParameters>]
```

## DESCRIPTION
The **Edit-NanoServerImage** cmdlet adds packages, drivers, and configures operating system options for a base Nano Server installation.
The cmdlet operates on an image produced by the New-NanoServerImage cmdlet.

You can use the **Edit-NanoServerImage** cmdlet to do the following operations: 

- Add packages.
- Add drivers.
- Set the computer name.
- Set the administrator password.
- Join a domain.
- Enable debugging.
- Enable Emergency Management Services (EMS).
- Set the static IP address.

## EXAMPLES

### Example 1: Modify a Nano Server installation image
```
PS C:\>Edit-NanoServerImage -MediaPath "D:\" -BasePath ".\Base" -TargetPath ".\Target 1\NanoServer.vhdx" -Compute -ComputerName "Nano" -DomainName "ContosoDomain" -AdministratorPassword (ConvertTo-SecureString -String "Passw0rd" -AsPlainText -Force)
```

This example assumes that you've run the New-NanoServerImage cmdlet and specified .\Base as the base path.

This command copies required files from D:\ to .\Base.
It converts the Nano Server .wim file into a .vhdx file and moves it to .\Target 1\NanoServer.vhdx.
It adds the Compute (Hyper-V) package, sets the computer name to Nano, sets the administrator password to Passw0rd, and performs an offline domain join of the machine to ContosoDomain.

## PARAMETERS

### -AdministratorPassword
Specifies the administrator password for the image.
If you do not specify this value on the command line, this cmdlet prompts you for the password.

```yaml
Type: SecureString
Parameter Sets: (All)
Aliases: 

Required: False
Position: 6
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
Position: 0
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
Position: 5
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
Position: 21
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
Position: 18
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
Position: 9
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
Position: 8
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
Position: 10
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
Position: 20
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
Position: 19
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
Position: 11
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
Position: 26
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
Position: 14
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
Position: 17
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
Position: 16
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
Position: 15
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
Position: 12
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
Position: 13
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
Position: 23
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
Position: 25
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
Position: 24
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
Position: 3
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
Position: 4
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
Position: 22
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
Position: 2
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
Position: 1
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
Position: 7
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

[Get-NanoServerPackage](./Get-NanoServerPackage.md)

[New-NanoServerImage](./New-NanoServerImage.md)

