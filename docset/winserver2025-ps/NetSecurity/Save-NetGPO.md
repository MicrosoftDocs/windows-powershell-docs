---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: NetGPO.cmdletDefinition.cdxml-help.xml
Module Name: NetSecurity
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/netsecurity/save-netgpo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Save-NetGPO
---

# Save-NetGPO

## SYNOPSIS
Applies the modified cached local Group Policy Object (GPO) to the actual GPO.

## SYNTAX

```
Save-NetGPO [-GPOSession] <String> [-CimSession <CimSession[]>] [-ThrottleLimit <Int32>] [-AsJob]
 [<CommonParameters>]
```

## DESCRIPTION
The **Save-NetGPO** cmdlet saves the changes made to the local cached group policy object.
The cached Group Policy Object (GPO) copy is created with the Open-NetGPO cmdlet.

Individual operations on group policy objects require a round-trip to load the policy store.
When the policy store is a GPO on a busy domain controller, an administrator will want to open the GPO, do the work on it, and then save it back, with an in-memory copy.

Modifications are performed through the use of the *GPOSession* parameter.

This cmdlet does not batch individual changes, it loads and saves the entire GPO at once.
If any other changes were made by another administrator, or in a different Windows PowerShell® session, saving the GPO would overwrite those changes.

## EXAMPLES

### EXAMPLE 1
```
PS C:\>$gpoSession = Open-NetGPO -PolicyStore castle.contoso.com\Win8ClientFirewallPolicy



PS C:\>Remove-NetFirewallRule -Name BlockIMAccess -GPOSession $gpoSession



PS C:\>New-NetFirewallRule -Name LimitIMAccess -DisplayName "Contoso Messenger" -Program "%ProgramFiles(X86)%\Contoso Messenger\cmsg.exe" -Action Block -GPOSession $gpoSession



PS C:\>Save-NetGPO -GPOSession $gpoSession
```

This example replaces one rule in a domain GPO with another using a cached copy of the GPO.

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

### -GPOSession
Specifies the GPO session to be saved.
This parameter is used in the same way as the *PolicyStore* parameter.
When modifying GPOs in Windows PowerShell®, each change to a GPO requires the entire GPO to be loaded, modified, and saved back.
On a busy Domain Controller (DC), this can be a slow and resource-heavy operation.
A GPO session loads a domain GPO onto the local computer and makes all changes in a batch, before saving it back.
This reduces the load on the DC and speeds up the Windows PowerShell cmdlets.
To load a GPO Session, use the Open-NetGPO cmdlet.
To save a GPO Session, use this cmdlet.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
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

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Management.Infrastructure.CimInstance#root\StandardCimv2\GPOSession
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.

## OUTPUTS

### None

## NOTES

## RELATED LINKS

[New-NetFirewallRule](./New-NetFirewallRule.md)

[Open-NetGPO](./Open-NetGPO.md)

[Remove-NetFirewallRule](./Remove-NetFirewallRule.md)

