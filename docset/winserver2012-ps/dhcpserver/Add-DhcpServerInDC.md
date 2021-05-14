---
external help file: DhcpServer_Cmdlets.xml
Module Name: DhcpServer
online version: https://docs.microsoft.com/powershell/module/dhcpserver/add-dhcpserverindc?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Add-DhcpServerInDC

## SYNOPSIS
Adds the computer running the DHCP server service to the list of authorized Dynamic Host Configuration Protocol (DHCP) server services in Active Directory (AD).

## SYNTAX

```
Add-DhcpServerInDC [[-DnsName] <String>] [[-IPAddress] <IPAddress>] [-AsJob] [-CimSession <CimSession[]>]
 [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Add-DhcpServerInDC** cmdlet adds the computer running the DHCP server service to the list of authorized Dynamic Host Configuration Protocol (DHCP) server services in the Active Directory (AD).
A DHCP server service running on a domain joined computer needs to be authorized in AD so that it can start leasing IP addresses on the network.

If neither the **DnsName** nor the **IPAddress** parameter is specified, the local server will be added in the AD.

If only the **DnsName** parameter is specified, the specified Domain Name System (DNS) name will be added in AD.

In both these cases, any of the IP addresses of the computer running the DHCP server service being added into the domain controller are added as part of the server object in AD.

If the **DnsName** and the **IPAddress** parameter are specified, the object will be added to domain controller with specified values.

In addition to adding the computer running the DHCP server service in DC, this cmdlet also triggers the DHCP server service to perform an authorization check.

The trigger for authorization check will be done even if the addition of computer running the DHCP server service fails with an object already exists error.

The following warning will be displayed if the computer running the DHCP server service is already authorized and the trigger for the server authorization check succeeded: 

 - `The DHCP server is already authorized in Active Directory.
The authorization check on the DHCP server has been initiated.`

The following warning will be displayed if the computer running the DHCP server service is already authorized, but the trigger for the server authorization check failed: 

 - `The DHCP server is already authorized in Active Directory.
Failed to initiate the authorization check on the DHCP server.
Error code: %d`

The following warning will be displayed if the addition of the computer running the DHCP server service in AD succeeded, but the trigger for the server authorization check failed: 

 - `The DHCP server has been successfully authorized in Active Directory.
Failed to initiate the authorization check on the DHCP server.
Error code: %d`

If the addition of computer running the DHCP server service to AD fails with an error other than object_already_exists_error, then an error is returned and authorization check on the server is not triggered.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Add-DhcpServerInDC -DnsName dhcpserver.contoso.com -IPAddress 10.10.10.2
```

This example adds an object in the AD domain for the DHCP server service running on the computer with the DNS name dhcpserver.contoso.com and the IP address 10.10.10.2, and authorizes the DHCP server service to serve DHCP clients on the network.

### EXAMPLE 2
```
PS C:\>Add-DhcpServerInDC -DnsName dhcpserver.contoso.com
```

This example adds an object in the AD domain for the DHCP server service running on the computer with the DNS name dhcpserver.contoso.com, and authorizes the DHCP server service to serve DHCP clients on the network.
The IP address for the DHCP server service object in AD will be obtained by looking up dhcpserver.contoso.com in DNS.

### EXAMPLE 3
```
PS C:\>Add-DhcpServerInDC
```

This example adds an object in the AD domain for the DHCP server service running on the local computer.
The IP address for the computer running the DHCP server service in AD will be obtained by looking up the hostname of the local computer in DNS.

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
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DnsName
Specifies the DNS name of the computer running the DHCP server service to be added to the list of authorized DHCP server services in AD.

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
Specifies the IP address of the computer running the DHCP server service which is added to the list of authorized DHCP server services in AD.

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

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

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

