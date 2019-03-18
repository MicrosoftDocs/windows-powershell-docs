---
external help file: DhcpServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 89E1F016-9E38-4553-AE4B-569FACDDD265
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# Get-DhcpServerv4OptionDefinition

## SYNOPSIS
Gets the DHCPv4 option definition for the specified option identifiers (IDs).

## SYNTAX

```
Get-DhcpServerv4OptionDefinition [[-OptionId] <UInt32[]>] [[-VendorClass] <String>] [-All] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DhcpServerv4OptionDefinition** cmdlet gets the DHCPv4 option definitions for the specified option identifiers (IDs).

If the **OptionId** parameter is not specified, then all of the option definitions, which are not vendor specific, are returned.
The **VendorClass** parameter acts as a filter for option definitions for the specified vendor class only.

If the **All** parameter is specified, then all of the option definitions including the vendor class specific option definitions will be returned.

If the **All** and **OptionId** parameters are specified, then all of the option definitions including the vendor class specific option definitions with the specified option ID will be returned.

If the **All** and the **VendorClass** parameters are specified, then the **All** parameter is ignored.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-DhcpServerv4OptionDefinition -ComputerName dhcpserver.contoso.com
```

This example gets the standard, or non-vendor specific, DHCPv4 option definitions on the DHCP server service running on the computer named dhcpserver.contoso.com.

### EXAMPLE 2
```
PS C:\> Get-DhcpServerv4OptionDefinition -ComputerName dhcpserver.contoso.com -All
```

This example gets all of the DHCPv4 option definitions including vendor specific option definition present on the DHCP server service.

### EXAMPLE 3
```
PS C:\> Get-DhcpServerv4OptionDefinition -ComputerName dhcpserver.contoso.com -OptionId 23
```

This example gets the DHCPv4 option definition for the specified option.

### EXAMPLE 4
```
PS C:\> Get-DhcpServerv4OptionDefinition -ComputerName dhcpserver.contoso.com -VendorClass "Microsoft Windows Options"
```

This example gets all the DHCPv4 option definitions for the specified vendor class.

## PARAMETERS

### -All
Gets all of the option definitions on the DHCP server service including vendor specific option definitions.

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
Specifies the DNS name, or IPv4 or IPv6 address, of the target computer running the Dynamic Host Configuration Protocol (DHCP) server service.

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

### -OptionId
Specifies the numerical identifiers of the options for which the option definitions are requested.
If nothing is specified, then all of the DHCPv4 option definitions are returned.

```yaml
Type: UInt32[]
Parameter Sets: (All)
Aliases: 

Required: False
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

### -VendorClass
Returns the option definitions only for the specified vendor class.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4OptionValue
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv4OptionDefinition[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv4OptionDefinition](./Add-DhcpServerv4OptionDefinition.md)

[Remove-DhcpServerv4OptionDefinition](./Remove-DhcpServerv4OptionDefinition.md)

[Set-DhcpServerv4OptionDefinition](./Set-DhcpServerv4OptionDefinition.md)

