---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamServerInventory.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/set-ipamserverinventory?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-IpamServerInventory
---

# Set-IpamServerInventory

## SYNOPSIS
Modifies the properties of an infrastructure server in the IPAM server inventory.

## SYNTAX

```
Set-IpamServerInventory [-Name] <String> [[-NewName] <String>] [-ManageabilityStatus <ManageabilityStatus>]
 [-Owner <String>] [-ServerType <ServerRole[]>] [-Description <String>] [-AddCustomConfiguration <String>]
 [-RemoveCustomConfiguration <String>] [-Force] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-IpamServerInventory** cmdlet modifies the properties of an infrastructure server in an IP Address Management (IPAM) server inventory.
Use the server name or fully qualified domain name (FQDN) to identify the server.
If you only specify the server name, IPAM tries to resolve the server name.

## EXAMPLES

### Example 1: Modify the properties of a server
```
PS C:\> Set-IpamServerInventory -Name "Dhcp01" -ManageabilityStatus Managed -PassThru
```

This command modifies the properties of an infrastructure server named Dhcp01, and makes it manageable by IPAM.

The command includes the *PassThru* parameter, so it displays results to the console.

## PARAMETERS

### -AddCustomConfiguration
Specifies custom configuration to add to the server inventory.

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
Specifies a description for the server.

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

### -ManageabilityStatus
Specifies the manageability status of a server.

The acceptable values for this parameter are:

- Unspecified
- Managed
- Unmanaged

If you specify a value of Managed for this parameter, IPAM gathers data from the server.

```yaml
Type: ManageabilityStatus
Parameter Sets: (All)
Aliases:
Accepted values: Unspecified, Unmanaged, Managed

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the FQDN of the infrastructure server to modify.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ServerName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NewName
Specifies the new name or FQDN of an infrastructure server.
IPAM tries to resolve the name to an IP address and reports an error if it cannot resolve the name.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Owner
Specifies the owner of the Dynamic Host Configuration Protocol (DHCP) server.

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
Specifies the metadata fields to modify.
List the metadata as a series of custom field names, separated by semicolons (;).

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

### -ServerType
Specifies an array of server roles that are present on the server.

The acceptable values for this parameter are:

- DHCP
- DC
- DNS
- NPS

```yaml
Type: ServerRole[]
Parameter Sets: (All)
Aliases:
Accepted values: DC, DNS, DHCP, NPS

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

### IpamServerInventory
This cmdlet returns an object that represents an infrastructure server in IPAM system.

## NOTES

## RELATED LINKS

[Add-IpamServerInventory](./Add-IpamServerInventory.md)

[Get-IpamServerInventory](./Get-IpamServerInventory.md)

[Remove-IpamServerInventory](./Remove-IpamServerInventory.md)

