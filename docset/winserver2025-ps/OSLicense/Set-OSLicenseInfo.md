---
document type: cmdlet
external help file: OSLicense-Help.xml
HelpUri: https://learn.microsoft.com/powershell/module/oslicense/set-oslicenseinfo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
Locale: en-US
Module Name: OSLicense
ms.date: 09/10/2026
PlatyPS schema version: 2024-05-01
title: Set-OSLicenseInfo
---

# Set-OSLicenseInfo

## SYNOPSIS
Sets the Windows volume activation type.

## SYNTAX

### __AllParameterSets

```
Set-OSLicenseInfo [-ActivationType] <Int32> [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `Set-OSLicenseInfo` cmdlet changes the volume activation type that the Windows software
licensing service uses on the local computer. Use the default activation behavior or require
Active Directory-based, Key Management Services (KMS), or token-based activation.

The cmdlet returns a structured object that indicates whether the operation succeeded. If a runtime
Common Information Model (CIM) failure occurs, the object includes the available Windows error code
and error message. The cmdlet doesn't write the failure to the error stream.

> [!NOTE]
> `Set-OSLicenseInfo` is available in [Windows Server vNext Preview Build 29651](https://techcommunity.microsoft.com/discussions/windowsserverinsiders/announcing-windows-server-vnext-preview-build-29651/4549702)
> and the [2026-09 security update for Windows 11 (KB5124008)](https://support.microsoft.com/help/5124008).

## EXAMPLES

### Example 1: Require Active Directory-based activation

This command configures the local computer to use Active Directory-based activation. Changing the
activation type can prevent activation if the required activation infrastructure isn't available,
so confirm your organization's activation configuration before you run the command.

```powershell
$result = Set-OSLicenseInfo -ActivationType 1
$result
```

Inspect the **Success** property to determine whether the licensing service applied the change. If
**Success** is `$false`, inspect **ErrorCode** and **ErrorMessage** for failure details.

### Example 2: Restore the default activation behavior

This command restores the default volume activation behavior. This operation changes the local
computer's licensing configuration, so verify that the default behavior is appropriate before you
run the command.

```powershell
Set-OSLicenseInfo -ActivationType 0
```

## PARAMETERS

### -ActivationType

Specifies the volume activation type. The parameter supports these values:

- `0` - Use the default activation type.
- `1` - Use Active Directory-based activation.
- `2` - Use KMS activation.
- `3` - Use token-based activation.

You must specify this parameter. PowerShell rejects values outside the range `0` through `3`
before the cmdlet changes the licensing configuration.

```yaml
Type: System.Int32
DefaultValue: ''
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
AcceptedValues:
- 0
- 1
- 2
- 3
HelpMessage: ''
```

### -AsJob

Runs the command as a background job when you invoke it through an implicit-remoting wrapper. This
wrapper supplies the parameter, and the local `OSLicense` module function doesn't declare it.

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

## INPUTS

### None

This cmdlet doesn't accept pipeline input.

## OUTPUTS

### System.Management.Automation.PSCustomObject

When the licensing service applies the activation type, the cmdlet returns an object. Its
**Success** property is `$true`, and its **ActivationType** property contains the requested value.

When a runtime CIM operation fails, the cmdlet returns an object. The **Success** property is
`$false`, the **ErrorCode** property contains the available Windows HRESULT in hexadecimal format,
and the **ErrorMessage** property contains the available Windows error message. The cmdlet returns
no object if it can't find the software licensing service.

### System.Management.Automation.Job

When you specify the **AsJob** parameter through an implicit-remoting wrapper, the cmdlet returns a
job object. Use `Receive-Job` to retrieve the structured result from the completed job.

## NOTES

Run this cmdlet from an elevated PowerShell session. Parameter-binding and validation failures,
including an **ActivationType** value outside the supported range, occur before the cmdlet invokes
the licensing service. The cmdlet doesn't return these failures as structured result objects.

## RELATED LINKS

- [Slmgr.vbs options for volume activation](/windows-server/get-started/activation-slmgr-vbs-options)
- [SoftwareLicensingService class](/previous-versions/windows/desktop/sppwmi/softwarelicensingservice)
