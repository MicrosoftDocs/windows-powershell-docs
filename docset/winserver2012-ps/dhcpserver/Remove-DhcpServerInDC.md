---
external help file: DhcpServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: 06B5393E-D9BB-4B52-AAA8-A72CD3669436
manager: dansimp
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
---

# Remove-DhcpServerInDC

## SYNOPSIS
Deletes the specified Dynamic Host Configuration Protocol (DHCP) server service from the list of authorized DHCP server services in Active Directory (AD).

## SYNTAX

```
Remove-DhcpServerInDC [[-DnsName] <String>] [[-IPAddress] <IPAddress>] [-AsJob] [-CimSession <CimSession[]>]
 [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-DhcpServerInDC** cmdlet deletes the specified Dynamic Host Configuration Protocol (DHCP) server service from the list of authorized DHCP server services in Active Directory (AD).

When neither the **DnsName** nor the **IPAddress** parameter is specified, then the local DHCP server service will be removed from the list of authorized DHCP server services in AD.

If only the **DnsName** parameter is specified, then the DHCP server service running on the computer with the specified DNS name will be removed from the list of authorized DHCP server services in AD.

If the **DnsName** and the **IPAddress** parameters are specified, then the DHCP server service running on the computer with specified values will be removed from the list of authorized DHCP server services in AD.

If only the **IPAddress** parameter is specified, then an error is returned.

In addition to removing the computer running the DHCP server service in DC, this cmdlet also triggers the DHCP server service to perform an authorization check.

The trigger for authorization check will be done even if the removal of computer running the DHCP server service fails with an object already exists error.

The following warning will be displayed if the computer running the DHCP server service does not exist in AD and the trigger for the server authorization check succeeded: 

 - `The DHCP server is already de-authorized in Active Directory.
The authorization check on the DHCP server has been initiated.`

The following warning will be displayed if the computer running the DHCP server service does not exist in AD, but the trigger for the server authorization check failed: 

 - `The DHCP server is already de-authorized in Active Directory.
Failed to initiate the authorization check on the DHCP server.
Error code: %d`

The following warning will be displayed if the deletion of the computer running the DHCP server service in AD succeeded, but the trigger for the server authorization check failed: 

 - `The DHCP server has been successfully de-authorized in Active Directory.
Failed to initiate the authorization check on the DHCP server.
Error code: %d`

If the deletion of computer running the DHCP server service to AD fails with an error other than object_does not already_exists_error, then an error is returned and authorization check on the server is not triggered.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Remove-DhcpServerInDC -DnsName dhcpserver.contoso.com -IPAddress 10.10.10.2
```

This example deletes the object in the AD domain for the DHCP server service running on the computer with the DNS name dhcpserver.contoso.com and the IP address 10.10.10.2, thereby de-authorizing the DHCP server service for clients on the network.

### EXAMPLE 2
```
PS C:\>Remove-DhcpServerInDC -DnsName dhcpserver.contoso.com
```

This example deletes an object in the AD domain for the DHCP server service running on the computer with the DNS name dhcpserver.contoso.com, thereby de-authorizing the DHCP server service for the clients on the network.
The IP address for computer running the DHCP server service object in AD will be obtained by looking up dhcpserver.contoso.com in DNS.

### EXAMPLE 3
```
PS C:\>Remove-DhcpServerInDC
```

This example deletes an object in the AD domain for the DHCP server service running on the local computer.

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
Specifies the DNS name of the computer, on which the DHCP server service is running, to de-authorize.

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
Specifies the IP address of the computer, on which the DHCP server service is running, to de-authorize.

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

[Add-DhcpServerInDC](./Add-DhcpServerInDC.md)

[Get-DhcpServerInDC](./Get-DhcpServerInDC.md)

