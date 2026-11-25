---
document type: cmdlet
external help file: OSLicense-Help.xml
HelpUri: https://learn.microsoft.com/powershell/module/oslicense/invoke-subscriptionlicense?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
Locale: en-US
Module Name: OSLicense
ms.date: 09/10/2026
PlatyPS schema version: 2024-05-01
title: Invoke-SubscriptionLicense
---

# Invoke-SubscriptionLicense

## SYNOPSIS
Invokes a Windows subscription licensing operation.

## SYNTAX

### Remove

```
Invoke-SubscriptionLicense [-Remove] [-AsJob] [<CommonParameters>]
```

### Refresh

```
Invoke-SubscriptionLicense [-Refresh] [-AsJob] [<CommonParameters>]
```

### Acquire

```
Invoke-SubscriptionLicense [-Acquire] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

`Invoke-SubscriptionLicense` invokes a Windows subscription licensing operation on the local
computer. Select **Remove**, **Refresh**, or **Acquire**. The function reads the
**SubscriptionType** property from the **SoftwareLicensingService** CIM class and uses the matching
entry in its internal tool map.

For subscription type `0`, the source maps **Remove** to `removesubscription` and **Refresh** to
`refreshsubscription`. It maps **Acquire** to `$null`. Every helper call includes `noshow`, so the
current **Acquire** path starts `%SystemRoot%\System32\ClipRenew.exe` with only `noshow`. The source
doesn't establish an acquisition command for this configuration.

The cmdlet discards native tool output and catches all errors. It returns a success object only
if the native tool exits with code `0`. It returns no object if you don't select an operation or
if configuration lookup, tool startup, or the requested operation fails.

> [!NOTE]
> `Invoke-SubscriptionLicense` is available in [Windows Server vNext Preview Build 29651](https://techcommunity.microsoft.com/discussions/windowsserverinsiders/announcing-windows-server-vnext-preview-build-29651/4549702)
> and the [2026-09 security update for Windows 11 (KB5124008)](https://support.microsoft.com/help/5124008).

## EXAMPLES

### Example 1: Request a subscription license refresh

This example requests a refresh and checks whether the cmdlet returns `$null` for a failure. Don't
treat the absence of an error record as proof of success.

```powershell
$result = Invoke-SubscriptionLicense -Refresh

if ($null -eq $result) {
    Write-Warning 'The refresh did not return a success result.'
    return
}

$result | Select-Object Success, Operation
```

For a non-null result, **Success** is `$true`, and **Operation** is `RefreshSubscription`.

### Example 2: Remove a subscription license

The following command removes the subscription license from the device.

> [!CAUTION]
> The function doesn't implement `SupportsShouldProcess`, so `-WhatIf` and `-Confirm` aren't
> available. Use **Remove** only after you assess the device's licensing requirements and have a
> recovery plan.

```powershell
Invoke-SubscriptionLicense -Remove
```

## PARAMETERS

### -Acquire

Selects the acquire operation. For subscription type `0`, the current tool map sets the acquire
command to `$null`. The helper therefore starts `ClipRenew.exe` with only the `noshow` argument.
The source doesn't establish that this invocation requests a new subscription license.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: False
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: Acquire
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -AsJob

Runs the command as a background job when you invoke it through an implicit-remoting wrapper. This
wrapper supplies this parameter, but the local `OSLicense` module function doesn't declare it.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: False
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

### -Refresh

Requests a subscription license refresh. For subscription type `0`, the cmdlet passes
`refreshsubscription noshow` to `ClipRenew.exe`.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: False
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: Refresh
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Remove

Removes the subscription license. For subscription type `0`, the cmdlet passes
`removesubscription noshow` to `ClipRenew.exe`.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: False
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: Remove
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

When the native tool exits with code `0`, the cmdlet returns an object with **Success** set to
`$true`. The **Operation** value is `RemoveSubscription`, `RefreshSubscription`, or
`AcquireSubscription`, based on the selected operation.

The cmdlet returns no object when no operation is selected, the subscription type isn't supported,
the native tool isn't present, the native tool exits with a nonzero code, or another caught error
occurs.

### System.Management.Automation.Job

When you use **AsJob** through an implicit-remoting wrapper, the cmdlet returns a job object. Use
`Receive-Job` to retrieve the operation result after the job completes.

## NOTES

Run this cmdlet from an elevated PowerShell session. The operations change subscription licensing
state on the target device.

The current source defines a tool mapping only for subscription type `0`. An unsupported
**SubscriptionType** value causes the configuration lookup to fail, and the cmdlet catches that
failure and returns no object.

The cmdlet discards the native tool's standard output and uses only the process exit code to decide
whether to return a success object. It doesn't return an error object or write an error record when
an operation fails.

The current **Acquire** mapping is `$null`. Until the implementation defines an acquisition
command, don't interpret an `AcquireSubscription` success object as evidence that the source
requested acquisition through a named `ClipRenew.exe` command.

## RELATED LINKS

- [Windows subscription activation](/windows/deployment/windows-subscription-activation)
- [SoftwareLicensingService class](/previous-versions/windows/desktop/sppwmi/softwarelicensingservice)
- [about_Remote_Jobs](/powershell/module/microsoft.powershell.core/about/about_remote_jobs)
