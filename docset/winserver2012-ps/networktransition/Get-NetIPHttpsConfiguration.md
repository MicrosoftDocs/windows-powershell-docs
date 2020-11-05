---
external help file: NetTransition_Cmdlets.xml
online version: 
schema: 2.0.0
ms.reviewer:
ms.author: v-kaunu
author: Kateyanne
ms.assetid: E3DB6861-8AC4-43D7-96A7-E832280B9A10
manager: dansimp
---

# Get-NetIPHttpsConfiguration

## SYNOPSIS
Gets the IP-HTTPS configuration from a computer or a Group Policy Object (GPO).

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-NetIPHttpsConfiguration [-AsJob] [-CimSession <CimSession[]>] [-PolicyStore <String>] [-Profile <String[]>]
 [-ProfileActivated <Boolean[]>] [-ThrottleLimit <Int32>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-NetIPHttpsConfiguration [-AsJob] [-CimSession <CimSession[]>] [-GPOSession <String>] [-Profile <String[]>]
 [-ProfileActivated <Boolean[]>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NetIPHttpsConfiguration** cmdlet gets the IP-HTTPS configuration from a computer or a Group Policy Object (GPO).

You can also use **Get-NetIPHttpsConfiguration** to retrieve the IP-HTTPS configuration, and then use the configuration information as input into other cmdlets.

## EXAMPLES

### Example 1: Get the IP-HTTPS configuration
```
PS C:\>Get-NetIPHttpsConfiguration
```

This command gets the IP-HTTPS configuration from a computer or a GPO.

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
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GPOSession
Specifies the Group Policy session from which to get the configuration information. 

You can use this parameter with the **NetGPO** cmdlets to aggregate multiple operations performed on a GPO. 

You cannot use this parameter with the **PolicyStore** parameter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicyStore
Specifies the policy store from which to get the configuration.
The default store is ActiveStore. 

Valid values for this parameter are: 

 -- ActiveStore 

 -- PersistentStore 

 -- GPO 

To get the configuration of a GPO, specify the GPO name using the following format: `Domain\GPOName`

You cannot use this parameter with the **GPOSession** parameter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: ActiveStore
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Filters the objects retrieved by the profile name.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: IPHttpsProfile

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProfileActivated
Filters the objects retrieved by profile status.

```yaml
Type: Boolean[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

## INPUTS

### None
This cmdlet accepts no input objects.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIpHTTPsConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

This cmdlet returns one or more IP-HTTPS configuration objects.

## NOTES

## RELATED LINKS

[New-NetIPHttpsConfiguration](./New-NetIPHttpsConfiguration.md)

[Remove-NetIPHttpsConfiguration](./Remove-NetIPHttpsConfiguration.md)

[Rename-NetIPHttpsConfiguration](./Rename-NetIPHttpsConfiguration.md)

[Reset-NetIPHttpsConfiguration](./Reset-NetIPHttpsConfiguration.md)

[Set-NetIPHttpsConfiguration](./Set-NetIPHttpsConfiguration.md)

