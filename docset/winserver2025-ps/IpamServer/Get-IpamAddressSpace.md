---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamAddressSpace.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/get-ipamaddressspace?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-IpamAddressSpace
---

# Get-IpamAddressSpace

## SYNOPSIS
Gets address spaces in IPAM.

## SYNTAX

### ByName
```
Get-IpamAddressSpace [[-Name] <String[]>] [[-Type] <AddressSpaceType[]>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

### ByMapping
```
Get-IpamAddressSpace -MappingToProviderAddressSpace <String[]> [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-IpamAddressSpace** cmdlet gets address spaces in IP Address Management (IPAM).
You can specify the *MappingToProviderAddressSpace* parameter to get all customer address spaces that belong to a provider address group.
Customer address spaces in IPAM belong to a single provider address space.
You can use the *Name* parameter to get address spaces that match the address space names that you specify.
You can use the *Type* parameter to gets address spaces that match the types of address spaces that you specify.
You can use wildcards for the *Name*  parameter.
Use wildcards to gets all address spaces that have a specified prefix or suffix.
If you do not specify any parameters, the cmdlet gets all address spaces in IPAM.

## EXAMPLES

### Example 1: Get all address spaces
```
PS C:\> Get-IpamAddressSpace
```

This command gets all address spaces in IPAM.

### Example 2: Get an address space
```
PS C:\> Get-IpamAddressSpace -Name "ContosoMusic"
Name                           : ContosoMusic

Type                           : CustomerAddressSpace

Owner                          :

Description                    : Music Mp3

AssociatedProviderAddressSpace : MainDatacenter

Tenant                         : 4001

VMNetwork                      : ContosoMusic_Network

IsolationMethod                : NVGRE

Ipv4PercentageUtilized         : 62.0805369127517

Ipv6PercentageUtilized         : 0

CustomConfiguration            :
```

This command gets the address space named ContosoMusic.

### Example 3: Get all customer address spaces that map to a provider address space
```
PS C:\> Get-IpamAddressSpace -MappingToProviderAddressSpace "MainDataCenter"
Name                           : TreyResearch

Type                           : CustomerAddressSpace

Owner                          :

Description                    : A research and design company

AssociatedProviderAddressSpace : MainDatacenter

Tenant                         : 1001

VMNetwork                      : Trey Research_Network

IsolationMethod                : NVGRE

Ipv4PercentageUtilized         : 15.1515151515152

Ipv6PercentageUtilized         : 0

CustomConfiguration            :
Name                           : ContosoMusic

Type                           : CustomerAddressSpace

Owner                          :

Description                    : Music Mp3

AssociatedProviderAddressSpace : MainDatacenter

Tenant                         : 4001

VMNetwork                      : ContosoTunes_Network

IsolationMethod                : NVGRE

Ipv4PercentageUtilized         : 62.0805369127517

Ipv6PercentageUtilized         : 0

CustomConfiguration            :
```

This command gets all customer address spaces that belong to the provider address space named MainDataCenter.

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

### -MappingToProviderAddressSpace
Specifies an array of names of provider address spaces.
The cmdlet gets all customer address spaces which belong to the provider address spaces.

```yaml
Type: String[]
Parameter Sets: ByMapping
Aliases: PA

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies an array of names for the address spaces.
The cmdlet gets all address spaces that match the names that you specify.

```yaml
Type: String[]
Parameter Sets: ByName
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

### -Type
Specifies an array of address space types.

The acceptable values for this parameter are:

- ProviderAddressSpace
- CustomerAddressSpace

```yaml
Type: AddressSpaceType[]
Parameter Sets: ByName
Aliases:
Accepted values: ProviderAddressSpace, CustomerAddressSpace

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### IpamAddressSpace
This cmdlet returns an object that represents address space information, including the type of address space which can be CustomerAddressSpace or ProviderAddressSpace.

## NOTES

## RELATED LINKS

[Add-IpamAddressSpace](./Add-IpamAddressSpace.md)

[Set-IpamAddressSpace](./Set-IpamAddressSpace.md)

[Remove-IpamAddressSpace](./Remove-IpamAddressSpace.md)

