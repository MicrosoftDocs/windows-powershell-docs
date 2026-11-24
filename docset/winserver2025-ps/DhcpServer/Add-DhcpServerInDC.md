---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DhcpServerInDC_v1.0.0.cdxml-help.xml
Module Name: DhcpServer
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/dhcpserver/add-dhcpserverindc?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Add-DhcpServerInDC
---

# Add-DhcpServerInDC

## SYNOPSIS
Adds the computer that runs the DHCP server service to the list of authorized DHCP server services in Active Directory.

## SYNTAX

```
Add-DhcpServerInDC [[-DnsName] <String>] [[-IPAddress] <IPAddress>] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Add-DhcpServerInDC** cmdlet adds the computer that runs the DHCP server service to the list of authorized Dynamic Host Configuration Protocol (DHCP) server services in the Active Directory.
A DHCP server service that runs on a domain joined computer must be authorized in Active Directory so that it can start leasing IP addresses on the network.

If you specify neither the *DnsName* nor the *IPAddress* parameter, the local server is added in the Active Directory.

If you specify only the *DnsName* parameter, the specified Domain Name System (DNS) name is added in Active Directory.

In both these cases, any of the IP addresses of the computer that runs the DHCP server service being added into the domain controller are added as part of the server object in Active Directory.

If you specify the *DnsName* and the *IPAddress* parameter, the object is added to domain controller that has specified values.

In addition to adding the computer that runs the DHCP server service in DC, this cmdlet also triggers the DHCP server service to perform an authorization check.

The trigger for authorization check is done even if the addition of computer that runs the DHCP server service fails with an object already exists error.

The following warning is displayed if the computer that runs the DHCP server service is already authorized and the trigger for the server authorization check succeeded:

`The DHCP server is already authorized in Active Directory.
The authorization check on the DHCP server has been initiated.`

The following warning is displayed if the computer that runs the DHCP server service is already authorized, but the trigger for the server authorization check failed:

`The DHCP server is already authorized in Active Directory.
Failed to initiate the authorization check on the DHCP server.
Error code: %d`

The following warning is displayed if the addition of the computer that runs the DHCP server service in Active Directory succeeded, but the trigger for the server authorization check failed:

`The DHCP server has been successfully authorized in Active Directory.
Failed to initiate the authorization check on the DHCP server.
Error code: %d`

If the addition of computer that runs the DHCP server service to Active Directory fails with an error other than object_already_exists_error, an error is returned and authorization check on the server is not triggered.

## EXAMPLES

### Example 1: Add an object for the DHCP server service
```
PS C:\> Add-DhcpServerInDC -DnsName "dhcpserver.contoso.com" -IPAddress 10.10.10.2
```

This example adds an object in the Active Directory domain for the DHCP server service that runs on the computer that has the DNS name dhcpserver.contoso.com and the IP address 10.10.10.2, and authorizes the DHCP server service to serve DHCP clients on the network.

### Example 2: Add an object for the DHCP server service with IP address lookup
```
PS C:\> Add-DhcpServerInDC -DnsName "dhcpserver.contoso.com"
```

This example adds an object in the Active Directory domain for the DHCP server service that runs on the computer that has the DNS name dhcpserver.contoso.com, and authorizes the DHCP server service to serve DHCP clients on the network.
The IP address for the DHCP server service object in Active Directory is obtained by looking up dhcpserver.contoso.com in DNS.

### Example 1: Add an object for the DHCP server service on the local computer with IP address lookup
```
PS C:\> Add-DhcpServerInDC
```

This example adds an object in the Active Directory domain for the DHCP server service that runs on the local computer.
The IP address for the computer that runs the DHCP server service in Active Directory is obtained by looking up the host name of the local computer in DNS.

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
Specifies the DNS name of the computer that runs the DHCP server service to be added to the list of authorized DHCP server services in Active Directory.

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
Specifies the IP address of the computer that runs the DHCP server service which is added to the list of authorized DHCP server services in Active Directory.

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

[Get-DhcpServerInDC](./Get-DhcpServerInDC.md)

[Remove-DhcpServerInDC](./Remove-DhcpServerInDC.md)

