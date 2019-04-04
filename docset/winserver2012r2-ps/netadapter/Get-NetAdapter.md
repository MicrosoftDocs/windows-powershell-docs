---
external help file: MSFT_NetAdapter.cmdletDefinition.cdxml-help.xml
Module Name: NetAdapter
online version: 
schema: 2.0.0
title: Get-NetAdapter
description: 
keywords: powershell, cmdlet
author: kenwith
manager: jasgro
ms.date: 2017-10-29
ms.topic: reference
ms.prod: powershell
ms.technology: powershell
ms.assetid: 265FB18B-0065-469F-88C4-55D6C7CF54D3
ms.author: kenwith
ms.reviewer: brianlic
---

# Get-NetAdapter

## SYNOPSIS
Gets the basic network adapter properties.

## SYNTAX

### ByName (Default)
```
Get-NetAdapter [[-Name] <String[]>] [-IncludeHidden] [-Physical] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByInstanceID
```
Get-NetAdapter -InterfaceDescription <String[]> [-IncludeHidden] [-Physical] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByIfIndex
```
Get-NetAdapter -InterfaceIndex <UInt32[]> [-IncludeHidden] [-Physical] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetAdapter** cmdlet gets the basic network adapter properties.
By default only visible adapters are returned.
To see the common network adapter properties, pipe the output into the Format-Listhttp://go.microsoft.com/fwlink/p/?LinkID=113302 cmdlet.
To see all the properties, pipe the output to the Format-Listhttp://go.microsoft.com/fwlink/p/?LinkID=113302 with the **Property** parameter specified as any (`*`).
This cmdlet supports multiple views.
The default view is as a table.
To see more information regarding various network adapter identifiers use the names view using the Format-Tablehttp://go.microsoft.com/fwlink/p/?LinkID=113303 cmdlet with the **View** parameter specified as name.
To see more information regarding the miniport (device driver) such as driver date or version use the driver view using the Format-Tablehttp://go.microsoft.com/fwlink/p/?LinkID=113303 cmdlet with the **View** parameter specified as driver.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NetAdapter -Name *
```

This example gets all of the visible network adapters.

### EXAMPLE 2
```
PS C:\>Get-NetAdapter -Name * -IncludeHidden
```

This example gets all of the network adapters.

### EXAMPLE 3
```
PS C:\>Get-NetAdapter -Name * -Physical
```

This example gets all of the physical network adapters.

### EXAMPLE 4
```
PS C:\>Get-NetAdapter -Name "Ethernet 2"

A version of the cmdlet that uses wildcard characters.
PS C:\>Get-NetAdapter -Name "E*2"

A version of the cmdlet that uses position and wildcard characters.
PS C:\>Get-NetAdapter "E*2"
```

This example gets the network adapter named Ethernet 2.

### EXAMPLE 5
```
PS C:\>Get-NetAdapter -Name "Ethernet 2" | Format-List -Property *
```

This example displays the common properties for the network adapter named Ethernet 2.

### EXAMPLE 6
```
PS C:\>Get-NetAdapter -Name "Ethernet 2" | Format-List -Property *
```

This example displays all of the properties for the network adapter named Ethernet 2,

### EXAMPLE 7
```
PS C:\>Get-NetAdapter -Name * -InterfaceDescription "VendorAdapter*"
```

This example gets all of network adapters using the interface description that matches the prefix pattern VendorAdapter.

### EXAMPLE 8
```
PS C:\>Get-NetAdapter -Name * -IncludeHidden | Format-List -Property Name, InterfaceDescription, InterfaceName
```

This example displays the **Name**, **InterfaceDescription**, and **InterfaceName** parameter values for all network adapters.

### EXAMPLE 9
```
PS C:\>Get-NetAdapter -Name * -CimSession Server5
```

This example gets the visible network adapters on the server named Server5.
Note: The server named Server5 can be a remote computer.

### EXAMPLE 10
```
PS C:\>Get-NetAdapter -Name * | Format-Table -View Driver
```

This example gets the visible network adapters and formats the output to present driver information.

### EXAMPLE 11
```
PS C:\>Get-NetAdapter -Name * | Format-Table -View Name
```

This example gets the visible network adapters and formats the output to present various names by which a network adapter can be identified such as the **Name**, **InterfaceDescription**, and **InterfaceIndex** parameter values.

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
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeHidden
Specifies both visible and hidden network adapters should be included.
By default only visible network adapters are included.
If a wildcard character is used in identifying a network adapter and this parameter has been specified, then the wildcard string is matched against both hidden and visible network adapters.

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

### -InterfaceDescription
Specifies the network adapter interface description.
For a physical network adapter this is typically the name of the vendor of the network adapter followed by a part number and description, such as `Contoso 12345 Gigabit Network Device`.

```yaml
Type: String[]
Parameter Sets: ByInstanceID
Aliases: ifDesc

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InterfaceIndex
Specifies the network adapter interface index number.

```yaml
Type: UInt32[]
Parameter Sets: ByIfIndex
Aliases: ifIndex

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the network adapter.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: ifAlias, InterfaceAlias

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Physical
Returns all physical network adapters.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/NetAdapter
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Format-List](http://go.microsoft.com/fwlink/p/?LinkID=113302)

[Format-Table](http://go.microsoft.com/fwlink/p/?LinkID=113303)

[Disable-NetAdapter](./Disable-NetAdapter.md)

[Enable-NetAdapter](./Enable-NetAdapter.md)

[Rename-NetAdapter](./Rename-NetAdapter.md)

[Restart-NetAdapter](./Restart-NetAdapter.md)

[Set-NetAdapter](./Set-NetAdapter.md)

