---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamCapabilities.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/enable-ipamcapability?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-IpamCapability
---

# Enable-IpamCapability

## SYNOPSIS
Enables an optional capability on the IPAM server.

## SYNTAX

```
Enable-IpamCapability [-Capability] <Capability> [-Force] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Enable-IpamCapability** cmdlet enables an optional IPAM capability on the Internet Protocol address management (IPAM) server.
Specify the name of the capability to enable.
Use the **Disable-IpamCapability** cmdlet to disable an optional IPAM capability on the IPAM server.

Currently, IP address tracking is the only optional capability available.
When you run this cmdlet, IPAM starts gathering audit data.
IPAM tracks IP addresses by correlating DHCP lease events on managed DHCP servers with user and computer authentication events on managed domain controllers and NPS servers.

## EXAMPLES

### Example 1: Enable the IP address tracking capability in IPAM
```
PS C:\> Enable-IpamCapability -Capability IpAddressTracking
Confirm

Enabling IpAddressTracking.Do you want to continue?.

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

This command enables the IP address tracking capability in IPAM.

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

### -Capability
Specifies the name of an optional IPAM capability.
The cmdlet disables the optional IPAM capability.
Currently, IpAddressTracking is the only valid value for this parameter.

```yaml
Type: Capability
Parameter Sets: (All)
Aliases:
Accepted values: IpAddressTracking

Required: True
Position: 0
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

### IpamCapability
This cmdlet returns an object that represents an optional capability provided by an IPAM server.

## NOTES

## RELATED LINKS

[Get-IpamCapability](./Get-IpamCapability.md)

[Disable-IpamCapability](./Disable-IpamCapability.md)

