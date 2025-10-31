---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DnsServerZoneTransferPolicy_v1.0.0.cdxml-help.xml
Module Name: DnsServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dnsserver/remove-dnsserverzonetransferpolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DnsServerZoneTransferPolicy
---

# Remove-DnsServerZoneTransferPolicy

## SYNOPSIS
Removes a zone transfer policy from a DNS server.

## SYNTAX

### Server (Default)
```
Remove-DnsServerZoneTransferPolicy [-PassThru] [-Name] <String> [-ComputerName <String>] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Zone
```
Remove-DnsServerZoneTransferPolicy [-PassThru] [-Name] <String> [-ComputerName <String>] [-Force]
 [-ZoneName] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DnsServerZoneTransferPolicy** cmdlet removes a zone transfer policy from a Domain Name System (DNS) server.
Specify a zone name to remove zone level policies.
If you do not specify a zone, this cmdlet removes server level policies.

## EXAMPLES

### Example 1: Remove all zone transfer policies for a zone
```
PS C:\> Get-DnsServerZoneTransferPolicy -ZoneName "contoso.com" | Remove-DnsServerZoneTransferPolicy -ZoneName "contoso.com" -Force
```

This command gets all zone transfer policies on a zone named contoso.com by using the **Get-DnsServerZoneTransferPolicy** cmdlet.
The command passes the policies to the current cmdlet by using the pipeline operator.
The current cmdlet deletes each of the policies from this zone.
This command specifies the *Force* parameter.
It removes policies without prompting you to confirm.

### Example 2: Remove a server level zone transfer policy
```
PS C:\> Remove-DnsServerZoneTransferPolicy -Name "InternalTransfers" -PassThru
Confirm
Removing the server level policy InternalTransfers from the DNS server SERVER01-T10. Do you want to continue?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y

Name                                 ProcessingOrder                      IsEnabled                            Action
----                                 ---------------                      ---------                            ------
InternalTransfers                    2                                    True                                 Ignore
```

This command removes server level zone transfer policy named InternalTransfers.

### Example 3: Remove a zone level zone transfer policy
```
PS C:\> Remove-DnsServerZoneTransferPolicy -Name "InternalTransfers" -ZoneName "contoso.com" -Force
```

This command removes the zone transfer policy named InternalTransfers on the zone named contoso.com.

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

### -ComputerName
Specifies a remote DNS server.
You can specify an IP address or any value that resolves to an IP address, such as an FQDN, host name, or NETBIOS name.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

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

### -Name
Specifies the name of the policy to remove.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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

### -ZoneName
Specifies the name of a DNS zone.
This cmdlet removes the policy from the zone that this parameter specifies.

```yaml
Type: String
Parameter Sets: Zone
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#DnsServerPolicy

## NOTES

## RELATED LINKS

[Add-DnsServerZoneTransferPolicy](./Add-DnsServerZoneTransferPolicy.md)

[Get-DnsServerZoneTransferPolicy](./Get-DnsServerZoneTransferPolicy.md)

[Set-DnsServerZoneTransferPolicy](./Set-DnsServerZoneTransferPolicy.md)

[Start-DnsServerZoneTransfer](./Start-DnsServerZoneTransfer.md)

[Add-DnsServerQueryResolutionPolicy](./Add-DnsServerQueryResolutionPolicy.md)

