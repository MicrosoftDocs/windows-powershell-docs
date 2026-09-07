---
document type: cmdlet
external help file: OSLicense-Help.xml
HelpUri: ''
Locale: en-US
Module Name: OSLicense
ms.date: 09/07/2026
PlatyPS schema version: 2024-05-01
title: Invoke-ADLicense
---

# Invoke-ADLicense

## SYNOPSIS
Performs Active Directory-based licensing operations.

## SYNTAX

### ActivateOnline

```
Invoke-ADLicense [-ActivateOnline] [-ProductKey <String>] [-ConfirmationID <String>]
 [-ActivationObjectName <String>] [-AsJob] [<CommonParameters>]
```

### ActivateForest

```
Invoke-ADLicense [-ActivateForest] [-ProductKey <String>] [-ConfirmationID <String>]
 [-ActivationObjectName <String>] [-AsJob] [<CommonParameters>]
```

### DeleteActivationObjects

```
Invoke-ADLicense [-DeleteActivationObjects <String>] [-AsJob] [<CommonParameters>]
```

### None

```
Invoke-ADLicense [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `Invoke-ADLicense` cmdlet performs Active Directory-based activation and deletes Active
Directory activation objects. Online activation calls the software licensing service to create an
activation object. Forest activation deposits an offline activation confirmation. The deletion
operation accepts either the distinguished name or the relative name of an activation object.

The cmdlet returns structured objects for completed operations and caught failures. It returns no
object when the software licensing service query returns no instance or when you don't select an
operation.

The applicable Windows update KB number for this cmdlet is pending confirmation.

## EXAMPLES

### Example 1: Deposit a fictitious offline activation confirmation

> [!CAUTION]
> This example uses a fictitious product key, confirmation ID, and activation object name. The
> command changes Active Directory-based activation state. Replace the values only in an authorized
> test environment after you verify the intended licensing operation.

```powershell
$activationParameters = @{
    ActivateForest      = $true
    ProductKey           = 'AAAAA-BBBBB-CCCCC-DDDDD-EEEEE'
    ConfirmationID       = '000000000000000000000000000000000000000000000000'
    ActivationObjectName = 'Fabrikam-Docs-Activation-Object'
}

Invoke-ADLicense @activationParameters
```

This example requests forest activation by depositing a fictitious offline activation confirmation.
It doesn't represent an executed activation or actual command output.

### Example 2: Delete a fictitious activation object by relative name

> [!CAUTION]
> Deleting an activation object is immediate and the cmdlet doesn't prompt for confirmation. The
> object name in this example is fictitious. Verify the target object and your recovery plan before
> you run a deletion command in an authorized environment.

```powershell
Invoke-ADLicense -DeleteActivationObjects 'Fabrikam-Docs-Obsolete-Activation-Object'
```

This example requests deletion by relative name. The cmdlet resolves a relative name under the
`CN=Activation Objects,CN=Microsoft SPP` container in the configuration naming context. It doesn't
represent an executed deletion or actual command output.

## PARAMETERS

### -ActivateForest

Requests forest activation by depositing an offline activation confirmation through the software
licensing service. **ProductKey** and **ConfirmationID** are validated at runtime and must have
values when you use this parameter.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ActivateForest
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

Requests online Active Directory-based activation through the software licensing service. The
**ProductKey** parameter is validated at runtime and must have a value when you use this parameter.

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

### -ActivationObjectName

Specifies the name of the activation object for online or forest activation. When you omit this
parameter, the cmdlet passes an empty string to the corresponding software licensing service method.

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
- Name: ActivateForest
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

Runs the command as a background job. The implicit-remoting wrapper that exposes this command adds
this parameter; the `Invoke-ADLicense` function in the OSLicense module doesn't declare it. Use
`Receive-Job` to retrieve the operation result.

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

### -ConfirmationID

Specifies the offline activation confirmation ID. The function declares this parameter for both
activation parameter sets, but uses it only with **ActivateForest**. The value is validated at
runtime and is required for forest activation. The **ActivateOnline** operation ignores this value.

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
- Name: ActivateForest
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -DeleteActivationObjects

Specifies an activation object to delete. Enter a distinguished name that starts with `CN=`, or
enter the relative name without the `CN=` prefix for an object in the
`CN=Activation Objects,CN=Microsoft SPP` container. The cmdlet uses `Remove-ADObject` when the
ActiveDirectory module is available. Otherwise, it uses Active Directory Service Interfaces (ADSI)
to delete the object tree.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: DeleteActivationObjects
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -ProductKey

Specifies the product key for online or forest activation. The cmdlet validates this value at
runtime and requires it for either activation operation. A successful activation result includes
this value in its **ProductKey** property. Protect command output that contains a product key.

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
- Name: ActivateForest
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

For a successful online or forest activation request, the cmdlet returns an object with these
properties:

- **Success** is `$true`.
- **Operation** is `ActivateOnline` or `ActivateForest`.
- **ProductKey** is the value supplied to **ProductKey**.
- **ActivationObjectName** is the value supplied to **ActivationObjectName**, or an empty string
  when omitted.

For a successful deletion, the cmdlet returns an object with these properties:

- **Success** is `$true`.
- **Operation** is `DeleteActivationObject`.
- **ActivationObject** is the value supplied to **DeleteActivationObjects**.

For a caught failure, the cmdlet returns an object with these properties:

- **Success** is `$false`.
- **ErrorCode** is the CIM `error_Code` value formatted as an eight-digit hexadecimal string with a
  `0x` prefix, or `$null` when CIM error data doesn't provide a code.
- **ErrorMessage** is the CIM `error_WindowsErrorMessage` value when available. Otherwise, it is the
  exception message or the string representation of the caught error.

The cmdlet returns no object when the CIM query returns no `SoftwareLicensingService` instance or
when no operation is selected.

### System.Management.Automation.Job

When you use **AsJob**, the implicit-remoting wrapper returns a job object instead of returning the
operation result directly. Use `Receive-Job` to receive the underlying structured result, or no
output when the underlying command returns no object.

## NOTES

Run this cmdlet with the permissions required to invoke software licensing service methods and to
modify Active Directory activation objects.

The `Invoke-ADLicense` function doesn't implement `SupportsShouldProcess`. For deletion, it calls
`Remove-ADObject` with confirmation disabled when the ActiveDirectory module is available, or calls
the ADSI `DeleteTree()` method otherwise.

The **ProductKey**, **ConfirmationID**, and activation switches aren't marked as mandatory in the
function metadata. The function performs runtime validation: both activation operations require a
product key, and forest activation also requires a confirmation ID.

The generated implicit-remoting wrapper adds **AsJob** to every parameter set. This wrapper
parameter is intentionally retained even though it isn't present in the module function source.

## RELATED LINKS

- [Monitor activation](/windows/deployment/volume-activation/monitor-activation-client)
- [Slmgr.vbs Active Directory-based activation options](/windows-server/get-started/activation-slmgr-vbs-options#active-directory-based-activation-configuration-options)
- [Receive-Job](/powershell/module/microsoft.powershell.core/receive-job)
