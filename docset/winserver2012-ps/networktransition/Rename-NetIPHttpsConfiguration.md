---
external help file: NetTransition_Cmdlets.xml
Module Name: NetworkTransition
online version: https://docs.microsoft.com/powershell/module/networktransition/rename-netiphttpsconfiguration?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Rename-NetIPHttpsConfiguration

## SYNOPSIS
Renames an IP-HTTPS profile.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Rename-NetIPHttpsConfiguration [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-PolicyStore <String>]
 [-Profile <String[]>] [-ProfileActivated <Boolean[]>] [-ThrottleLimit <Int32>] -NewName <String> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_2
```
Rename-NetIPHttpsConfiguration [-AsJob] [-CimSession <CimSession[]>] [-GPOSession <String>] [-PassThru]
 [-Profile <String[]>] [-ProfileActivated <Boolean[]>] [-ThrottleLimit <Int32>] -NewName <String> [-Confirm]
 [-WhatIf]
```

### UNNAMED_PARAMETER_SET_3
```
Rename-NetIPHttpsConfiguration [-AsJob] [-CimSession <CimSession[]>] [-PassThru] [-ThrottleLimit <Int32>]
 -InputObject <CimInstance[]> -NewName <String> [-Confirm] [-WhatIf]
```

## DESCRIPTION
The **Rename-NetIPHttpsConfiguration** cmdlet renames an IP-HTTPS profile, either on a computer or in a Group Policy Object (GPO).

## EXAMPLES

### Example 1: Rename an IP-HTTPS profile using a configuration object
```
PS C:\>$config = Get-NetIPHttpsConfiguration -PolicyStore "testdomain\GPOName"



PS C:\>Rename-NetIPHttpsConfiguration -InputObject $config
```

This set of commands uses the Get-NetIPHttpsConfiguration cmdlet to get an IP-HTTPS configuration object and stores it in a variable named $config.
The contents of the variable are then passed to this cmdlet.

### Example 2: Rename an IP-HTTPS profile
```
PS C:\>Rename-NetIPHttpsConfiguration -Profile Redmond -NewName Fareast
```

This command renames the IP-HTTPS profile named **Redmond** to **Fareast**.

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
Specifies the Group Policy session which contains the IP-HTTPS configuration to rename. 

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

### -InputObject
Specifies the object which contains an IP-HTTPS profile to rename.

```yaml
Type: CimInstance[]
Parameter Sets: UNNAMED_PARAMETER_SET_3
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -NewName
Specifies the new name for the IP-HTTPS profile.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
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

### -PolicyStore
Specifies the policy store that contains the configuration profile to rename. 
The acceptable values for this parameter are:

 -- GPO 

To rename the configuration profile of a GPO, specify the GPO name using the following format: `Domain\GPOName`

You cannot use this parameter with the **GPOSession** parameter.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profile
Specifies the name of the profile to rename.

```yaml
Type: String[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
Aliases: IPHttpsProfile

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProfileActivated
Specifies which profile to rename.

```yaml
Type: Boolean[]
Parameter Sets: UNNAMED_PARAMETER_SET_1, UNNAMED_PARAMETER_SET_2
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
This cmdlet accepts no input objects.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetIPHttpsConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

When the **Passthru** parameter is specified, this cmdlet outputs a modified Windows Management Instrumentation (WMI) object.

## NOTES

## RELATED LINKS

[Get-NetIPHttpsConfiguration](./Get-NetIPHttpsConfiguration.md)

[New-NetIPHttpsConfiguration](./New-NetIPHttpsConfiguration.md)

[Remove-NetIPHttpsConfiguration](./Remove-NetIPHttpsConfiguration.md)

[Reset-NetIPHttpsConfiguration](./Reset-NetIPHttpsConfiguration.md)

[Set-NetIPHttpsConfiguration](./Set-NetIPHttpsConfiguration.md)

