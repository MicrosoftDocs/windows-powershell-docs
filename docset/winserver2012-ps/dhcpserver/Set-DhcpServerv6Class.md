---
author: Kateyanne
external help file: DhcpServer_Cmdlets.xml
manager: dansimp
Module Name: DhcpServer
ms.author: v-kaunu
ms.reviewer: 
online version: https://docs.microsoft.com/powershell/module/dhcpserver/set-dhcpserverv6class?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Set-DhcpServerv6Class

## SYNOPSIS
Modifies the properties of an IPv6 vendor or user class on the Dynamic Host Configuration Protocol (DHCP) server service.

## SYNTAX

```
Set-DhcpServerv6Class [-Name] <String> [-Type] <String> [[-Data] <String>] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-Description <String>] [-PassThru]
 [-ThrottleLimit <Int32>] [-VendorId <UInt32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-DhcpServerv6Class** cmdlet modifies the properties of an IPv6 vendor or user class on the Dynamic Host Configuration Protocol (DHCP) server.
At least one of the **Description**, **VendorId**, and **Data** parameter must be specified.
The **VendorId** parameter must not be specified if a user class is being modified.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-DhcpServerv6Class -Name "User Class for Lab Computers" -Data "LabComputers" -Type User
```

This example sets the data for the DHCPv6 user class for lab computers.

### EXAMPLE 2
```
PS C:\>Set-DhcpServerv6Class -Name "Vendor Class for Printers" -Data "JetPrinters" -VendorId 100 -Type Vendor
```

This example sets the data and vendor identifier (ID) for the DHCPv6 vendor class for printers.

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

### -Data
Specifies the data for the specified vendor or user class.
This parameter value is expected to be present in the request from the client belonging to the vendor class.
The format for this parameter can be given as ANSI or hexadecimal.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Description
Specifies the description to set on the class being modified.

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

### -Name
Specifies the name of vendor or user class being modified.

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

### -Type
Specifies the type of the class.
The acceptable values for this parameter are: Vendor or User.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VendorId
Specifies the enterprise number of the vendor class.

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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Class
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerv6Class
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerv6Class](./Add-DhcpServerv6Class.md)

[Get-DhcpServerv6Class](./Get-DhcpServerv6Class.md)

[Remove-DhcpServerv6Class](./Remove-DhcpServerv6Class.md)

