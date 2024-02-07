---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: PS_DAEntryPointDC_v1.0.0.cdxml-help.xml
Module Name: RemoteAccess
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/remoteaccess/set-daentrypointdc?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-DAEntryPointDC
---

# Set-DAEntryPointDC

## SYNOPSIS
Modifies domain controller (DC) settings for the entry point.

## SYNTAX

### ChangeByDCName (Default)
```
Set-DAEntryPointDC [-ComputerName <String>] [-NewDC <String>] [-Force] [-PassThru] -ExistingDC <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ChangeByEntryPoint
```
Set-DAEntryPointDC [-ComputerName <String>] [-NewDC <String>] [-Force] [-PassThru] -EntryPointName <String>
 [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
The **Set-DAEntryPointDC** cmdlet modifies domain controller (DC) settings for entry points, and can be used to the following:

 -- Assigns a DC to all entry points previously assigned to the DC specified in the **ExistingDC** parameter.
This is useful when a DC is no longer reachable and entry points settings must be updated.

 -- Assigns a DC to a specific entry point.
This is useful for optimization, such as improving the Group Policy propagation time by specifying a DC that is located within the same Active Directory site as the other servers in an entry point.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>Set-DAEntryPointDC -EntryPointName "Entry Point 1" -NewDC "DC3.Domain1.corp.company.com" -Force -PassThru
EntryPointName       : Entry Point 1
DomainControllerName : dc3.domain1.corp.contoso.com
```

This example associates Entry Point 1 with the DC named dc3.domain1.corp.contoso.com.

### EXAMPLE 2
```
PS C:\>Set-DAEntryPointDC -EntryPointName "Entry Point 1" -ComputerName "da1.domain1.corp.contoso.com" -Force -PassThru
EntryPointName       : Entry Point 1
DomainControllerName : dc3.domain1.corp.contoso.com
```

This example automatically picks the DC named dc3.domain1.corp.contoso.com is the closest to the server named da1.domain1.corp.contoso.com and associate the DC with Entry Point 1, because the **NewDC** parameter is not specified.

### EXAMPLE 3
```
PS C:\>Set-DAEntryPointDC -ExistingDC "dc1.domain1.corp.contoso.com" -NewDC "dc3.domain1.corp.contoso.com" -Force -PassThru
EntryPointName       : Entry Point 1
DomainControllerName : dc3.domain1.corp.contoso.com
```

This example associates all of the entry points which were previously associated with the DC named dc1.domain1.corp.contoso.com with the DC named dc3.domain1.corp.contoso.com.

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

### -ComputerName
Specifies theIPv4 or IPv6 address, or host name, of a server included in the entry point.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Cn

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

### -EntryPointName
Specifies the name of the entry point for which the DC is be updated.

```yaml
Type: String
Parameter Sets: ChangeByEntryPoint
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ExistingDC
Specifies the fully qualified domain name (FQDN) of the existing DC that will be updated.

```yaml
Type: String
Parameter Sets: ChangeByDCName
Aliases: DomainControllerName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Force
Forces the command to run without asking for user confirmation.

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

### -NewDC
Specifies the FQDN of the new DC.

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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance[]

### Microsoft.Management.Infrastructure.CimInstance#DADomainController

The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

The array of DADomainController objects that contains the following properties:

 -- ChangeByDCName: Provides a list of entry points for which the associated DCs have been changed, and the name of the new DC.
The **ExistingDC** parameter has a specified value.
The **EntryPointName** parameter does not have a specified value.

 -- ChangeByEntryPoint: Provides information about the specified entry point and its updated DC.
The **ExistingDC** parameter does not have a specified value.
The **EntryPointName** parameter has a specified value.

## NOTES

## RELATED LINKS

[Add-DAEntryPoint](./Add-DAEntryPoint.md)

[Get-DAEntryPoint](./Get-DAEntryPoint.md)

[Get-DAEntryPointDC](./Get-DAEntryPointDC.md)

[Remove-DAEntryPoint](./Remove-DAEntryPoint.md)

[Set-DAEntryPoint](./Set-DAEntryPoint.md)

