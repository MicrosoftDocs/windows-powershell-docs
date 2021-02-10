---
external help file: UnifiedRA_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 6E7980F4-55A8-4013-8BE7-BB0A16F49DB9
manager: dansimp
---

# Remove-VpnS2SInterface

## SYNOPSIS
Removes a specified site-to-site (S2S) interface.

## SYNTAX

```
Remove-VpnS2SInterface [-Name] <String[]> [-AsJob] [-CimSession <CimSession[]>] [-Force] [-PassThru]
 [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-VpnS2SInterface** cmdlet removes a specified site-to-site (S2S) interface.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-VpnS2SInterface -Name TestVpnS2SInterface
Confirm 
The VPN site-to-site network adapter TestVpnS2SInterface will be deleted. Are you sure you want to continue? 
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

This example removes the S2S VPN interface named TestVpnS2SInterface.

### EXAMPLE 2
```
PS C:\>Get-VpnS2SInterface -Name TestVpnS2SInterface | Remove-VpnS2SInterface -PassThru
Confirm 
The VPN site-to-site network adapter TestVpnS2SInterface will be deleted. Are you sure you want to continue? 
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y 
 
Name                 Destination          AdminStatus  ConnectionState IPv4Subnet 
----                 -----------          -----------  --------------- ---------- 
TestVpnS2SInterface  {30.0.0.1}           True         Disconnected    {131.0.1.0/24:254, 121.0.0.0/16:124}
```

This example retrieves the S2S VPN interface named TestVpnS2SInterface and removes it.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

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
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
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
Specifies the name of the interface.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#VpnS2SInterface[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-VpnS2SInterface](./Add-VpnS2SInterface.md)

[Clear-VpnS2SInterfaceStatistics](./Clear-VpnS2SInterfaceStatistics.md)

[Connect-VpnS2SInterface](./Connect-VpnS2SInterface.md)

[Disconnect-VpnS2SInterface](./Disconnect-VpnS2SInterface.md)

[Get-VpnAuthProtocol](./Get-VpnAuthProtocol.md)

[Get-VpnS2SInterface](./Get-VpnS2SInterface.md)

[Get-VpnS2SInterfaceStatistics](./Get-VpnS2SInterfaceStatistics.md)

[Get-VpnServerIPsecConfiguration](./Get-VpnServerIPsecConfiguration.md)

[Set-VpnAuthProtocol](./Set-VpnAuthProtocol.md)

[Set-VpnS2SInterface](./Set-VpnS2SInterface.md)

[Set-VpnServerIPsecConfiguration](./Set-VpnServerIPsecConfiguration.md)

