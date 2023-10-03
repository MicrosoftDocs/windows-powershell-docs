---
external help file: MSFT_NetAdapterRss.cmdletDefinition.cdxml-help.xml
Module Name: NetAdapter
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/netadapter/get-netadapterrss?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-NetAdapterRss
---

# Get-NetAdapterRss

## SYNOPSIS
Gets receive side scaling (RSS) properties of the network adapter.

## SYNTAX

### ByName (Default)
```
Get-NetAdapterRss [[-Name] <String[]>] [-IncludeHidden] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
 [-AsJob] [<CommonParameters>]
```

### ByInstanceID
```
Get-NetAdapterRss -InterfaceDescription <String[]> [-IncludeHidden] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetAdapterRss** cmdlet gets receive side scaling (RSS) properties of the network adapters that support RSS.
RSS is a scalability technology that distributes the receive network traffic among multiple processors by hashing the header of the incoming packet and using an indirection table.
Without RSS in Windows Server® 2012 and later, network traffic is received on the first processor which can quickly reach full utilization limiting receive network throughput.
Various properties can be configured to optimize the performance of RSS.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-NetAdapterRss -Name *
```

This example gets all of the RSS capable network adapters.

### EXAMPLE 2
```
PS C:\>Get-NetAdapterRss -Name MyAdapter
```

This example gets the RSS properties of the network adapter named MyAdapter.

### EXAMPLE 3
```
PS C:\>Get-NetAdapterRss -Name MyAdapter | Format-List -Property *
```

This example displays all of the RSS properties of the network adapter named MyAdapter.

### EXAMPLE 4
```
PS C:\>Get-NetAdapterRss -Name * | Where-Object -FilterScript { $_.Enabled }
```

This example gets all of the RSS capable network adapters with RSS enabled.

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
Aliases: ifDesc, InstanceID

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapterRssSettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Format-List](https://go.microsoft.com/fwlink/p/?LinkID=113302)

[Where-Object](https://go.microsoft.com/fwlink/p/?LinkID=113423)

[Disable-NetAdapterRss](./Disable-NetAdapterRss.md)

[Enable-NetAdapterRss](./Enable-NetAdapterRss.md)

[Set-NetAdapterRss](./Set-NetAdapterRss.md)

