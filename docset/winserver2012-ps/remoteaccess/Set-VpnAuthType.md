---
external help file: UnifiedRA_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: 8B4AA1E7-D102-4304-A987-91F99AFA9A1B
manager: dansimp
---

# Set-VpnAuthType

## SYNOPSIS
Sets the authentication type to be used for connecting to a VPN.

## SYNTAX

```
Set-VpnAuthType [-Type] <String> [[-RadiusServer] <String>] [[-SharedSecret] <String>] [-AsJob]
 [-CimSession <CimSession[]>] [-ComputerName <String>] [-EntrypointName <String>] [-MsgAuthenticator <String>]
 [-PassThru] [-RadiusPort <UInt16>] [-RadiusScore <Byte>] [-RadiusTimeout <UInt32>] [-ThrottleLimit <Int32>]
 [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Set-VpnAuthType** cmdlet is only used to toggle from one authentication type to another.
This cmdlet cannot be used to explicitly add any additional RADIUS servers if RADIUS authentication is being used. 

 -- The parameters for RADIUS authentication properties, such as the **MsgAuthenticator**, **RadiusPort**, **RadiusScore**, **RadiusServer**, **RadiusTimeout** and **SharedSecret** parameters, are applicable only when the ExternalRadius authentication is configured.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-VpnAuthType -Type "ExternalRadius" -RadiusServer "10.1.1.1" -SharedSecret "s3cr3t" -PassThru
Type             : ExternalRadius 
RadiusServerList : {10.1.1.1}
```

This example sets the VPN authentication type to be ExternalRadius.
A RADIUS server is specified along with the shared secret required to communicate with that RADIUS server.

### EXAMPLE 2
```
PS C:\>Set-VpnAuthType -Type "Windows" -PassThru
Type             : Windows 
RadiusServerList :
```

This example sets the VPN authentication type to be Windows, which causes authentication to happen on the Remote Access server computer.

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

### -ComputerName
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the VPN server computer specific tasks should be run.
If this parameter is specified, then the authentication type is configured for that VPN server.

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

### -EntrypointName
Identifies a site in a multi-site deployment for which the authentication type needs to be configured. 

If this parameter is not specified in a multi-site deployment, then this parameter value on which the cmdlet is run is used.
The server could also be represented by using the **ComputerName** parameter. 

If this parameter and the **ComputerName** parameter are specified and the **ComputerName** does not belong to the site represented by this parameter, then this parameter takes precedence and the authentication type is configured for it.

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

### -MsgAuthenticator
Specifies the enabled state for the usage of message authenticator.
The acceptable values for this parameter are:

 -- Enabled. 

 -- Disabled.
This is the default value. 

This parameter can be configured only if the **Type** parameter is specified to be ExternalRadius.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: Disable
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

### -RadiusPort
Specifies the port number on which the RADIUS server is accepting authentication requests. 

The default value is 1813. 

This parameter can be configured only if the **Type** parameter is specified to be ExternalRadius.

```yaml
Type: UInt16
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 1813
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RadiusScore
Specifies the initial score. 

The default value is 30. 

This parameter can be configured only if the **Type** parameter is specified to be ExternalRadius.

```yaml
Type: Byte
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 30
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RadiusServer
Specifies the IPv4 or IPv6 address, or host name, of the external RADIUS server that is used for accounting.
This parameter can be configured only if the **Type** parameter is specified to be ExternalRadius. 

Specifying the corresponding shared secret is mandatory.
The default values can be used for the other parameters.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RadiusTimeout
Specifies the RADIUS time out value, in seconds. 

The default value is 5 seconds. 

This parameter can be configured only if the **Type** parameter is specified to be ExternalRadius.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: 5
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SharedSecret
Specifies the shared secret between the Remote Access server and the specified external RADIUS server which is required for successful communication between the two servers. 
Note: The secret is specified in clear text. 

This parameter can be configured only if the **Type** parameter is specified to be ExternalRadius. 

When specifying a RADIUS server for authentication, it is mandatory to also specify the shared secret.
The default values can be used for the other parameters.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
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

### -Type
Specifies the authentication type.
The acceptable values for this parameter are:

 -- Windows. 

 -- ExternalRadius.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#VpnAuth
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The VpnAuth object consists of the following properties: 

 -- Authentication type: Windows or ExternalRadius. 

 -- Configured RADIUS servers: If external RADIUS authentication was set, then the configured RADIUS servers are displayed.

## NOTES

## RELATED LINKS

[Get-VpnAuthProtocol](./Get-VpnAuthProtocol.md)

[Set-VpnAuthProtocol](./Set-VpnAuthProtocol.md)

