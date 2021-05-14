---
external help file: NetTransition_Cmdlets.xml
Module Name: NetworkTransition
online version: https://docs.microsoft.com/powershell/module/networktransition/get-netteredoconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-NetTeredoConfiguration

## SYNOPSIS
Gets the Teredo configuration of a computer or a Group Policy Object (GPO).

## SYNTAX

```
Get-NetTeredoConfiguration [-AsJob] [-CimSession <CimSession[]>] [-GPOSession <String>]
 [-IPInterface <CimInstance>] [-PolicyStore <String>] [-ThrottleLimit <Int32>]
```

## DESCRIPTION
The **Get-NetTeredoConfiguration** cmdlet gets the Teredo configuration of a computer or a Group Policy Object (GPO).

## EXAMPLES

### Example 1: Get the Teredo configuration of a computer
```
PS C:\>Get-NetTeredoConfiguration
```

This command gets the Teredo configuration from the active store on the local computer.

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
Specifies the Group Policy session from which to get the Teredo configuration information. 

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
Specifies the interface for which to get the Teredo configuration.
If the interface is not a Teredo interface, then the cmdlet does not return any Teredo configuration information.

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

 -- PersistentStore 

 -- ActiveStore 

 -- GPO 

The default value is ActiveStore. 

To retrieve the configuration from a GPO, specify the GPO name using the following format: `Domain\GPOName`

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

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetTeredoConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

This cmdlet returns a Teredo configuration object.

## NOTES

## RELATED LINKS

[Reset-NetTeredoConfiguration](./Reset-NetTeredoConfiguration.md)

[Set-NetTeredoConfiguration](./Set-NetTeredoConfiguration.md)

