---
document type: cmdlet
external help file: OSLicense-Help.xml
HelpUri: https://learn.microsoft.com/powershell/module/oslicense/invoke-kmslicense?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
Locale: en-US
Module Name: OSLicense
ms.date: 09/10/2026
PlatyPS schema version: 2024-05-01
title: Invoke-KmsLicense
---

# Invoke-KmsLicense

## SYNOPSIS
Clears selected Key Management Service (KMS) configuration overrides.

## SYNTAX

### ClearServer

```
Invoke-KmsLicense [-ClearServer] [-AsJob] [<CommonParameters>]
```

### ClearPort

```
Invoke-KmsLicense [-ClearPort] [-AsJob] [<CommonParameters>]
```

### ClearDomain

```
Invoke-KmsLicense [-ClearDomain] [-AsJob] [<CommonParameters>]
```

### ClearListeningPort

```
Invoke-KmsLicense [-ClearListeningPort] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `Invoke-KmsLicense` cmdlet clears a manually configured KMS client or KMS host setting from the
local software licensing service. It can clear the KMS client host name, client port, DNS lookup
domain, or KMS host listening port. Each clearing operation uses a separate parameter set, so
select only one operation per invocation.

The cmdlet returns a structured result object for successful operations and CIM errors. It doesn't
write operation status or error details to the console. For output details, see the OUTPUTS and
NOTES sections.

> [!NOTE]
> `Invoke-KmsLicense` is available in [Windows Server vNext Preview Build 29651](https://techcommunity.microsoft.com/discussions/windowsserverinsiders/announcing-windows-server-vnext-preview-build-29651/4549702)
> and the [2026-09 security update for Windows 11 (KB5124008)](https://support.microsoft.com/help/5124008).

## EXAMPLES

### Example 1: Clear KMS client host and port overrides

This example reviews the configured KMS client host and port, and then clears each override with a
separate command. The `kms.example.com` host name in the sample output is fictitious. Verify the
current settings before you clear them because the command doesn't prompt for confirmation.

```powershell
Get-KmsLicenseInfo |
  Select-Object KeyManagementServiceMachine, KeyManagementServicePort
```

```Output
KeyManagementServiceMachine KeyManagementServicePort
--------------------------- ------------------------
kms.example.com                                 1688
```

```powershell
$serverResult = Invoke-KmsLicense -ClearServer
$portResult = Invoke-KmsLicense -ClearPort
$serverResult
$portResult
```

```Output
Success Operation
------- ---------
   True ClearServer
   True ClearPort
```

Clearing the server and port overrides doesn't clear a configured KMS lookup domain.

### Example 2: Clear a KMS host listening-port override and inspect the result

This example clears the configured listening-port override on a KMS host and reports whether the
operation succeeds. Before you run the command, confirm that clearing the override won't disrupt
KMS client connectivity.

```powershell
$result = Invoke-KmsLicense -ClearListeningPort

if ($result.Success) {
  "Cleared operation: $($result.Operation)"
} else {
  "Clear failed: $($result.ErrorCode) $($result.ErrorMessage)"
}
```

On success, **Operation** is `ClearListeningPort`. On failure, **ErrorCode** contains a Windows
HRESULT if the CIM exception provides one, and **ErrorMessage** contains the Windows error text
or the exception message.

## PARAMETERS

### -AsJob

Runs the command as a background job when you invoke it through an implicit-remoting wrapper. This
parameter comes from the wrapper, but the local `OSLicense` module function doesn't declare it.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ClearDomain

Clears the KMS client DNS lookup domain override by calling the
`ClearKeyManagementServiceLookupDomain` method of the local software licensing service. This
operation doesn't clear the configured KMS client host name or port.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ClearDomain
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ClearListeningPort

Clears the KMS host listening-port override by calling the
`ClearKeyManagementServiceListeningPort` method of the local software licensing service. This
operation doesn't disable the KMS host or clear KMS client connection settings.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ClearListeningPort
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ClearPort

Clears the manually configured KMS client port override by calling the
`ClearKeyManagementServicePort` method of the local software licensing service. This operation
doesn't clear the configured KMS client host name or DNS lookup domain.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ClearPort
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ClearServer

Clears the manually configured KMS client host name by calling the
`ClearKeyManagementServiceMachine` method of the local software licensing service. This operation
doesn't clear the configured KMS client port or DNS lookup domain.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ClearServer
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

## INPUTS

### None

This cmdlet doesn't accept pipeline input.

## OUTPUTS

### System.Management.Automation.PSCustomObject

When you run the cmdlet synchronously, it attempts a clearing operation and returns a result
object. In a successful result, **Success** is `$true`, and **Operation** is `ClearServer`, `ClearPort`,
`ClearDomain`, or `ClearListeningPort`.

If a CIM operation fails, **Success** is `$false`, **ErrorCode** contains the Windows HRESULT when
available, and **ErrorMessage** contains the Windows error text or exception message. Failure
results don't contain an **Operation** property.

### System.Management.Automation.Job

When you use **AsJob** through an implicit-remoting wrapper, the cmdlet returns a job object. Use
`Receive-Job` to retrieve the result object from the completed job.

## NOTES

Run this cmdlet in an elevated PowerShell session to change machine-wide licensing settings. The
cmdlet doesn't support **WhatIf** or **Confirm**, and it doesn't prompt before clearing a setting.
Use `Get-KmsLicenseInfo` to review the current KMS configuration before you make a change.

The clearing switches are mutually exclusive. If you invoke the underlying function without a
clearing switch, it returns no object and makes no change. The function also returns no object and
doesn't raise a CIM error if the local **SoftwareLicensingService** CIM instance isn't available. For
other CIM failures, the function returns the structured failure object that the OUTPUTS section
describes instead of writing to the error stream or throwing a terminating error to the caller.

The **AsJob** parameter is an implicit-remoting wrapper feature. The underlying local
`Invoke-KmsLicense` function doesn't declare that parameter.
The remote job can return deserialized representations of the result objects.

## RELATED LINKS

- [Slmgr.vbs options for obtaining volume activation information](/windows-server/get-started/activation-slmgr-vbs-options)
- [Activate using Key Management Service](/windows/deployment/volume-activation/activate-using-key-management-service-vamt)
- [Monitor activation](/windows/deployment/volume-activation/monitor-activation-client)
- [SoftwareLicensingService class](/previous-versions/windows/desktop/sppwmi/softwarelicensingservice)
