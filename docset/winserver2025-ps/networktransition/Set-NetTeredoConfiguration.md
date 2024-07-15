---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: MSFT_NetTeredoConfiguration.cdxml-help.xml
Module Name: NetworkTransition
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/networktransition/set-netteredoconfiguration?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-NetTeredoConfiguration
---

# Set-NetTeredoConfiguration

## SYNOPSIS
Modifies the Teredo configuration of a computer or a Group Policy object (GPO).

## SYNTAX

### ByName (Default)
```
Set-NetTeredoConfiguration [-IPInterface <CimInstance>] [-PolicyStore <String>] [-GPOSession <String>]
 [[-Type] <Type>] [[-ServerName] <String>] [[-RefreshIntervalSeconds] <UInt32>] [[-ClientPort] <UInt32>]
 [[-ServerVirtualIP] <String>] [[-DefaultQualified] <Boolean>] [[-ServerShunt] <Boolean>]
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject (cdxml)
```
Set-NetTeredoConfiguration -InputObject <CimInstance[]> [[-Type] <Type>] [[-ServerName] <String>]
 [[-RefreshIntervalSeconds] <UInt32>] [[-ClientPort] <UInt32>] [[-ServerVirtualIP] <String>]
 [[-DefaultQualified] <Boolean>] [[-ServerShunt] <Boolean>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-NetTeredoConfiguration** cmdlet modifies the Teredo configuration of either a computer or a Group Policy Object (GPO).

## EXAMPLES

### Example 1: Set the Teredo server name
```
PS C:\>Set-NetTeredoConfiguration -ServerName "Test"
```

This command sets the Teredo server name to Test on the local persistent store.

### Example 2: Set the Teredo state
```
PS C:\>Set-NetTeredoConfiguration -Type Enterpriseclient -PolicyStore "Domain\GPOname"
```

This command sets the Teredo state to enterpriseclient in a GPO named Domain\GPOname.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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
Enter a computer name or a session object, such as the output of a [New-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](https://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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

### -ClientPort
Specifies the UDP port of the client computer.
If this parameter is not specified, then the port is chosen by the operating system.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultQualified
Determines if this cmdlet qualifies Teredo by default.
The default value is False.
This parameter can only be specified on GPOs.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GPOSession
Specifies the Group Policy session to which to store the configuration information.

You can use this parameter with the **NetGPO** cmdlets to aggregate multiple operations performed on a GPO.

You cannot use this parameter with the *PolicyStore* parameter.

```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPInterface
Specifies the interface on which to set the Teredo configuration.
If the specified interface is not a Teredo interface, then the cmdlet does not return any configuration.

```yaml
Type: CimInstance
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InputObject
Specifies the input object that is used in a pipeline command.

```yaml
Type: CimInstance[]
Parameter Sets: InputObject (cdxml)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Specifies the policy store that contains the configuration to set.
The acceptable values for this parameter are:

- PersistentStore
- GPO

The default value is PersistentStore.

To set the configuration of a GPO, specify the GPO name using the following format: Domain\GPOName

You cannot use this parameter with the *GPOSession* parameter.

```yaml
Type: String
Parameter Sets: ByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RefreshIntervalSeconds
Specifies the client refresh interval in seconds.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: RefreshInterval

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerName
Specifies the name or IPv4 address of the Teredo server.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerShunt
Indicates that the tunnel miniport and IPv4 routing layer are bypassed for high throughput on the Teredo relay functionality of the Teredo server.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServerVirtualIP
Specifies the virtual IPv4 address of the server.
This parameter is not applicable if the computer is a Teredo client.
This parameter can only be specified on GPOs.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
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

### -Type
Specifies the state of Teredo.
The acceptable values for this parameter are:

- Disabled: Disables the Teredo service.
- Client.
Enables the Teredo client.
- Enterpriseclient.
Skips the managed network detection.
- Server.
Enables the Teredo server.
- Relay.
- Automatic.
- Default.
The default state is client.

```yaml
Type: Type
Parameter Sets: (All)
Aliases:
Accepted values: Default, Relay, Client, Server, Disabled, Automatic, Enterpriseclient, Natawareclient

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs.
The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None
This cmdlet accepts no input objects.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\MSFT_NetTeredoConfiguration
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

When the *Passthru* parameter is specified, this cmdlet outputs a modified Teredo configuration object.

## NOTES

## RELATED LINKS

[Get-NetTeredoConfiguration](./Get-NetTeredoConfiguration.md)

[Reset-NetTeredoConfiguration](./Reset-NetTeredoConfiguration.md)

