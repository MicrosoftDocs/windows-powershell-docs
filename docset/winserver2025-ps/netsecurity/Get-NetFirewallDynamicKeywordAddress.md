---
description: The Get-NetFirewallDynamicKeywordAddress cmdlet gets dynamic keyword addresses.
external help file: NetFirewallDynamicKeywordAddress.cmdletDefinition.cdxml-help.xml
Module Name: NetSecurity
ms.date: 10/20/2021
online version: https://learn.microsoft.com/powershell/module/netsecurity/get-netfirewalldynamickeywordaddress?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetFirewallDynamicKeywordAddress
---

# Get-NetFirewallDynamicKeywordAddress

## SYNOPSIS
Gets dynamic keyword addresses.

## SYNTAX

### GetAll (Default)
```
Get-NetFirewallDynamicKeywordAddress [-All] [-PolicyStore <String>] [-AllAutoResolve] [-AllNonAutoResolve]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ById
```
Get-NetFirewallDynamicKeywordAddress [-Id] <String[]> [-PolicyStore <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetFirewallDynamicKeywordAddress** cmdlet gets dynamic keyword addresses.
You can specify an ID or get all `AutoResolve` or all non-`AutoResolve` dynamic keyword addresses.

## EXAMPLES

### Example 1: Get a dynamic keyword address
```powershell
Get-NetFirewallDynamicKeywordAddress -Id "{01234567-89ab-cdef-0123-456789abcdef}" -PolicyStore "ContosoPolicyStore"
```

This example gets the specified dynamic keyword address from the specified policy store.
The braces are required for the ID.

### Example 2: Get all AutoResolve dynamic keyword addresses
```powershell
Get-NetFirewallDynamicKeywordAddress -PolicyStore "ContosoPolicyStore" -AllAutoResolve
```

This example gets all the `AutoResolve` dynamic keyword addresses from the specified policy store.

## PARAMETERS

### -All
Indicates that the cmdlet gets all dynamic keyword addresses.

```yaml
Type: SwitchParameter
Parameter Sets: GetAll
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllAutoResolve
Indicates that the cmdlet gets all `AutoResolve` dynamic keyword addresses.

```yaml
Type: SwitchParameter
Parameter Sets: GetAll
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllNonAutoResolve
Indicates that the cmdlet gets all non-`AutoResolve` dynamic keyword addresses.

```yaml
Type: SwitchParameter
Parameter Sets: GetAll
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Id
Specifies the GUIDs of the dynamic keyword addresses to get.

```yaml
Type: String[]
Parameter Sets: ById
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PolicyStore
Specifies the policy store from which to get dynamic key addresses.
A policy store is a container for firewall and IPsec policy.

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
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
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

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance

### Microsoft.Management.Infrastructure.CimInstance#root/standardcimv2/MSFT_NetFirewallDynamicKeywordAddress

## NOTES

## RELATED LINKS

[New-NetFirewallDynamicKeywordAddress](New-NetFirewallDynamicKeywordAddress.md)

[Remove-NetFirewallDynamicKeywordAddress](Remove-NetFirewallDynamicKeywordAddress.md)

[Update-NetFirewallDynamicKeywordAddress](Update-NetFirewallDynamicKeywordAddress.md)
