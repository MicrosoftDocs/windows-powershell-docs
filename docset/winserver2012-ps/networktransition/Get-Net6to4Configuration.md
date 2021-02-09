---
external help file: NetTransition_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 842E2785-8569-442C-A586-CCFD5B69CA60
manager: dansimp
---

# Get-Net6to4Configuration

## SYNOPSIS
Retrieves the 6to4 configuration of a computer or a Group Policy Object (GPO).

## SYNTAX

```
Get-Net6to4Configuration [-AsJob] [-CimSession <CimSession[]>] [-GPOSession <String>]
 [-IPInterface <CimInstance>] [-PolicyStore <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-Net6to4Configuration** cmdlet retrieves the 6to4 configuration of a computer or a Group Policy Object (GPO).

6to4 is an address assignment and router-to-router automatic tunneling technology that is described in RFC 3056: Connection of IPv6 Domains via IPv4 Cloudshttp://go.microsoft.com/fwlink/p/?LinkId=256388.
6to4 provides a globally-routable IPv6 address to a host with a public IPv4 address.
This IPv6 address can be used to connect to other 6to4 hosts or the IPv6 Internet.

## EXAMPLES

### Example 1: Get the 6to4 configuration
```
PS C:\>Get-Net6to4Configuration
```

This command retrieves the 6to4 configuration of a computer or a GPO.

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

### -GPOSession
Specifies the Group Policy session from which to retrieve the configuration information. 

You can use this parameter with the **NetGPO** cmdlets to aggregate multiple operations performed on a GPO. 

You cannot use this parameter with the **PolicyStore** parameter.

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

### -IPInterface
Specifies the interface for which to retrieve the 6to4 configuration.
If the interface is not a 6to4 interface, then the cmdlet does not return any 6to4 configuration.

```yaml
Type: CimInstance
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PolicyStore
Specifies the policy store from which to retrieve the configuration. 
The acceptable values for this parameter are:

 -- ActiveStore 

 -- PersistentStore 

 -- GPO 

To retrieve the configuration of a GPO, specify the GPO name using the following format: `Domain\GPOName`

You cannot use this parameter with the **GPOSession** parameter.

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
This cmdlet accepts no input objects.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_Net6to4Configuration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

This cmdlet returns a 6to4 configuration object.

## NOTES

## RELATED LINKS

[Reset-Net6to4Configuration](./Reset-Net6to4Configuration.md)

[Set-Net6to4Configuration](./Set-Net6to4Configuration.md)

