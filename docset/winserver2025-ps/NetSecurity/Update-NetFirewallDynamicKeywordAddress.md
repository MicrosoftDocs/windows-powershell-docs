---
description: The Update-NetFirewallDynamicKeywordAddress cmdlet updates a dynamic keyword address.
external help file: NetFirewallDynamicKeywordAddress.cmdletDefinition.cdxml-help.xml
Module Name: NetSecurity
ms.date: 10/20/2021
online version: https://learn.microsoft.com/powershell/module/netsecurity/update-netfirewalldynamickeywordaddress?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Update-NetFirewallDynamicKeywordAddress
---

# Update-NetFirewallDynamicKeywordAddress

## SYNOPSIS
Updates a dynamic keyword address.

## SYNTAX

```
Update-NetFirewallDynamicKeywordAddress [-Id <String>] [-Addresses <String>] [-Append <Boolean>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Update-NetFirewallDynamicKeywordAddress** cmdlet updates a dynamic keyword address.
Specify a dynamic keyword address by ID.

A firewall rule can use dynamic keyword addresses instead of explicitly defining IP addresses for its remote address condition.

## EXAMPLES

### Example 1: Update a dynamic keyword address
```powershell
Update-NetFirewallDynamicKeywordAddress -Id "{01234567-89ab-cdef-0123-456789abcdef}" -Addresses 10.0.0.15
```

This example updates a dynamic keyword address to the specified value.
You can instead use the form `-Address` in the command, for clarity.
The braces are required for the ID.

### Example 2: Append an address to a dynamic keyword address
```powershell
Update-NetFirewallDynamicKeywordAddress -Id "{01234567-89ab-cdef-0123-456789abcdef}" -Addresses 192.0.0.1 -Append $True
```

This example adds the specified address to a dynamic keyword address.
The braces are required for the ID.

## PARAMETERS

### -Addresses
Specifies the addresses for the dynamic keyword address.

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

### -Append
Specifies whether to append the specified address to the dynamic keyword address.

```yaml
Type: Boolean
Parameter Sets: (All)
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
Specifies the GUID of the dynamic keyword address to update.

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

### System.Object
## NOTES

## RELATED LINKS

[Get-NetFirewallDynamicKeywordAddress](Get-NetFirewallDynamicKeywordAddress.md)

[New-NetFirewallDynamicKeywordAddress](New-NetFirewallDynamicKeywordAddress.md)

[Remove-NetFirewallDynamicKeywordAddress](Remove-NetFirewallDynamicKeywordAddress.md)
