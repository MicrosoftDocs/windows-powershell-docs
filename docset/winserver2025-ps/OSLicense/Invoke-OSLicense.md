---
document type: cmdlet
external help file: OSLicense-Help.xml
HelpUri: https://learn.microsoft.com/powershell/module/oslicense/invoke-oslicense?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
Locale: en-US
Module Name: OSLicense
ms.date: 09/10/2026
PlatyPS schema version: 2024-05-01
title: Invoke-OSLicense
---

# Invoke-OSLicense

## SYNOPSIS
Performs a selected Windows operating system licensing operation.

## SYNTAX

### None

```
Invoke-OSLicense [-AsJob] [<CommonParameters>]
```

### ClearKey

```
Invoke-OSLicense [-ClearProductKeyFromRegistry] [-AsJob] [<CommonParameters>]
```

### InstallKey

```
Invoke-OSLicense [-InstallProductKey <String>] [-AsJob] [<CommonParameters>]
```

### InstallLicense

```
Invoke-OSLicense [-InstallLicenseFile <String>] [-AsJob] [<CommonParameters>]
```

### ReinstallLicenses

```
Invoke-OSLicense [-ReinstallSystemLicenses] [-AsJob] [<CommonParameters>]
```

### Rearm

```
Invoke-OSLicense [-Rearm] [-RearmID <String>] [-AsJob] [<CommonParameters>]
```

### UninstallKey

```
Invoke-OSLicense [-UninstallProductKey] [-ActivationID <String>] [-AsJob]
 [<CommonParameters>]
```

### ActivateOnline

```
Invoke-OSLicense [-ActivateOnline] [-ActivationID <String>] [-AsJob]
 [<CommonParameters>]
```

### ActivateOffline

```
Invoke-OSLicense [-ActivateOffline <String>] [-ConfirmationID <String>] [-AsJob]
 [<CommonParameters>]
```

### ActivateToken

```
Invoke-OSLicense [-TokenCertThumbprint <String>] [-TokenPIN <String>] [-AsJob]
 [<CommonParameters>]
```

### RemoveToken

```
Invoke-OSLicense [-ILID <String>] [-ILvID <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

`Invoke-OSLicense` performs one state-changing Windows licensing operation on the local computer.
The operation parameter that you provide selects a parameter set and the corresponding licensing
operation. For example, **InstallProductKey** selects product-key installation, and
**ReinstallSystemLicenses** selects system-license reinstallation. If you don't provide an operation
parameter, the command returns no output and doesn't perform an operation.

For online activation and product-key removal, provide **ActivationID** to target a specific
licensing product. If you omit **ActivationID**, the command selects the first primary Windows
product that has a partial product key and isn't an add-on product. For rearm operations, omit
**RearmID** to rearm Windows. Provide **RearmID** to target a licensing SKU by activation ID or an
application by application ID.

Offline activation requires **ConfirmationID**. To use an activation ID or offline installation ID,
provide **ActivateOffline**. If you provide only **ConfirmationID**, the command
selects the first primary Windows product that has a partial product key and an offline
installation ID. Token activation requires **TokenCertThumbprint**. **TokenPIN** is optional.
Token-license removal requires both **ILID** and **ILvID**.

Direct operations return structured objects instead of status text. Successful results contain
**Success**, **Operation**, and operation-specific properties. Caught failures return **Success**
as `$false`, **Operation**, **ErrorCode**, and **ErrorMessage**. When available, **ErrorCode**
contains the Windows HRESULT reported by the CIM operation. An online or offline activation
failure after product resolution also includes **ActivationID** and **ProductName**.

> [!NOTE]
> `Invoke-OSLicense` is available in [Windows Server vNext Preview Build 29651](https://techcommunity.microsoft.com/discussions/windowsserverinsiders/announcing-windows-server-vnext-preview-build-29651/4549702)
> and the [2026-09 security update for Windows 11 (KB5124008)](https://support.microsoft.com/help/5124008).

## EXAMPLES

### Example 1: Install a product key and inspect the result

Caution: This example changes the product key on the local computer. It uses a fictitious key that
you must replace with an authorized key. Run state-changing licensing operations only from an
elevated PowerShell session and validate the command in a nonproduction environment first.

```powershell
$result = Invoke-OSLicense -InstallProductKey 'AAAAA-BBBBB-CCCCC-DDDDD-EEEEE'
$result | Select-Object Success, Operation, ErrorCode, ErrorMessage
```

The first command requests product-key installation. The second command displays the common result
properties. The example doesn't indicate that the fictitious key is valid or that activation
succeeds.

### Example 2: Activate a specific product online and inspect the result

Caution: Online activation contacts the activation service and can change licensing state. The
activation ID in this example is fictitious. Replace it with the intended product's activation ID
only after you verify the target.

```powershell
$activationParameters = @{
  ActivateOnline = $true
  ActivationID   = '00000000-0000-0000-0000-000000000000'
}
$result = Invoke-OSLicense @activationParameters
$result |
  Select-Object Success, Operation, ActivationID, ProductName, ErrorCode, ErrorMessage
```

The first command requests online activation for a specific product. The second command displays
the success and error properties. The example doesn't indicate that the fictitious activation ID
resolves or that the operation succeeds.

## PARAMETERS

### -ActivateOffline

Specifies the activation ID or offline installation ID of the product to activate offline. If you
omit this parameter and provide **ConfirmationID**, the command selects the first primary Windows
product that has a partial product key and an offline installation ID.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ActivateOffline
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ActivateOnline

Selects online activation. Use **ActivationID** to target a specific licensing product. If you omit
**ActivationID**, the command selects the first primary Windows product that has a partial product
key and isn't an add-on product.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ActivateOnline
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ActivationID

Specifies the activation ID of a licensing product for online activation or product-key removal.
If you omit this parameter, the command selects the first primary Windows product that has a partial
product key and isn't an add-on product.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ActivateOnline
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
- Name: UninstallKey
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

Runs the command as a background job when you invoke the module through an implicit-remoting
wrapper. The target `Invoke-OSLicense` function doesn't declare this parameter; the generated
implicit-remoting wrapper adds it. Use `Receive-Job` to retrieve the operation result.

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

### -ClearProductKeyFromRegistry

Selects the operation that removes the product key from the registry. This operation doesn't
uninstall the product key from the licensing product.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ClearKey
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ConfirmationID

Specifies the confirmation ID to deposit for offline activation. A successful offline activation
operation requires this parameter. If you omit **ActivateOffline**, the command attempts to select
the first primary Windows product that has a partial product key and an offline installation ID.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ActivateOffline
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ILID

Specifies the installation license ID of the token-based license to remove. Provide **ILvID** with
this parameter. If either value is missing, the command doesn't perform the removal operation.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: RemoveToken
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ILvID

Specifies the version ID of the token-based license to remove. Provide **ILID** with this parameter.
If either value is missing, the command doesn't perform the removal operation.

```yaml
Type: System.Int32
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: RemoveToken
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -InstallLicenseFile

Specifies the path of an `.xrm-ms` license file to install. The command reads the complete file and
passes its contents to the licensing service. An invalid or inaccessible path produces a structured
failure result.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: InstallLicense
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -InstallProductKey

Specifies the product key to install. The direct result object includes the supplied value in its
**ProductKey** property. Don't write that property to logs or other locations that unauthorized
users can access.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: InstallKey
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -Rearm

Selects a rearm operation. If you omit **RearmID**, the command rearms Windows. Use **RearmID** to
target a licensing SKU or application. A successful operation sets **RestartRequired** to `$true`.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: Rearm
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -RearmID

Specifies an activation ID for a licensing SKU or an application ID for an application-level rearm.
The command first searches for a licensing product whose activation ID matches the value. If it
doesn't find a product, it passes the value to the application-level rearm operation.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: Rearm
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ReinstallSystemLicenses

Selects the operation that reinstalls `.xrm-ms` files from the Windows system licensing-token and
OEM directories. The command continues after a file fails and reports counts and paths for
installed and failed files in the result object.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ReinstallLicenses
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -TokenCertThumbprint

Specifies the thumbprint of a certificate in the local computer certificate store for token-based
activation. The certificate must include an RSA private key, and its certificate chain must build
successfully. This parameter selects token activation; **TokenPIN** alone doesn't select an
operation.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ActivateToken
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -TokenPIN

Specifies the optional PIN for token-based activation. Provide **TokenCertThumbprint** to select the
token activation operation. Avoid including the PIN in command history or logs.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ActivateToken
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -UninstallProductKey

Selects the operation that uninstalls a product key from a licensing product. Use **ActivationID**
to target a specific product. If you omit **ActivationID**, the command selects the first primary
Windows product that has a partial product key and isn't an add-on product.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: UninstallKey
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

You can't pipe objects to this cmdlet.

## OUTPUTS

### System.Management.Automation.PSCustomObject

A direct operation returns a structured result object. Every operation result includes **Success**
and **Operation**. Successful results include additional properties that depend on the operation:

- Product-key installation: **ProductKey**.
- License-file installation: **LicenseFile**.
- System-license reinstallation: **LicensesInstalled**, **LicensesFailed**, **InstalledFiles**, and
  **FailedFiles**. **Success** is `$true` only when no individual license file fails.
- Rearm: **Target** and **RestartRequired**.
- Product-key removal: **ActivationID**.
- Online activation: **ActivationID** and **ProductName**.
- Offline activation: **ActivationID**, **ProductName**, and **ConfirmationID**.
- Token activation: **CertificateThumbprint**.
- Token-license removal: **ILID** and **ILvID**.

When the cmdlet catches a failure, it returns a result where **Success** is `$false`. The result
also includes **Operation**, **ErrorCode**, and **ErrorMessage**. **ErrorCode** is a hexadecimal
Windows HRESULT when the CIM exception provides one; otherwise, its value is `$null`. If an online
or offline activation operation resolved a product before the failure, the object also includes
**ActivationID** and **ProductName**.

The command returns no object when you don't select an operation or when you provide an incomplete
token-license removal combination that doesn't reach the operation.

### System.Management.Automation.Job

When you use **AsJob** through an implicit-remoting wrapper, the command returns a background job.
Use `Receive-Job` to retrieve the structured operation result from the job.

## NOTES

Run this cmdlet from an elevated PowerShell session. Its operations can change the product key,
activation state, installed license files, token licenses, or rearm state of the local computer.
Confirm the target and back up any required licensing information before you run an operation.

The target function doesn't declare the operation parameters as mandatory. Therefore, PowerShell
might bind a parameter set even when you omit the selector that the operation needs. In
particular, token activation requires **TokenCertThumbprint**, token-license removal requires both
**ILID** and **ILvID**, and offline activation requires **ConfirmationID**.

After product-key installation, product-key removal, and activation operations, the command requests
a best-effort licensing-status refresh. A refresh failure doesn't replace the result of the primary
operation. System-license reinstallation continues across individual file failures and reports the
aggregate result. A successful rearm result indicates that you must restart the computer.

The direct function catches operation errors and returns them as structured objects. Inspect
**Success**, **ErrorCode**, and **ErrorMessage** instead of relying on console output. Protect
product keys and token PINs from command history, transcripts, logs, and other unauthorized
disclosure.

## RELATED LINKS

- [Slmgr.vbs options for obtaining volume activation information](/windows-server/get-started/activation-slmgr-vbs-options)
- [Activate using Key Management Service](/windows/deployment/volume-activation/activate-using-key-management-service-vamt)
- [Monitor activation](/windows/deployment/volume-activation/monitor-activation-client)
