---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
Module Name: NetworkController
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networkcontroller/new-networkcontrollernetworkinterface?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: New-NetworkControllerNetworkInterface
---

# New-NetworkControllerNetworkInterface

## SYNOPSIS

This cmdlet adds a new network interface resource to the Network Controller

## SYNTAX

```
New-NetworkControllerNetworkInterface [-ResourceId] <String> [[-Tags] <PSObject>]
 [-Properties] <NetworkInterfaceProperties> [[-Etag] <String>] [[-ResourceMetadata] <ResourceMetadata>]
 [-Force] -ConnectionUri <Uri> [-CertificateThumbprint <String>] [-Credential <PSCredential>]
 [-PassInnerException] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
This cmdlet adds a new network interface resource to the Network Controller

## EXAMPLES

### Example 1

This example retrieves an existing network interface named nw1 from the Network Controller.
Then, it updates the network interface to allow MAC spoofing.

```
$nw=Get-NetworkControllerNetworkInterface -ConnectionUri https://networkcontroller -ResourceId nw1

$nw.Properties.PortSettings.MacSpoofingEnabled="Enabled"
New-NetworkControllerNetworkInterface -ConnectionUri https://networkcontroller -ResourceId nw1 -Properties $nw.Properties
```

## PARAMETERS

### -CertificateThumbPrint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.
This is the certificate thumbprint of the certificate.
This thumbprint must also be provided in the ClientCertificateThumbprint parameter in the Install-NetworkController or Set-NetworkController cmdlet so that Network Controller can authorize this user.

```yaml
Type: string
Parameter Sets: (All)
Aliases:
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConnectionUri
Specifies the Uniform Resource Identifier (URI) of the Network Controller, used by all Representational State Transfer (REST) clients to connect to Network Controller.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:
Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies a user credential that has permission to perform this action.
The default value is the current user.This user must be present in the security group provided in the ClientSecurityGroup parameter in the Install-NetworkController cmdlet.

```yaml
Type: PSCredential
Parameter Sets: (All)
Aliases:
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Etag
Specifies the entity tag (ETag) parameter of the resource.
An ETag (entity tag) is an HTTP response header returned by an HTTP-compliant web server used to determine change in the content of a resource at a given URL.
The value of the header is an opaque string representing the state of the resource at the time the response was generated.

```yaml
Type: string
Parameter Sets: (All)
Aliases:
Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -PassInnerException
This thumbprint must also be provided in the **ClientCertificateThumbprint** parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

The thumbprint must be provided only if the network controller client authentication is X509 certificates.
**Get-NetworkController** retrieves that client authentication and authorization information.

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

### -Properties
Following properties of a network interface can be added/changed:
1.
MAC address
2.
IP address
3.
Whether this is a host virtual NIC
4.
Whether the NIC is primary
5.
Internal DNS name label of the NIC
6.
Port settings of the NIC
   a.
Whether MAC spoofing is enabled
   b.
Whether ARP guard is enabled.
ARP guard will allow only addresses specified in ArpFilter to pass through the port
   c.
ArpFilter: IP list for allowed addresses when arpGuard is enabled
   d.
Whether DHCP guard is enabled.
Specifies whether to drop DHCP messages from a virtual machine claiming to be a DHCP server.
   e.
Storm limit: the number of broadcast, multicast, and unknown unicast packets per second a virtual machine is allowed to send through the specified virtual network adapter.
A value of zero (0) means there is no limit.
   f.
Port Flow Limit: Specifies the maximum number of flows that can be executed for the port.
A value of blank or zero (0) means there is no limit
   g.
IovWeight: Specifies whether single-root I/O virtualization (SR-IOV) is to be enabled on this virtual network adapter.
The range of the value is typically from 0 through 100.
Value of 0 disables SR-IOV on the virtual network adapter.
   h.
IovInterruptModeration: Specifies the interrupt moderation value for a single-root I/O virtualization (SR-IOV) virtual function assigned to a virtual network adapter.
Allowed values are "default", "adaptive", "off", low", "medium", and "high".
   i.
IovQueuePairsRequested: Specifies the number of hardware queue pairs to be allocated to an SR-IOV virtual function.
If receive-side scaling (RSS) is required, and if the physical network adapter that binds to the virtual switch supports RSS on SR-IOV virtual functions, then more than one queue pair is required.
Allowed values range from 1 to 4294967295
   j.
VmqWeight: Specifies whether virtual machine queue (VMQ) is to be enabled on the virtual network adapter.
The relative weight describes the affinity of the virtual network adapter to use VMQ.
The range of value is typically from 0 through 100.
Value of 0 disables VMQ on the virtual network adapter.
   h.
QosSettings: Reference to QoS Settings applied on the interface
7.
DNS servers assigned to the interface
8.
IP configuration of the interface
    a.
Private IP address
    b.
Private IP address allocation method
    c.
Load balancer backend address pools associated with the IP configuration
    d.
Load balancer inbound NAT Rules associated with the IP configuration
    e.
Subnet associated with the IP configuration
    f.
Public IP address associated with the IP configuration
    g.
Access control list associated with the IP Configuration
    h.
Service insertion rules associated with the IP configuration

```yaml
Type: NetworkInterfaceProperties
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Specifies the unique ID of the network interface

```yaml
Type: string
Parameter Sets: (All)
Aliases:
Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceMetadata
This parameter contains metadata information for the client, such as the tenant ID, group ID, and resource name.

```yaml
Type: ResourceMetadata
Parameter Sets: (All)
Aliases:
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tags
@{Text=}

```yaml
Type: psobject
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
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Windows.NetworkController.NetworkInterfaceProperties

Following properties of a network interface can be added/changed:
1.
MAC address
2.
IP address
3.
Whether this is a host virtual NIC
4.
Whether the NIC is primary
5.
Internal DNS name label of the NIC
6.
Port settings of the NIC
   a.
Whether MAC spoofing is enabled
   b.
Whether ARP guard is enabled.
ARP guard will allow only addresses specified in ArpFilter to pass through the port
   c.
ArpFilter: IP list for allowed addresses when arpGuard is enabled
   d.
Whether DHCP guard is enabled.
Specifies whether to drop DHCP messages from a virtual machine claiming to be a DHCP server.
   e.
Storm limit: the number of broadcast, multicast, and unknown unicast packets per second a virtual machine is allowed to send through the specified virtual network adapter.
A value of zero (0) means there is no limit.
   f.
Port Flow Limit: Specifies the maximum number of flows that can be executed for the port.
A value of blank or zero (0) means there is no limit
   g.
IovWeight: Specifies whether single-root I/O virtualization (SR-IOV) is to be enabled on this virtual network adapter.
The range of the value is typically from 0 through 100.
Value of 0 disables SR-IOV on the virtual network adapter.
   h.
IovInterruptModeration: Specifies the interrupt moderation value for a single-root I/O virtualization (SR-IOV) virtual function assigned to a virtual network adapter.
Allowed values are "default", "adaptive", "off", low", "medium", and "high".
   i.
IovQueuePairsRequested: Specifies the number of hardware queue pairs to be allocated to an SR-IOV virtual function.
If receive-side scaling (RSS) is required, and if the physical network adapter that binds to the virtual switch supports RSS on SR-IOV virtual functions, then more than one queue pair is required.
Allowed values range from 1 to 4294967295
   j.
VmqWeight: Specifies whether virtual machine queue (VMQ) is to be enabled on the virtual network adapter.
The relative weight describes the affinity of the virtual network adapter to use VMQ.
The range of value is typically from 0 through 100.
Value of 0 disables VMQ on the virtual network adapter.
   h.
QosSettings: Reference to QoS Settings applied on the interface
7.
DNS servers assigned to the interface
8.
IP configuration of the interface
    a.
Private IP address
    b.
Private IP address allocation method
    c.
Load balancer backend address pools associated with the IP configuration
    d.
Load balancer inbound NAT Rules associated with the IP configuration
    e.
Subnet associated with the IP configuration
    f.
Public IP address associated with the IP configuration
    g.
Access control list associated with the IP Configuration
    h.
Service insertion rules associated with the IP configuration

## OUTPUTS

### System.Object

## NOTES
## RELATED LINKS

