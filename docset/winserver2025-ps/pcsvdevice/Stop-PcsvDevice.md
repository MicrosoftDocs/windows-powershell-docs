---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: CIM_PhysicalComputerSystemView.cdxml-help.xml
Module Name: PCSVDevice
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/pcsvdevice/stop-pcsvdevice?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-PcsvDevice
---

# Stop-PcsvDevice

## SYNOPSIS
Shuts down a remote hardware device.

## SYNTAX

### ByNoConnectionParams (Default)
```
Stop-PcsvDevice [-TimeoutSec <UInt32>] [-ShutdownType <PossibleShutdownTypes>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByComputerName
```
Stop-PcsvDevice [-TargetAddress] <String> [-Credential] <PSCredential>
 [-ManagementProtocol] <ManagementProtocol> [[-Port] <UInt16>] [-Authentication <Authentication>] [-UseSSL]
 [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck] [-TimeoutSec <UInt32>]
 [-ShutdownType <PossibleShutdownTypes>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Stop-PcsvDevice -InputObject <CimInstance[]> [-ShutdownType <PossibleShutdownTypes>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Stop-PcsvDevice** cmdlet shuts down a remote hardware device by using Web Services for Management (WS-Management) or Intelligent Platform Management Interface (IPMI).
The cmdlet puts the device in the Disabled state, which corresponds to a hard shutdown of the hardware device.
Specify the remote hardware device by the management name or IP address, provide credentials necessary to shut down the remote hardware device, and specify which management protocol to use.
The credentials must have administrator permissions on the remote hardware device.

## EXAMPLES

### Example 1: Shut down a computer
```
PS C:\> $Credential = Get-Credential
PS C:\>Stop-PcsvDevice -TargetAddress "10.1.12.43" -Credential $Credential -ManagementProtocol IPMI
```

This example shuts down a computer.

The first command uses the **Get-Credential** cmdlet to create a credential, and then stores it in the **$Credential** variable.
The cmdlet prompts you for a user name and password.
For more information, type `Get-Help Get-Credential`.

The second command shuts down the computer that has the management IP address 10.1.12.43 by using the IPMI management protocol.
The command specifies the credential object, stored in the **$Credential** variable, needed to connect to the computer.
By default, the cmdlet prompts you before it stops the remote hardware device.

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
Specifies an authentication method to use for devices managed by using WS-Management.
Do not specify this parameter for devices managed by using IPMI.
The acceptable values for this parameter are:

- Basic
- Digest
- Default

If you specify Default for this parameter and a value of WSMAN for the ManagementProtocol parameter, the cmdlet uses Basic authentication.

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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a **PSCredential** object based on a user name and password.
To obtain a **PSCredential** object, use the **Get-Credential** cmdlet.
For more information, type `Get-Help Get-Credential`.
This parameter specifies the credential for the remote hardware device.

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

Refer to your hardware documentation for supported management protocols.

Specify WSMAN for devices that represent information by using Systems Management Architecture for Server Hardware (SMASH), Desktop and mobile Architecture for System Hardware (DASH), or Physical Computer System View profiles.

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

### -Port
Specifies a port on the remote computer to use for the management connection.
If you do not specify a port, the cmdlet uses the following default values:

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

### -ShutdownType


```yaml
Type: PossibleShutdownTypes
Parameter Sets: (All)
Aliases:
Accepted values: Forced, Graceful

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipCACheck
Indicates that the client connects by using HTTPS without validating that a trusted CA signed the server certificate.
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
Indicates that the certificate CN of the server does not need to match the host name of the server.
Do not specify this parameter if you specify a value of IPMI for the **ManagementProtocol** parameter.

Specify this parameter only for managing devices by using WS-Management over HTTPS.
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
Do not specify this parameter if you specify a value of IPMI for the **ManagementProtocol** parameter.

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
Specifies the name or IP address of the management port on the remote hardware device.
For server hardware, this is typically a dedicated Baseboard Management Controller (BMC) IP address.
For other devices, like network switches, this is the IP address of their management port.
For desktop and mobile devices, the BMC sometimes shares the same IP address as the computer.

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

The cmdlet only returns an **MSFT_PCSVDevice** object if you specify the **PassThru** parameter.

## NOTES

## RELATED LINKS

[Get-PcsvDevice](./Get-PcsvDevice.md)

[Restart-PcsvDevice](./Restart-PcsvDevice.md)

[Set-PcsvDeviceBootConfiguration](./Set-PcsvDeviceBootConfiguration.md)

[Start-PcsvDevice](./Start-PcsvDevice.md)

