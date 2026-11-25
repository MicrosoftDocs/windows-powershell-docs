---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamConfiguration.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/set-ipamconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-IpamConfiguration
---

# Set-IpamConfiguration

## SYNOPSIS
Modifies the configuration for the computer that runs the IPAM server.

## SYNTAX

### SetIpamConfiguration0
```
Set-IpamConfiguration [-Port] <UInt16> [-Force] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetIpamConfiguration4
```
Set-IpamConfiguration [-Force] [-PassThru] [-UpdateTables] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetIpamConfiguration3
```
Set-IpamConfiguration [-Force] [-PassThru] -HmacKey <SecureString> [-UpdateTables] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetIpamConfiguration2
```
Set-IpamConfiguration [-Force] [-PassThru] [-RefreshHmacKey] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetIpamConfiguration1
```
Set-IpamConfiguration [-Force] [-PassThru] [-ProvisioningMethod] <ProvisioningMethod> [[-GpoPrefix] <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-IpamConfiguration** cmdlet modifies the IP Address Management (IPAM) server configuration, including the TCP port over which the computer that runs the IPAM Remote Server Administration Tools (RSAT) client connects and communicates with the computer that runs the IPAM server.

## EXAMPLES

### Example 1: Modify an IPAM configuration
```
PS C:\> Set-IpamServerConfiguration -Port 45000  -PassThru -Force
Version : 1.3

 Port : 45000
```

This command changes the IPAM server management port to 45000 and suppresses the default confirmation text.
The command also returns the modified IPAM server configuration object.

The command includes the *PassThru* parameter, so it displays results to the console.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.

For more information about Windows PowerShell background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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

### -Force
Forces the command to run without asking for user confirmation.

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

### -GpoPrefix
Specifies the unique Group Policy Object (GPO) prefix name that IPAM uses to create the group policy objects.
Use this parameter only when the value of the *ProvisioningMethod* parameter is set to Automatic.

```yaml
Type: String
Parameter Sets: SetIpamConfiguration1
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HmacKey
Specifies a keyed-hash message authentication code (HMAC).

```yaml
Type: SecureString
Parameter Sets: SetIpamConfiguration3
Aliases:

Required: True
Position: Named
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
Specifies the TCP port number for communication between computers that run the IPAM RSAT client and the IPAM server.
IPAM lets you configure any port number in the range 1-65535  for communication between computers that run the IPAM client and server.
To avoid port conflicts with well-known ports, choose a port from the unassigned port range, 48620-49150.
By default, IPAM uses port number 48885.
The cmdlet configures appropriate custom IPAM server firewall rules for the specified new port, enables appropriate custom IPAM server firewall rules for the specified new port, and restarts the IPAM application pool to listen on the specified new port.

```yaml
Type: UInt16
Parameter Sets: SetIpamConfiguration0
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProvisioningMethod
Specifies a provisioning method.

The acceptable values for this parameter are: Automatic and Manual.

```yaml
Type: ProvisioningMethod
Parameter Sets: SetIpamConfiguration1
Aliases:
Accepted values: Automatic, Manual

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RefreshHmacKey
Indicates that the cmdlet refreshes the HMAC key, if the key has expired.

```yaml
Type: SwitchParameter
Parameter Sets: SetIpamConfiguration2
Aliases:

Required: True
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

### -UpdateTables
Indicates that the cmdlet updates the database tables.

```yaml
Type: SwitchParameter
Parameter Sets: SetIpamConfiguration4
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: SwitchParameter
Parameter Sets: SetIpamConfiguration3
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### None

## OUTPUTS

### Microsoft.Windows.Ipam.Commands.IpamConfiguration
This cmdlet returns an object that contains an IPAM configuration.

## NOTES

## RELATED LINKS

[Get-IpamConfiguration](./Get-IpamConfiguration.md)

