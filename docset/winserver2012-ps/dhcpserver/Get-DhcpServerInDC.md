---
external help file: DhcpServer_Cmdlets.xml
online version: 
schema: 2.0.0
ms.assetid: D92DBC65-9B8B-460F-9497-67299F86D43D
manager: dansimp
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# Get-DhcpServerInDC

## SYNOPSIS
Retrieves the list of authorized computers running the Dynamic Host Configuration Protocol (DHCP) server service from Active Directory (AD).

## SYNTAX

```
Get-DhcpServerInDC [-AsJob] [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-DhcpServerInDC** cmdlet retrieves the list of authorized computers running the Dynamic Host Configuration Protocol (DHCP) server service from Active Directory (AD).
Only a computer running a DHCP server service that is authorized in AD can lease IP addresses on the network.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-DhcpServerInDC
```

This example gets the list of all computers running the DHCP server service which are authorized in the AD domain.

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

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root/Microsoft/Windows/DHCP/DhcpServerInDC[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Add-DhcpServerInDC](./Add-DhcpServerInDC.md)

[Remove-DhcpServerInDC](./Remove-DhcpServerInDC.md)

