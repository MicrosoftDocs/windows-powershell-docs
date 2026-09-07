---
document type: cmdlet
external help file: OSLicense-Help.xml
HelpUri: ''
Locale: en-US
Module Name: OSLicense
ms.date: 09/07/2026
PlatyPS schema version: 2024-05-01
title: Set-SubscriptionLicenseInfo
---

# Set-SubscriptionLicenseInfo

## SYNOPSIS
Sets subscription license configuration.

## SYNTAX

### __AllParameterSets

```
Set-SubscriptionLicenseInfo [-Enabled] <Boolean> [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `Set-SubscriptionLicenseInfo` cmdlet enables or disables Windows subscription licensing.
Set **Enabled** to `$true` to enable subscription licensing or `$false` to disable it.

This cmdlet is available on systems that include the OSLicense module. The applicable Windows
update KB number is pending confirmation.

## EXAMPLES

### Example 1: Enable subscription licensing

This command requests that Windows enable subscription licensing.

> [!CAUTION]
> This operation changes the system's subscription licensing configuration. Confirm the intended
> state before you run the command.

```powershell
Set-SubscriptionLicenseInfo -Enabled $true
```

### Example 2: Disable subscription licensing

This command requests that Windows disable subscription licensing.

> [!CAUTION]
> This operation changes the system's subscription licensing configuration. Confirm the intended
> state before you run the command.

```powershell
Set-SubscriptionLicenseInfo -Enabled $false
```

## PARAMETERS

### -AsJob

Runs the command as a background job. This parameter is added by the implicit-remoting wrapper and
isn't declared by the underlying `Set-SubscriptionLicenseInfo` function.

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

### -Enabled

Specifies whether to enable or disable Windows subscription licensing. Set this parameter to `$true`
to enable subscription licensing or `$false` to disable it.

```yaml
Type: System.Boolean
DefaultValue: False
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: (All)
  Position: 0
  IsRequired: true
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

When the operation succeeds, the cmdlet returns an object whose **Success** property is `$true`.
The **Operation** property is `EnableSubscription` or `DisableSubscription`, depending on the value
of **Enabled**.

If an exception occurs, the cmdlet returns `$null` and doesn't write an error record.

### System.Management.Automation.Job

When you use **AsJob** through an implicit-remoting wrapper, the cmdlet returns a job object. Use
`Receive-Job` to retrieve the operation result after the job completes.

## NOTES

Run this cmdlet from an elevated PowerShell session because it changes system licensing
configuration.

The cmdlet reads the subscription type from the `SoftwareLicensingService` CIM instance. The current
implementation supports subscription type `0`. It invokes `ClipRenew.exe` with either the
`enablesubscription` or `disablesubscription` operation and suppresses the native command's output.
An unsupported subscription type, a CIM error, a missing tool, or a nonzero native exit code causes
the cmdlet to return `$null`.

The source function doesn't define **AsJob**. This parameter is retained because the
implicit-remoting wrapper adds it to the command surface.

## RELATED LINKS

- [Windows subscription activation](/windows/deployment/windows-subscription-activation)
- [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs)
