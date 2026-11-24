---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: CIM_PhysicalComputerSystemView.cdxml-help.xml
Module Name: PCSVDevice
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/pcsvdevice/restart-pcsvdevice?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Restart-PcsvDevice
---

# Restart-PcsvDevice

## SYNOPSIS
Restarts a remote hardware device.

## SYNTAX

### ByNoConnectionParams (Default)
```
Restart-PcsvDevice [-TimeoutSec <UInt32>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByComputerName
```
Restart-PcsvDevice [-TargetAddress] <String> [-Credential] <PSCredential>
 [-ManagementProtocol] <ManagementProtocol> [[-Port] <UInt16>] [-Authentication <Authentication>] [-UseSSL]
 [-SkipCACheck] [-SkipCNCheck] [-SkipRevocationCheck] [-TimeoutSec <UInt32>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Restart-PcsvDevice -InputObject <CimInstance[]> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Restart-PcsvDevice** cmdlet restarts a device remotely by using Web Services for Management (WS-Management) or Intelligent Platform Management Interface (IPMI).
The cmdlet restarts the device if the current state of the device is enabled, or starts the device if the current state is other than enabled.
If you specify a device that is a Baseboard Management Controller (BMC), the cmdlet restarts the system that the BMC manages, and not the BMC.

## EXAMPLES

### Example 1: Restart a remote IPMI hardware device
```
PS C:\> $Credential = Get-Credential Admin
PS C:\> Restart-PCSVDevice -TargetAddress 10.0.0.29 -ManagementProtocol IPMI -Credential $Credential
Confirm
Are you sure you want to perform this action?
Performing operation 'Changing state of machine' on Target '10.10.0.29'.
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
```

This example restarts an IPMI device remotely.

The first command uses the **Get-Credential** cmdlet to create a credential, and then stores it in the **$Credential** variable.
The cmdlet prompts you for a user name and password.
For more information, type `Get-Help Get-Credential`.

The second command connects with the target computer that has the IP address 10.0.0.29 by using the IPMI management protocol The command specifies the credential object stored in the **$Credential** variable.
The command prompts the user for confirmation because restarting the system can cause a loss of unsaved state.

### Example 2: Restart an IPMI device remotely by using an object variable
```
PS C:\> $Credential = Get-Credential Admin
PS C:\> Get-PcsvDevice -TargetAddress 10.0.0.29 -ManagementProtocol IPMI -Credential $Credential | Restart-PcsvDevice -Confirm $False
```

This example restarts an IPMI device remotely by using an object variable to specify the device.

The first command uses the **Get-Credential** cmdlet to create a credential, and then stores it in the **$Credential** variable.
The cmdlet prompts you for a user name and password.
For more information, type `Get-Help Get-Credential`.

The second command uses the Get-PcsvDevice cmdlet to connect with the target computer that has the IP address 10.0.0.29 by using the IPMI management protocol and the credential object stored in the **$Credential** variable.
The command gets the remote device object and passes the object to the Restart-PcsvDevice cmdlet by using the pipeline operator.
The Restart-PcsvDevice cmdlet restarts the remote device.
The command sets the **Confirm** parameter to $False so the cmdlet does not prompt the user for confirmation to restart the device.

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

 If you specify Default for this parameter and a value of WSMAN for the **ManagementProtocol** parameter, the cmdlet uses Basic authentication.

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

Specify WSMAN for WS-Management devices that represent information by using Systems Management Architecture for Server Hardware (SMASH), Desktop and mobile Architecture for System Hardware (DASH) or Physical Computer System View profiles.
Refer to your hardware documentation for supported management protocols.

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
If you do not specify a port, the cmdlet uses the following default ports:

- IPMI and WSMAN over HTTP.
Port 623.
- WSMAN over HTTPS.
Port 664

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
Indicates that the client connects by using HTTPS without validating that a trusted CA signed the server certificate.

Do not specify this parameter unless you can establish trust in another way, such as if the remote computer is part of a network that is physically secure and isolated, or if the remote computer is a trusted host in a Windows Remote Management (WinRM) configuration.
Do not specify this parameter if you specify a value of IPMI for the **ManagementProtocol** parameter.

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
Indicates that the certificate common name of the server does not need to match the host name of the server.

Specify this parameter only for managing devices by using WS-Management over HTTPS.
Be sure to specify this parameter only for trusted computers.
Do not specify this parameter if you specify a value of IPMI for the **ManagementProtocol** parameter.

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
WS-Management encrypts all content transmitted over the network.
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

[Start-PcsvDevice](./Start-PcsvDevice.md)

[Stop-PcsvDevice](./Stop-PcsvDevice.md)

