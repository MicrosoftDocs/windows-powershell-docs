---
external help file: DhcpServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: D364C9E8-C0BA-4C07-856A-2319617EE9D5
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Set-DhcpServerSetting

## SYNOPSIS
Sets one or more server level configuration parameters for the Dynamic Host Configuration Protocol (DHCP) server service.

## SYNTAX

```
Set-DhcpServerSetting [-ActivatePolicies <Boolean>] [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-ConflictDetectionAttempts <UInt32>] [-NapEnabled <Boolean>]
 [-NpsUnreachableAction <String>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-DhcpServerSetting** cmdlet sets one or more server level configuration parameters for the Dynamic Host Configuration Protocol (DHCP) server service.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-DhcpServerSetting -ComputerName dhcpserver.contoso.com -NapEnabled True -ConflictDetectionAttempts 1 -ActivatePolicies False
```

This example enables the NAP check, sets the number of conflict detection attempts to 1, and disables policy enforcement on the DHCP server service running on the computer named dhcpserver.contoso.com.

## PARAMETERS

### -ActivatePolicies
Specifies the enabled state for enforcement of policies.
The acceptable values for this parameter are: True or False.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

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

### -ComputerName
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the DHCP server service.

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

### -ConflictDetectionAttempts
Specifies the number of times that the DHCP server service should attempt conflict detection before leasing an IP address.
The acceptable values for this parameter are: 0 through 5.
The default value is 0.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NapEnabled
Specifies the enabled state for the Network Access Policy (NAP) check on the DHCP server service. 

If this parameter is set to True, then NAP is enabled and the DHCP server service uses the Network Policy Server (NPS) to perform a NAP check before leasing an IP address.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NpsUnreachableAction
Specifies that, if the **NapEnabled** parameter is set to True and the NPS server is unreachable, the default action that the DHCP server service performs.
The acceptable values for this parameter are: Full, Restricted, or NoAccess.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerSetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerSetting
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Get-DhcpServerSetting](./Get-DhcpServerSetting.md)

