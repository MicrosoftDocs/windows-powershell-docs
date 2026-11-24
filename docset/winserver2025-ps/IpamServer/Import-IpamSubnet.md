---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: IpamSubnet.cdxml-help.xml
Module Name: IpamServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/ipamserver/import-ipamsubnet?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Import-IpamSubnet
---

# Import-IpamSubnet

## SYNOPSIS
Imports IP address subnet objects from the specified file into IPAM.

## SYNTAX

```
Import-IpamSubnet -Path <String> -AddressFamily <AddressFamily> [-ErrorPath <String>] [-Force]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Import-IpamSubnet** cmdlet imports IP address subnet objects from the specified file into the computer that runs the IP Address Management (IPAM) server.
The cmdlet logs objects that fail to import during the operation.
Use this cmdlet to import both virtualized and non-virtualized subnets.
The cmdlet adds new IP address subnet objects from the comma separated value .csv file into the computer that runs the IPAM server and edits the existing subnet objects with the updated information specified in the .csv file.
The .csv file can contain both virtualized and non-virtualized subnets.
If the file you import does not contain the columns NetworkType, ProviderAddressSpace and CustomerAddressSpace in the header, the cmdlet assumes all subnets are non-virtualized, and it adds them to the default address space.
If the header contains these columns, then the cmdlet uses the network type to add the subnets to given provider or customer address space.

## EXAMPLES

### Example 1: Import IPv4 subnets
```
PS C:\> Import-IpamSubnet -AddressFamily IPv4 -Path "C:\subnetsv4.csv" -Force
```

This command imports the IPv4 subnets from the file Subnetsv4.csv into the computer that runs IPAM.
The command adds the new subnets and modifies existing addresses.
The command records any errors in the default folder, %windir%\temp for the user, in .csv file format.

### Example 2: Import IPv4 subnets and specify the error path
```
PS C:\> Import-IpamAddress -AddressFamily IPv4 -Path "C:\addressv4.csv" -ErrorPath "C:\" -Force
```

This command imports IPv4 subnets from the file Subnetsv4.csv into the computer that runs the IPAM server.
The command adds new subnets and modifies existing subnets.

## PARAMETERS

### -AddressFamily
Specifies an address family of IP address range objects to import.
The acceptable values for this parameter are:

- IPv4
- IPv6

You can specify only one address family at a time using this cmdlet and the records in the file should match the address family you specify with this parameter.

```yaml
Type: AddressFamily
Parameter Sets: (All)
Aliases:
Accepted values: IPv4, IPv6

Required: True
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

### -ErrorPath
Specifies the fully qualified path, but not the name, of the error files that are created if one or more records fail to import.
The IPAM server generates file names  by prepending the string Error_ and appending the timestamp of the operation to the file name.
The default value of this parameter is the %windir%\temp folder.

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

### -Path
Specifies the fully qualified path and name of the file to import.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

## NOTES

## RELATED LINKS

[Add-IpamSubnet](./Add-IpamSubnet.md)

[Export-IpamSubnet](./Export-IpamSubnet.md)

[Get-IpamSubnet](./Get-IpamSubnet.md)

[Remove-IpamSubnet](./Remove-IpamSubnet.md)

[Set-IpamSubnet](./Set-IpamSubnet.md)

