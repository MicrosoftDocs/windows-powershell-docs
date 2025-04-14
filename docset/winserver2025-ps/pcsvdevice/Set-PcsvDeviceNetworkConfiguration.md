---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: CIM_PhysicalComputerSystemView.cdxml-help.xml
Module Name: PCSVDevice
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/pcsvdevice/set-pcsvdevicenetworkconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-PcsvDeviceNetworkConfiguration
---

# Set-PcsvDeviceNetworkConfiguration

## SYNOPSIS
Changes the network configuration of a PCSV device.

## SYNTAX

### ByNoConnectionParams (Default)
```
Set-PcsvDeviceNetworkConfiguration [-TimeoutSec <UInt32>] [-IPv4AddressOrigin] <PossibleIPv4Origins>
 [-IPv4Address <String>] [-IPv4DefaultGateway <String>] [-IPv4SubnetMask <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByComputerName
```
Set-PcsvDeviceNetworkConfiguration [-TargetAddress] <String> [-Credential] <PSCredential>
 [-ManagementProtocol] <ManagementProtocol> [[-Port] <UInt16>] [-Authentication <Authentication>] [-UseSSL]
 [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck] [-TimeoutSec <UInt32>]
 [-IPv4AddressOrigin] <PossibleIPv4Origins> [-IPv4Address <String>] [-IPv4DefaultGateway <String>]
 [-IPv4SubnetMask <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-PcsvDeviceNetworkConfiguration -InputObject <CimInstance[]> [-IPv4AddressOrigin] <PossibleIPv4Origins>
 [-IPv4Address <String>] [-IPv4DefaultGateway <String>] [-IPv4SubnetMask <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-PcsvDeviceNetworkConfiguration** cmdlet changes the network configuration of a Physical Computer System View (PCSV) device.
You can configure the network settings of a device statically or dynamically, by using the DHCP service.
If you specify a static network configuration, you must specify the IP address, subnet mask, and default gateway.
This cmdlet currently supports devices that use the Intelligent Platform Management Interface (IPMI) protocol.
Changing the network configuration disrupts the out-of-band session, and, therefore, this cmdlet can only be run on an in-band connection.
To use with an in-band connection, you must have elevated privileges.

## EXAMPLES

### Example 1: Configure network settings dynamically
```
PS C:\>Set-PcsvDeviceNetworkConfiguration -IPv4AddressOrigin DHCP
```

This command configures network settings for the PCSV device.
The DHCP service updates the IP address, subnet mask and default gateway.

### Example 2: Configure network settings statically
```
PS C:\>Set-PcsvDeviceNetworkConfiguration -IPv4AddressOrigin Static -IPv4Address "10.0.1.2" -IPv4DefaultGateway "10.0.0.1" -IPv4SubnetMask "255.255.0.0"
```

This command configures network settings for the PCSV device.
The command specifies the IP address, subnet mask, and default gateway for the device.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -Authentication
Specifies an authentication method to use for devices managed by WS-Management.
Do not specify this parameter for devices managed by using IPMI.
The acceptable values for this parameter are:

- Basic
- Digest
- Default

```yaml
Type: Authentication
Parameter Sets: ByComputerName
Aliases:
Accepted values: Default, Basic, Digest

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a **PSCredential** object based on a user name and password.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.
For IPMI devices, specify credentials that correspond to a user with Administrator privileges on the device.

```yaml
Type: PSCredential
Parameter Sets: ByComputerName
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IPv4Address
Specifies an IPv4 address for the PCSV device.

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

### -IPv4AddressOrigin
Specifies how the IP address is acquired.
The acceptable values for this parameter are:

- Static
- DHCP

```yaml
Type: PossibleIPv4Origins
Parameter Sets: (All)
Aliases:
Accepted values: Static, DHCP

Required: True
Position: 3001
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPv4DefaultGateway
Specifies an IPv4 default gateway for the PCSV device.

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

### -IPv4SubnetMask
Specifies an IPv4 subnet mask for the PCSV device.

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
Specifies the input object that is used in a pipeline command.

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

### -ManagementProtocol
Specifies a management protocol used to communicate with a device.
The acceptable values for this parameter are:

- WSMAN
- IPMI

This cmdlet currently supports only devices that use the IPMI protocol.

```yaml
Type: ManagementProtocol
Parameter Sets: ByComputerName
Aliases: MP
Accepted values: WSMan, IPMI

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PassThru
Passthru

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

### -Port
Specifies a port on the remote computer to use for the management connection.
If you do not specify a port, the cmdlet uses the following default ports:

- IPMI and WSMAN over HTTP.
Port 623.
- WSMAN over HTTPS.
Port 664.

```yaml
Type: UInt16
Parameter Sets: ByComputerName
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkipCACheck
Indicates that the client connects by using HTTPS without validating that a trusted certification authority (CA) signed the server certificate.
Do not specify this parameter if you specify a value of IPMI for the **ManagementProtocol** parameter.

Do not specify this parameter unless you can establish trust in another way, such as if the remote computer is part of a network that is physically secure and isolated, or if the remote computer is a trusted host in a Windows Remote Management (WinRM) configuration.

```yaml
Type: SwitchParameter
Parameter Sets: ByComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkipCNCheck
Indicates that the certificate common name (CN) of the server does not need to match the host name of the server.
Do not specify this parameter if you specify a value of IPMI for the **ManagementProtocol** parameter.

Specify this parameter only for managing devices by using WSMAN over HTTPS.
Be sure to specify this parameter only for trusted computers.

```yaml
Type: SwitchParameter
Parameter Sets: ByComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkipRevocationCheck
Indicates that the cmdlet skips the revocation check of server certificates.

Be sure to specify this parameter only for trusted computers.

```yaml
Type: SwitchParameter
Parameter Sets: ByComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TargetAddress
Specifies the name or IP address of the remote hardware device.

```yaml
Type: String
Parameter Sets: ByComputerName
Aliases: CN, ComputerName, IpAddress

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -TimeoutSec
Specifies how long to wait, in seconds, for a response from the remote hardware device.
After this period, the cmdlet abandons the connection attempt.

```yaml
Type: UInt32
Parameter Sets: ByNoConnectionParams, ByComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UseSSL
Indicates that the server connects to the target computer by using SSL.
WSMAN encrypts all content transmitted over the network.
Specify this parameter to use the additional protection of HTTPS instead of HTTP.
If you specify this parameter and SSL is not available on the connection port, the command fails.

```yaml
Type: SwitchParameter
Parameter Sets: ByComputerName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Management.Automation.PSCredential

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.PcsvDevice.ManagementProtocol

### System.UInt16

### Microsoft.PowerShell.Cmdletization.GeneratedTypes.PcsvDevice.Authentication

### System.Management.Automation.SwitchParameter

### System.UInt32

### Microsoft.Management.Infrastructure.CimInstance[]

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/HardwareManagement/MSFT_PCSVDevice

This cmdlet returns a PCSV device object, if you specify the **PassThru** parameter.

## NOTES

## RELATED LINKS

[Get-PcsvDevice](./Get-PcsvDevice.md)

[Set-PcsvDeviceBootConfiguration](./Set-PcsvDeviceBootConfiguration.md)

