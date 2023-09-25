---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.ProcessMitigations.Commands.dll-Help.xml
Module Name: ProcessMitigations
ms.date: 03/29/2017
online version: https://learn.microsoft.com/powershell/module/processmitigations/set-processmitigation?view=windowsserver2022-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-ProcessMitigation
---

# Set-ProcessMitigation

## SYNOPSIS
Commands to enable and disable process mitigations or set them in bulk from an XML file.

## SYNTAX

### ProcessPolicy
```
Set-ProcessMitigation [[-Name] <String>] [-Disable <String[]>] [-Enable <String[]>] [-EAFModules <String[]>]
 [-Force <String>] [-Reset] [-Remove] [<CommonParameters>]
```

### FullPolicy
```
Set-ProcessMitigation -PolicyFilePath <String> [-IsValid] [<CommonParameters>]
```

### SystemMode
```
Set-ProcessMitigation [-Disable <String[]>] [-Enable <String[]>] [-EAFModules <String[]>] [-System]
 [-Force <String>] [-Reset] [-Remove] [<CommonParameters>]
```

## DESCRIPTION
Used to turn on and off various process mitigation settings.
Can also apply an XML file to apply settings for many processes at once.

## EXAMPLES

### Example 1
```
PS C:\>  Set-ProcessMitigation -Name Notepad.exe -Enable SEHOP -Disable ForceRelocateImages
```

Gets the current process mitigation for "notepad.exe" from the registry and then enables SEHOP, and disables ForceRelocateImages.

### Example 2
```
PS C:\> Set-ProcessMitigation -PolicyFilePath settings.xml
```

Applies all settings inside settings.xml

### Example 3
```
PS C:\> Set-ProcessMitigation -System -Enable DEP
```

Applies DEP at the system level. To disable mitigations, you can replace `-Enable` with `-Disable`. However, for app-level mitigations, this will force the mitigation to be disabled only for that app.

### Exmaple 4

```
PS C:\> Set-ProcessMitigation -System -Remove -Disable DEP
```

If you need to restore the mitigation back to the system default, you need to include the `-Remove` cmdlet as well, as in the above  example:

### Example 5

```
PS C:\> Set-ProcessMitigation -System -Enable SEHOP
```

Enable SEHOP Component at the system level.

### Example 6

```
PS C:\> Set-ProcessMitigation -System -Disable SEHOP
```

Disable SEHOP Component at the system level.

### Example 7

```
PS C:\> Set-ProcessMitigation -System -Reset
```

Reset Mitigation at the system level.

## PARAMETERS

### -Disable
Comma separated list of mitigations to disable.
Disable list takes priority over enable list.
If specified in both, it will be disabled.

```yaml
Type: String[]
Parameter Sets: ProcessPolicy, SystemMode
Aliases: d
Accepted values: DEP, EmulateAtlThunks, SEHOP, ForceRelocateImages, RequireInfo, BottomUp, HighEntropy, StrictHandle, DisableWin32kSystemCalls, AuditSystemCall, DisableExtensionPoints, BlockDynamicCode, AllowThreadsToOptOut, AuditDynamicCode, CFG, SuppressExports, StrictCFG, MicrosoftSignedOnly, AllowStoreSignedBinaries, AuditMicrosoftSigned, AuditStoreSigned, EnforceModuleDependencySigning, DisableNonSystemFonts, AuditFont, BlockRemoteImageLoads, BlockLowLabelImageLoads, PreferSystem32, AuditRemoteImageLoads, AuditLowLabelImageLoads, AuditPreferSystem32, EnableExportAddressFilter, AuditEnableExportAddressFilter, EnableExportAddressFilterPlus, AuditEnableExportAddressFilterPlus, EnableImportAddressFilter, AuditEnableImportAddressFilter, EnableRopStackPivot, AuditEnableRopStackPivot, EnableRopCallerCheck, AuditEnableRopCallerCheck, EnableRopSimExec, AuditEnableRopSimExec, SEHOP, AuditSEHOP, SEHOPTelemetry, TerminateOnError, DisallowChildProcessCreation, AuditChildProcess

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EAFModules
Modules to be added to the EAF+ mitigation.

```yaml
Type: String[]
Parameter Sets: ProcessPolicy, SystemMode
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enable
Comma separated list of mitigations to enable.
Disable list takes priority over enable list.
If specified in both, it will be disabled.

```yaml
Type: String[]
Parameter Sets: ProcessPolicy, SystemMode
Aliases: e
Accepted values: DEP, EmulateAtlThunks, SEHOP, ForceRelocateImages, RequireInfo, BottomUp, HighEntropy, StrictHandle, DisableWin32kSystemCalls, AuditSystemCall, DisableExtensionPoints, BlockDynamicCode, AllowThreadsToOptOut, AuditDynamicCode, CFG, SuppressExports, StrictCFG, MicrosoftSignedOnly, AllowStoreSignedBinaries, AuditMicrosoftSigned, AuditStoreSigned, EnforceModuleDependencySigning, DisableNonSystemFonts, AuditFont, BlockRemoteImageLoads, BlockLowLabelImageLoads, PreferSystem32, AuditRemoteImageLoads, AuditLowLabelImageLoads, AuditPreferSystem32, EnableExportAddressFilter, AuditEnableExportAddressFilter, EnableExportAddressFilterPlus, AuditEnableExportAddressFilterPlus, EnableImportAddressFilter, AuditEnableImportAddressFilter, EnableRopStackPivot, AuditEnableRopStackPivot, EnableRopCallerCheck, AuditEnableRopCallerCheck, EnableRopSimExec, AuditEnableRopSimExec, SEHOP, AuditSEHOP, SEHOPTelemetry, TerminateOnError, DisallowChildProcessCreation, AuditChildProcess

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Overrides a system setting either on or off depending on the level this is set at. Will force "on"/"off" all mitigations provided in the -Enable list

```yaml
Type: String
Parameter Sets: ProcessPolicy, SystemMode
Aliases: f
Accepted values: on, off, notset

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IsValid
Set to check the given XML file for validity. Requires local .xsd

```yaml
Type: SwitchParameter
Parameter Sets: FullPolicy
Aliases: v

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Name of the process to apply mitigation settings to.
Can be in the format "notepad" or "notepad.exe"

```yaml
Type: String
Parameter Sets: ProcessPolicy
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -PolicyFilePath
Path to XML file containing mitigation settings.

```yaml
Type: String
Parameter Sets: FullPolicy
Aliases: x

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Remove
Removes a mitigation entry from the registry.

```yaml
Type: SwitchParameter
Parameter Sets: ProcessPolicy, SystemMode
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Reset
Resets a specific mitigation entry to defer.

```yaml
Type: SwitchParameter
Parameter Sets: ProcessPolicy, SystemMode
Aliases: r

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -System
Used to configure system defaults rather than individual apps.

```yaml
Type: SwitchParameter
Parameter Sets: SystemMode
Aliases: s

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

### System.Object

## NOTES

## RELATED LINKS
