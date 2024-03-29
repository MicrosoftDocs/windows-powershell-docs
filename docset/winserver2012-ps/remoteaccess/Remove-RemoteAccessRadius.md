---
external help file: UnifiedRA_Cmdlets.xml
Module Name: RemoteAccess
online version: https://learn.microsoft.com/powershell/module/remoteaccess/remove-remoteaccessradius?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Remove-RemoteAccessRadius

## SYNOPSIS
Removes an external RADIUS server from being used for VPN authentication, accounting for both DirectAccess (DA) and VPN, or one-time password (OTP) authentication for DA.

## SYNTAX

```
Remove-RemoteAccessRadius [-ServerName] <String> [-Purpose] <String> [-AsJob] [-CimSession <CimSession[]>]
 [-ComputerName <String>] [-EntrypointName <String>] [-PassThru] [-ThrottleLimit <Int32>] [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Remove-RemoteAccessRadius** cmdlet removes an external RADIUS server from being used for VPN authentication, Accounting for both DirectAccess (DA) and VPN, or one-time password (OTP) authentication for DA as follows. 

 -- Accounting RADIUS configuration applies to both DA and VPN. 

 -- OTP RADIUS configuration applies only to DA. 

 -- Authentication RADIUS configuration applies only to VPN.

A RADIUS server configuration for Accounting and OTP are global in nature, such that the configurations apply to the entire Remote Access deployment.
RADIUS server configuration for VPN applies only to a specific VPN server, and all servers in a load balancing cluster, or if multi-site is deployed, to all VPN servers at a site.

The following behaviors describe aspects of this cmdlet. 

 -- If a RADIUS server is currently being used for multiple purposes, then it can be removed for one or more of the purposes.
However, the cmdlet would have to be run separately for each purpose. 

 -- If the last RADIUS server being used for accounting is removed, then the accounting type automatically switches to Windows accounting. 

 -- The User is not allowed to delete the last RADIUS server being used for VPN authentication if Radius authentication is configured. 

 -- When RADIUS accounting or RADIUS authentication is disabled, using the Set-RemoteAccessAccounting and Set-VpnAuthType cmdlets, then the RADIUS servers is use do not show up in the configuration and therefore cannot be explicitly removed.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Get-RemoteAccessRadius
ServerName      Purpose         Score   Timeout(s)  Port    AccountingOnOffMsg MsgAuthenticator 
----------      -------         -----   ----------  ----    ------------------ ---------------- 
10.1.1.1        Accounting       30       5         1813    Disabled 
10.1.3.1        Accounting       30       5         1813    Disabled 
10.1.1.1        Authentication   30       5         1812                       Disabled 
10.1.2.1        Authentication   30       5         1812                       Disabled 


PS C:\>Remove-RemoteAccessRadius -ServerName 10.1.1.1 -Purpose Authentication -PassThru
ServerName : 10.1.1.1 
Purpose    : Authentication 


PS C:\>Get-RemoteAccessRadius

ServerName      Purpose         Score   Timeout(s)  Port    AccountingOnOffMsg MsgAuthenticator 
----------      -------         -----   ----------  ----    ------------------ ---------------- 
10.1.1.1        Accounting       30       5         1813    Disabled 
10.1.3.1        Accounting       30       5         1813    Disabled 
10.1.2.1        Authentication   30       5         1812                       Disabled
```

This example removes a RADIUS server from being used for authentication.
The RADIUS server named 10.1.1.1 is being used for both authentication and accounting.
This cmdlet removes the server from being used for authentication.

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
Specifies the IPv4 or IPv6 address, or host name, of the computer on which the Remote Access server computer specific tasks should be run.
If this parameter is specified when removing a RADIUS server for authentication, then it is removed for the VPN server represented by this parameter.

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
Specifies a site in a multi-site deployment.
It is applicable only to RADIUS server configuration for VPN authentication.
It is not applicable to RADIUS accounting and OTP. 

When the parameter is specified it indicates that the Radius server for VPN authentication should be removed for that site. 

If this parameter is not specified in a multi-site deployment, then this parameter value on which the cmdlet is run is used.
The server could also be represented by using the **ComputerName** parameter. 

If this parameter and **ComputerName** are specified and the **ComputerName** does not belong to the site represented by this parameter, then this parameter takes precedence and the RADIUS server is removed from it.

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

### -Purpose
Specifies the purpose for which the external RADIUS server is being removed.
The acceptable values for this parameter are:

 -- Authentication. 

 -- Accounting. 

 -- Otp.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ServerName
Specifies the IPv4 or IPv6 address, or host name, of the external RADIUS server that needs to be removed.

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

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#RemoteAccessRadiusServerPurpose[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The array of RemoteAccessRadiusServerPurpose objects consists of the following properties: 

 -- The IPv4 or IPv6 address of the RADIUS server that was removed. 

 -- The purpose for which the server was removed.

## NOTES

## RELATED LINKS

[Set-RemoteAccessAccounting](./Set-RemoteAccessAccounting.md)

[Set-VpnAuthType](./Set-VpnAuthType.md)

