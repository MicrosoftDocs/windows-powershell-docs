---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamBlock.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/remove-ipamblock?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-IpamBlock
---

# Remove-IpamBlock

## SYNOPSIS
Removes an address block from IPAM.

## SYNTAX

### ByKeySet
```
Remove-IpamBlock [-NetworkId] <String[]> [-StartIPAddress] <IPAddress[]> [-EndIPAddress] <IPAddress[]>
 [-DeleteAssociatedSubBlocks] [-Force] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Remove-IpamBlock -InputObject <CimInstance[]> [-DeleteAssociatedSubBlocks] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
The **Remove-IpamBlock** cmdlet removes an IP address block from IP Address Management (IPAM).
Specify an address block by using the *StartIPAddress* and *EndIPAddress* parameters, or use the *InputObject* parameter to specify the input to this cmdlet.
You can specify the *DeleteAssociatedSubBlocks* parameter to remove all the child IP address ranges mapped to the address block.
When you remove an address block, IPAM remaps all subnets and unmaps some subnets which it previously mapped to an address block.

## EXAMPLES

### Example 1: Remove an IP address block
```
PS C:\> Get-IpamBlock -NetworkId "10.15.0.0/16" -StartIPAddress 10.15.0.0 -EndIPAddress 10.15.255.255 | Remove-IpamBlock
Confirm

Deleting IP address block with NetworkId 10.15.0.0/16 from IPAM. Deleting the block may move the currently mapped IP address ranges within this block to Unmapped address space.Do you want to continue?

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

This command removes the IP address block from the network that has the ID 10.15.0.0/8/16.
The command specifies the start and end addresses for the address block.

### Example 2: Remove all child IP address ranges that belong to an address block
```
PS C:\> Get-IpamBlock -NetworkId "10.0.0.0/8" -StartIPAddress 10.0.0.0 -EndIPAddress 10.255.255.255 | Remove-IpamBlock -DeleteAssociatedSubBlocks
Confirm

This will permanently delete the given IP Block with NetworkId 10.0.0.0/8 from IPAM. Deleting the block may move the currently mapped IP address ranges within this block to Unmapped address space. Any sub-blocks associated with the given block will also be deleted. Do you want to continue?

[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

This command removes all child IP address ranges that belong to the address block from the network that has the ID 10.0.0.0/8.
The command specifies the start and end addresses for the address block.

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

### -DeleteAssociatedSubBlocks
Indicates that the cmdlet removes the child IP address ranges that belong to the address block.

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

### -EndIPAddress
Specifies an array of end addresses for IP address blocks.

```yaml
Type: IPAddress[]
Parameter Sets: ByKeySet
Aliases:

Required: True
Position: 3
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

### -NetworkId
Specifies the IP network prefix, in Classless Interdomain Routing (CIDR) notation, for the network blocks to be deleted.

```yaml
Type: String[]
Parameter Sets: ByKeySet
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

### -StartIPAddress
Specifies an array of start addresses for IP address blocks.

```yaml
Type: IPAddress[]
Parameter Sets: ByKeySet
Aliases:

Required: True
Position: 2
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

### IpamBlock
This cmdlet returns an object that represents an address block in IPAM.

## NOTES

## RELATED LINKS

[Get-IpamBlock](./Get-IpamBlock.md)

[Set-IpamBlock](./Set-IpamBlock.md)

[Add-IpamBlock](./Add-IpamBlock.md)

