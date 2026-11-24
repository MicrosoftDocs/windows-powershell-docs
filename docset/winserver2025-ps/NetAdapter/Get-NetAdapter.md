---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetAdapter.cmdletDefinition.cdxml-help.xml
Module Name: NetAdapter
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/netadapter/get-netadapter?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetAdapter
---

# Get-NetAdapter

## SYNOPSIS
Gets the basic network adapter properties.

## SYNTAX

### ByName (Default)
```powershell
Get-NetAdapter [[-Name] <String[]>] [-IncludeHidden] [-Physical] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByInstanceID
```powershell
Get-NetAdapter -InterfaceDescription <String[]> [-IncludeHidden] [-Physical] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByIfIndex
```powershell
Get-NetAdapter -InterfaceIndex <UInt32[]> [-IncludeHidden] [-Physical] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetAdapter** cmdlet gets the basic network adapter properties.
By default only visible adapters are returned.
To see the common network adapter properties, pipe the output into the **Format-List** cmdlet.
To see all the properties, pipe the output to the **Format-List** cmdlet with the *Property* parameter specified as the wildcard character "*".
This cmdlet supports multiple views.
The default view is as a table.
To see more information regarding various network adapter identifiers use the **names** view using the **Format-Table** cmdlet with the *View* parameter specified as **name**.
To see more information regarding the miniport, device driver, such as driver date or version use the **driver** view using the **Format-Table** cmdlet with the *View* parameter specified as **driver**.

## EXAMPLES

### Example 1: Get all visible network adapters
```powershell
PS C:\> Get-NetAdapter -Name *
```

This command gets all of the visible network adapters.

### Example 2: Get all visible and hidden network adapters
```powershell
PS C:\> Get-NetAdapter -Name * -IncludeHidden
```

This command gets all of the network adapters.

### Example 3: Get all physical network adapters
```powershell
PS C:\> Get-NetAdapter -Name * -Physical
```

This command gets all of the physical network adapters.

### Example 4: Get a network adapter by the specified name
```powershell
PS C:\> Get-NetAdapter -Name "Ethernet 2"
```

This command gets the network adapter named Ethernet 2.

### Example 5: Get a network adapter by the specified name
```powershell
PS C:\> Get-NetAdapter -Name "E*2"
```

This command gets adapters starting with "E" and ending in "2" using wildcard characters.

### Example 6: Display the common properties for the specified network adapter
```powershell
PS C:\> Get-NetAdapter -Name "Ethernet 3" | Format-List -Property *
```

This command displays the common properties for the network adapter named Ethernet 3 and formats the list using the **Format-List** cmdlet.

### Example 7: Display all properties for the specified network adapter
```powershell
PS C:\> Get-NetAdapter -Name "Ethernet 6" | Format-List -Property *
```

This command displays all of the properties for the network adapter named Ethernet 6.

### Example 8: Get all network adapters using the interface description that matches a prefix pattern
```powershell
PS C:\> Get-NetAdapter -Name * -InterfaceDescription "VendorAdapter*"
```

This command gets all of the network adapters using the interface description that matches the prefix pattern VendorAdapter.

### Example 9: Display parameter values for all network adapters
```powershell
PS C:\> Get-NetAdapter -Name "*" -IncludeHidden | Format-List -Property "Name", "InterfaceDescription", "InterfaceName"
```

This command displays the *Name*, *InterfaceDescription*, and *InterfaceName* parameter values for all network adapters.

### Example 10: Get the visible network adapters on the specified server
```powershell
PS C:\> Get-NetAdapter -Name * -CimSession "Server5"
```

This command gets the visible network adapters on the server named Server5.
The server named Server5 can be a remote computer.

### Example 11: Get the visible network adapters and format the output
```powershell
PS C:\> Get-NetAdapter -Name * | Format-Table -View Driver
```

This command gets the visible network adapters and formats the output to present driver information.

### Example 12: Gets visible network adapters and format the output
```powershell
PS C:\> Get-NetAdapter -Name * | Format-Table -View Name
```

This command gets the visible network adapters and formats the output to present various names by which a network adapter can be identified such as the *Name*, *InterfaceDescription*, and *InterfaceName* parameter values.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job.
Use this parameter to run commands that take a long time to complete.
 The cmdlet immediately returns an object that represents the job and then displays the command prompt.
You can continue to work in the session while the job completes.
To manage the job, use the `*-Job` cmdlets.
To get the job results, use the [Receive-Job](https://go.microsoft.com/fwlink/?LinkID=113372) cmdlet.
 For more information about Windows PowerShell® background jobs, see [about_Jobs](https://go.microsoft.com/fwlink/?LinkID=113251).

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
Enter a computer name or a session object, such as the output of a [New-CimSession](/powershell/module/cimcmdlets/new-cimsession) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
Indicates that the cmdlet includes both visible and hidden network adapters in the operation.
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
Specifies an array of network adapter interface descriptions.
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
Specifies the network adapter interface index number as an array.

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
Specifies an array of network adapter names.

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
Indicates that the cmdlet gets all physical network adapters.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/NetAdapter
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

[CIM_NetworkAdapter class](/windows/win32/cimwin32prov/cim-networkadapter)

## NOTES

## RELATED LINKS

[Disable-NetAdapter](./Disable-NetAdapter.md)

[Enable-NetAdapter](./Enable-NetAdapter.md)

[Rename-NetAdapter](./Rename-NetAdapter.md)

[Restart-NetAdapter](./Restart-NetAdapter.md)

[Set-NetAdapter](./Set-NetAdapter.md)
