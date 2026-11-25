---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamAddressSpace.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/set-ipamaddressspace?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-IpamAddressSpace
---

# Set-IpamAddressSpace

## SYNOPSIS
Modifies address spaces in IPAM.

## SYNTAX

### ByName
```
Set-IpamAddressSpace [-Name] <String[]> [-NewName <String>] [-Owner <String>] [-Description <String>]
 [-AddCustomConfiguration <String>] [-RemoveCustomConfiguration <String>]
 [-AssociatedProviderAddressSpace <String>] [-Tenant <String>] [-VmNetwork <String>]
 [-IsolationMethod <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-IpamAddressSpace -InputObject <CimInstance[]> [-NewName <String>] [-Owner <String>] [-Description <String>]
 [-AddCustomConfiguration <String>] [-RemoveCustomConfiguration <String>]
 [-AssociatedProviderAddressSpace <String>] [-Tenant <String>] [-VmNetwork <String>]
 [-IsolationMethod <String>] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-IpamAddressSpace** cmdlet modifies address spaces in IP Address Management (IPAM).
Specify the address spaces to modify, or use the *InputObject* parameter to specify an *IpamAddressSpace* object to modify.
You must specify at least one optional parameter in addition to the *Name* parameter or *InputObject* parameter.

## EXAMPLES

### Example 1: Rename an address space
```
PS C:\> Set-IpamAddressSpace -Name "OneDataCenter" -NewName "MainDataCenter" -PassThru
Name                           : MainDataCenter

Type                           : ProviderAddressSpace

Owner                          :

Description                    :

AssociatedProviderAddressSpace :

Tenant                         :

VMNetwork                      :

IsolationMethod                :

Ipv4PercentageUtilized         : 66.8888888888889

Ipv6PercentageUtilized         : 0

CustomConfiguration            :
```

This command renames the address space named OneDataCenter to MainDataCenter.

The command includes the *PassThru* parameter, so it displays results to the console.

### Example 2: Change the provider address space for a customer address space
```
PS C:\> Get-IpamAddressSpace -Name "WoodgroveAddSpace" | Set-IpamAddressSpace -AssociatedProviderAddressSpace "MainDataCenter" -PassThru


Name                           : WoodgroveAddSpace

Type                           : CustomerAddressSpace

Owner                          :

Description                    : Equities and Mutual funds business

AssociatedProviderAddressSpace : MainDatacenter

Tenant                         : 5001

VMNetwork                      : WoodgroveBank_Network

IsolationMethod                : NVGRE

Ipv4PercentageUtilized         : 38.3838383838384

Ipv6PercentageUtilized         : 0

CustomConfiguration            :
```

This command changes the provider address space that is associated with a customer address space.
The command uses the **Get-IpamAddressSpace** cmdlet to get an **IpamAddressSpace** object that contains the customer address space named WoodgroveAddSpace.
The command passes the object to the **Set-IpamAddressSpace** cmdlet by using the pipeline operator.
The command sets the provider address space named MainDataCenter for the customer address space stored in the **IpamAddressSpace** object.

## PARAMETERS

### -AddCustomConfiguration
Specifies semi-colon separated name/value pairs.
This parameter specifies custom metadata that are associated with the address space.

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

### -AssociatedProviderAddressSpace
Specifies the provider address space that is associated with the customer address space.
Customer address spaces in IPAM belong to a single provider address space.

```yaml
Type: String
Parameter Sets: (All)
Aliases: PA

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -Description
Specifies a description of the address space.

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

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IsolationMethod
Specifies the network virtualization mechanism for the address space.
The acceptable values for this parameter are:

- NVGRE
- IPRewrite

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
Specifies an array of names of the address spaces.
The cmdlet modifies the address spaces.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewName
Specifies a new name for the address space.

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

### -Owner
Specifies the owner of the address space.

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

### -RemoveCustomConfiguration
Specifies a semi-colon separated string of custom field names.
The cmdlet removes the custom field names from the address spaces.

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

### -Tenant
Specifies the tenant ID, as a string, that is associated with the customer address space.
You must specify a tenant ID that is associated with the virtual machine network that you specify for the *VmNetwork* parameter.

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

### -VmNetwork
Specifies the name of the virtual machine network for the customer address space.
You must specify a virtual network that is associated with the tenant that you specify for the *Tenant* parameter.

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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### IpamAddressSpace
This cmdlet returns an object that represents an address space in IPAM.

## NOTES

## RELATED LINKS

[Get-IpamAddressSpace](./Get-IpamAddressSpace.md)

[Add-IpamAddressSpace](./Add-IpamAddressSpace.md)

[Remove-IpamAddressSpace](./Remove-IpamAddressSpace.md)

