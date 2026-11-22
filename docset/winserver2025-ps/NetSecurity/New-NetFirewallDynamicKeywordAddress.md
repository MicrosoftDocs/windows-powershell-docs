---
description: The New-NetFirewallDynamicKeywordAddress cmdlet creates a dynamic keyword address.
external help file: NetFirewallDynamicKeywordAddress.cmdletDefinition.cdxml-help.xml
Module Name: NetSecurity
ms.date: 10/20/2021
online version: https://learn.microsoft.com/powershell/module/netsecurity/new-netfirewalldynamickeywordaddress?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetFirewallDynamicKeywordAddress
---

# New-NetFirewallDynamicKeywordAddress

## SYNOPSIS
Creates a dynamic keyword address.

## SYNTAX

```
New-NetFirewallDynamicKeywordAddress [-Id <String>] [-Keyword <String>] [-Addresses <String>]
 [-AutoResolve <Boolean>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **New-NetFirewallDynamicKeywordAddress** cmdlet creates a dynamic keyword address.

A firewall rule can use dynamic keyword addresses instead of explicitly defining IP addresses for its remote address condition.

## EXAMPLES

### Example 1: Create dynamic keyword address with AutoResolve
```powershell
$GUID = New-Guid
New-NetFirewallDynamicKeywordAddress -Id $('{' + $GUID + '}') -Keyword "ContosoSubnet" -AutoResolve $True
```

This example creates an `AutoResolve` dynamic keyword address.

The first command creates a GUID and assigns it to `$GUID`.

The second command creates the dynamic address with the specified keyword.
The braces are required for the ID.

### Example 2: Create dynamic keyword address
```powershell
$GUID = New-Guid
New-NetFirewallDynamicKeywordAddress -Id $('{' + $GUID + '}') -Keyword "ContosoServerSubnet" -Addresses 10.0.0.21
```

This example creates a non-`AutoResolve` dynamic keyword address.

The first command creates a GUID and assigns it to `$GUID`.

The second command creates a dynamic address with the specified keyword.
The address does not use AutoResolve.

You can use the form `-Address` instead of `Addresses` in the command, for clarity.
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

### -AutoResolve
Whether the dynamic key address uses `AutoResolve`.
For `AutoResolve`, the keyword field represents a resolvable name and the IP addresses aren't defined when the dynamic key address is created.

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
Specifies a GUID for the dynamic keyword address.
Wrap the GUID value in braces.

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

### -Keyword
Specifies the keyword for the dynamic keyword address.

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

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

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

### None

## OUTPUTS

### System.Object

## NOTES

## RELATED LINKS

[Get-NetFirewallDynamicKeywordAddress](Get-NetFirewallDynamicKeywordAddress.md)

[Remove-NetFirewallDynamicKeywordAddress](Remove-NetFirewallDynamicKeywordAddress.md)

[Update-NetFirewallDynamicKeywordAddress](Update-NetFirewallDynamicKeywordAddress.md)
