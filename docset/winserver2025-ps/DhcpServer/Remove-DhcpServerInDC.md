---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerInDC_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/remove-dhcpserverindc?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-DhcpServerInDC
---

# Remove-DhcpServerInDC

## SYNOPSIS
Deletes the specified DHCP server service from the list of authorized DHCP server services in Active Directory.

## SYNTAX

```
Remove-DhcpServerInDC [[-DnsName] <String>] [[-IPAddress] <IPAddress>] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Remove-DhcpServerInDC** cmdlet deletes the specified Dynamic Host Configuration Protocol (DHCP) server service from the list of authorized DHCP server services in Active Directory.

When you specify neither the *DnsName* nor the *IPAddress* parameter, the local DHCP server service is removed from the list of authorized DHCP server services in Active Directory.

If you specify only the *DnsName* parameter, the DHCP server service that runs on the computer that has the specified DNS name is removed from the list of authorized DHCP server services in AD.

If you specify the *DnsName* and the *IPAddress* parameters, the DHCP server service that runs on the computer that has specified values is removed from the list of authorized DHCP server services in Active Directory.

If you specify only the *IPAddress* parameter, an error is returned.

In addition to removing the computer that runs the DHCP server service in DC, this cmdlet also triggers the DHCP server service to perform an authorization check.

The trigger for authorization check is performed even if the removal of computer that runs the DHCP server service fails with an object already exists error.

The following warning is displayed if the computer that runs the DHCP server service does not occur in Active Directory and the trigger for the server authorization check succeeded:

`The DHCP server is already de-authorized in Active Directory.
The authorization check on the DHCP server has been initiated.`

The following warning is displayed if the computer that runs the DHCP server service does not occur in AD, but the trigger for the server authorization check failed:

`The DHCP server is already de-authorized in Active Directory.
Failed to initiate the authorization check on the DHCP server.
Error code: %d`

The following warning is displayed if the deletion of the computer that runs the DHCP server service in Active Directory succeeded, but the trigger for the server authorization check failed:

`The DHCP server has been successfully de-authorized in Active Directory.
Failed to initiate the authorization check on the DHCP server.
Error code: %d`

If the deletion of computer that runs the DHCP server service to Active Directory fails with an error other than object_does not already_exists_error, an error is returned and authorization check on the server is not triggered.

## EXAMPLES

### Example 1: Delete an object by DNS name and address
```
PS C:\> Remove-DhcpServerInDC -DnsName "dhcpserver.contoso.com" -IPAddress 10.10.10.2
```

This example deletes the object in the Active Directory domain for the DHCP server service that runs on the computer that has the DNS name dhcpserver.contoso.com and the IP address 10.10.10.2, thereby de-authorizing the DHCP server service for clients on the network.

### Example 2: Delete an object by DNS name with IP address lookup
```
PS C:\> Remove-DhcpServerInDC -DnsName "dhcpserver.contoso.com"
```

This example deletes an object in the Active Directory domain for the DHCP server service that runs on the computer that has the DNS name dhcpserver.contoso.com, thereby de-authorizing the DHCP server service for the clients on the network.
The IP address for computer that runs the DHCP server service object in Active Directory is obtained by looking up dhcpserver.contoso.com in DNS.

### Example 3: Delete an object on the local computer
```
PS C:\> Remove-DhcpServerInDC
```

This example deletes an object in the Active Directory domain for the DHCP server service that runs on the local computer.

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

### -DnsName
Specifies the DNS name of the computer, on which the DHCP server service runs, to de-authorize.

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

### -IPAddress
Specifies the IP address of the computer, on which the DHCP server service runs, to de-authorize.

```yaml
Type: IPAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
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

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerInDC
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerInDC
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerInDC](./Add-DhcpServerInDC.md)

[Get-DhcpServerInDC](./Get-DhcpServerInDC.md)

