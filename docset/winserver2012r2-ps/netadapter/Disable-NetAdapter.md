---
external help file: MSFT_NetAdapter.cmdletDefinition.cdxml-help.xml
Module Name: NetAdapter
ms.date: 10/29/2017
online version: https://learn.microsoft.com/powershell/module/netadapter/disable-netadapter?view=windowsserver2012r2-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Disable-NetAdapter
---

# Disable-NetAdapter

## SYNOPSIS
Disables a network adapter.

## SYNTAX

### ByName (Default)
```
Disable-NetAdapter [-Name] <String[]> [-IncludeHidden] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByInstanceID
```
Disable-NetAdapter -InterfaceDescription <String[]> [-IncludeHidden] [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject (cdxml)
```
Disable-NetAdapter -InputObject <CimInstance[]> [-PassThru] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Disable-NetAdapter** cmdlet disables a network adapter.
A network adapter must be enabled to connect to a network.
This cmdlet causes loss of network connectivity of the specified network adapter.
Note: Do not disable the network adapter being used to manage a remote computer.
By default the user will be prompted to confirm the network adapter should be disabled

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Disable-NetAdapter -Name "Ethernet 2"


A version of the cmdlet that uses position.
PS C:\>Disable-NetAdapter "Ethernet 2"


A version of the cmdlet that uses position and wildcard characters.
PS C:\>Disable-NetAdapter E*2
```

This example disables a network adapter named Ethernet Connection 2.

### EXAMPLE 2
```
PS C:\>Disable-NetAdapter -Name VMGuestTrafficAdapter -CimSession HyperVServer4
```

This example disables the network adapter named VMGuestTrafficAdapter on the remote computer named HyperVServer4.

### EXAMPLE 3
```
PS C:\>Disable-NetAdapter -Name *
```

This example disables all network adapters.
Note: If remotely managing a computer, then all network connectivity will be lost and cannot be remotely restored.

### EXAMPLE 4
```
PS C:\>Disable-NetAdapter -Name MyAdapter
Confirm 
Are you sure you want to perform this action? 
Disable-NetAdapter ꞌMyAdapter' 


[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"):Y


A version of the cmdlet that overrides the default confirmation prompt when disabling the network adapter named MyAdapter. For more information about changing the default confirmation prompt, see the [CODE_Snippit]$ConfirmPreference[CODE_Snippit] variable by running the [CODE_Snippit]Get-Help -Name about_Preference_Variables[CODE_Snippit] cmdlet.
PS C:\>Disable-NetAdapter -Name MyAdapter -Confirm:$false
```

This example disables the network adapter named MyAdapter.

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

### -IncludeHidden
Specifies both visible and hidden network adapters should be included.
By default only visible network adapters are included.
If a wildcard character is used in identifying a network adapter and this parameter has been specified, then the wildcard string is matched against both hidden and visible network adapters.

```yaml
Type: SwitchParameter
Parameter Sets: ByName, ByInstanceID
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Specifies the input to this cmdlet.
You can use this parameter, or you can pipe the input to this cmdlet.

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

### -InterfaceDescription
Specifies the network adapter interface description.
For a physical network adapter this is typically the name of the vendor of the network adapter followed by a part number and description, such as `Contoso 12345 Gigabit Network Device`.

```yaml
Type: String[]
Parameter Sets: ByInstanceID
Aliases: ifDesc

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Specifies the name of the network adapter.

```yaml
Type: String[]
Parameter Sets: ByName
Aliases: ifAlias, InterfaceAlias

Required: True
Position: 0
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapter[]
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetAdapter
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## NOTES

## RELATED LINKS

[Enable-NetAdapter](./Enable-NetAdapter.md)

