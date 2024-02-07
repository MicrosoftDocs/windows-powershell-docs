---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_Net6to4Configuration.cdxml-help.xml
Module Name: NetworkTransition
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networktransition/get-net6to4configuration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Net6to4Configuration
---

# Get-Net6to4Configuration

## SYNOPSIS
Retrieves the 6to4 configuration of a computer or a GPO.

## SYNTAX

```
Get-Net6to4Configuration [-IPInterface <CimInstance>] [-PolicyStore <String>] [-GPOSession <String>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-Net6to4Configuration** cmdlet retrieves the 6to4 configuration of a computer or a Group Policy Object (GPO).

6to4 is an address assignment and router-to-router automatic tunneling technology that is described in [RFC 3056: Connection of IPv6 Domains via IPv4 Clouds](https://go.microsoft.com/fwlink/p/?LinkId=256388).
6to4 provides a globally-routable IPv6 address to a host with a public IPv4 address.
This IPv6 address can be used to connect to other 6to4 hosts or the IPv6 Internet.

## EXAMPLES

### Example 1: Get the 6to4 configuration
```
PS C:\>Get-Net6to4Configuration
```

This command retrieves the 6to4 configuration of a computer or a GPO.

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

### -GPOSession
Specifies the Group Policy session from which to retrieve the configuration information.

You can use this parameter with the **NetGPO** cmdlets to aggregate multiple operations performed on a GPO.

You cannot use this parameter with the *PolicyStore* parameter.

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

### -IPInterface
Specifies the interface for which to retrieve the 6to4 configuration.
If the interface is not a 6to4 interface, then the cmdlet does not return any 6to4 configuration.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PolicyStore
Specifies the policy store from which to retrieve the configuration.
The acceptable values for this parameter are:


- ActiveStore

- PersistentStore

- GPO

To retrieve the configuration of a GPO, specify the GPO name using the following format: Domain\GPOName

You cannot use this parameter with the *GPOSession* parameter.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet accepts no input objects.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_Net6to4Configuration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

This cmdlet returns a 6to4 configuration object.

## NOTES

## RELATED LINKS

[Reset-Net6to4Configuration](./Reset-Net6to4Configuration.md)

[Set-Net6to4Configuration](./Set-Net6to4Configuration.md)

