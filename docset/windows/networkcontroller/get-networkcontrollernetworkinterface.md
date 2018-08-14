---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: coreyp
author: coreyp-at-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.NetworkController.Powershell.dll-help.xml
keywords: powershell, cmdlet
manager: jasgro
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-NetworkControllerNetworkInterface
ms.assetid: F9FA653D-84BB-47D8-B876-F6C3E03852ED
---

# Get-NetworkControllerNetworkInterface

## SYNOPSIS
Retrieves the settings of a network interface from the Network Controller

## SYNTAX

```
Get-NetworkControllerNetworkInterface [[-ResourceId] <String[]>] -ConnectionUri <Uri>
 [-CertificateThumbprint <String>] [-Credential <PSCredential>] [-PassInnerException] [<CommonParameters>]
```

## DESCRIPTION
Retrieves the settings of a network interface from the Network Controller

## EXAMPLES

### Example 1

This example retrieves the configuration of a network interface called nw1, from the Network Controller.
```
Get-NetworkControllerNetworkInterface -ConnectionUri https://networkcontroller -ResourceId nw1
```

## PARAMETERS

### -CertificateThumbprint
Specifies the digital public key X.509 certificate of a user account that has permission to perform this action.This is the certificate thumbprint of the certificate.This thumbprint must also be provided in the *ClientCertificateThumbprint* parameter in the **Install-NetworkController** or **Set-NetworkController** cmdlet so that Network Controller can authorize this user.

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
Specifies a user credential that has permission to perform this action.The default value is the current user.This user must be present in the security group provided in the *ClientSecurityGroup* parameter in the **Install-NetworkController** cmdlet.

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

### -PassInnerException
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

### -ResourceId
Specifies the unique identifier for the networkinterface resource.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### 

Following settings of a network interface can be retrieved:
1. MAC address
2. IP address
3. Whether this is a host virtual NIC
4. Whether the NIC is primary
5. Internal DNS name label of the NIC
6. Port settings of the NIC   
 - Whether MAC spoofing is enabled   
 - Whether ARP guard is enabled.  ARP guard will allow only addresses specified in ArpFilter to pass through the port   
 - ArpFilter: IP list for allowed addresses when arpGuard is enabled   
 - Whether DHCP guard is enabled. Specifies whether to drop DHCP messages from a virtual machine claiming to be a DHCP server.   
 - Storm limit: the number of broadcast, multicast, and unknown unicast packets per second a virtual machine is allowed to send through the specified virtual network adapter. A value of zero (0) means there is no limit.   
 - Port Flow Limit: Specifies the maximum number of flows that can be executed for the port. A value of blank or zero (0) means there is no limit   
 - IovWeight: Specifies whether single-root I/O virtualization (SR-IOV) is to be enabled on this virtual network adapter. The range of the value is typically from 0 through 100. Value of 0 disables SR-IOV on the virtual network adapter.   
 - IovInterruptModeration: Specifies the interrupt moderation value for a single-root I/O virtualization (SR-IOV) virtual function assigned to a virtual network adapter. Allowed values are “default�?, “adaptive�?, “off�?, low�?, “medium�?, and “high�?.    
 - IovQueuePairsRequested: Specifies the number of hardware queue pairs to be allocated to an SR-IOV virtual function. If receive-side scaling (RSS) is required, and if the physical network adapter that binds to the virtual switch supports RSS on SR-IOV virtual functions, then more than one queue pair is required. Allowed values range from 1 to 4294967295   
 - VmqWeight: Specifies whether virtual machine queue (VMQ) is to be enabled on the virtual network adapter. The relative weight describes the affinity of the virtual network adapter to use VMQ. The range of value is typically from 0 through 100. Value of 0 disables VMQ on the virtual network adapter.   
 - QosSettings: Reference to QoS Settings applied on the interface
7. DNS servers assigned to the interface
8. IP configuration of the interface    
 - Private IP address    
 - Private IP address allocation method    
 - Load balancer backend address pools associated with the IP configuration    
 - Load balancer inbound NAT Rules associated with the IP configuration    
 - Subnet associated with the IP configuration    
 - Public IP address associated with the IP configuration    
 - Access control list associated with the IP Configuration    
 - Service insertion rules associated with the IP configuration
9. Server where the network interface is hosted
10. Virtual port association of the interface

## NOTES

## RELATED LINKS

