---
document type: cmdlet
external help file: OSLicense-Help.xml
HelpUri: https://learn.microsoft.com/powershell/module/oslicense/get-adlicenseinfo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
Locale: en-US
Module Name: OSLicense
ms.date: 09/10/2026
PlatyPS schema version: 2024-05-01
title: Get-ADLicenseInfo
---

# Get-ADLicenseInfo

## SYNOPSIS
Gets Active Directory-based activation license information.

## SYNTAX

### Default

```
Get-ADLicenseInfo [-AsJob] [<CommonParameters>]
```

### ForestInstallationId

```
Get-ADLicenseInfo [-ProductKey <String>] [-AsJob] [<CommonParameters>]
```

### ActivationObjects

```
Get-ADLicenseInfo [-ActivationObjects] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `Get-ADLicenseInfo` cmdlet queries Active Directory-based activation information for Windows.
Without parameters, it returns the current operating system licensing product's activation ID,
license status, and Active Directory activation properties.

Use **ProductKey** to generate an offline forest installation ID for Active Directory-based
activation. Use **ActivationObjects** to enumerate activation objects in the Active Directory
configuration naming context.

This cmdlet is read-only. It doesn't install a product key, activate Windows, or change activation
objects.

> [!NOTE]
> `Get-ADLicenseInfo` is available in [Windows Server vNext Preview Build 29651](https://techcommunity.microsoft.com/discussions/windowsserverinsiders/announcing-windows-server-vnext-preview-build-29651/4549702)
> and the [2026-09 security update for Windows 11 (KB5124008)](https://support.microsoft.com/help/5124008).

## EXAMPLES

### Example 1: Generate a forest installation ID

This example uses a fictitious product key to generate the installation ID for offline forest
activation. The cmdlet returns an object that includes the supplied product key. Avoid writing the
object to shared logs when you use an actual key.

```powershell
$result = Get-ADLicenseInfo -ProductKey 'XXXXX-XXXXX-XXXXX-XXXXX-XXXXX'
$result.ForestInstallationId
```

The command generates the installation ID without installing the product key or changing the
activation state.

### Example 2: List activation objects as a background job

When you access the module through an implicit-remoting wrapper, this example starts the query as a
background job and receives its results. The command lists selected properties from each activation
object.

```powershell
$job = Get-ADLicenseInfo -ActivationObjects -AsJob
$activationObjects = Receive-Job -Job $job -Wait -AutoRemoveJob
$activationObjects | Select-Object Name, DistinguishedName, ObjectClass
```

## PARAMETERS

### -ActivationObjects

Enumerates the activation objects in the `CN=Activation Objects,CN=Microsoft SPP` container in the
Active Directory configuration naming context.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ActivationObjects
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

Runs the command as a background job when you access the module through an implicit-remoting
wrapper. This parameter returns a job object immediately. Use `Receive-Job` to retrieve the license
information from the job.

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

### -ProductKey

Specifies the product key that the cmdlet uses to generate an offline forest installation ID. The
cmdlet returns an object that contains both the product key and the installation ID. Treat
the output as sensitive information when you specify an actual product key.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ForestInstallationId
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

This cmdlet doesn't accept input from the pipeline.

## OUTPUTS

### System.Management.Automation.PSCustomObject

For the `Default` parameter set, the cmdlet returns an object with **Name**, **Description**,
**ActivationID**, **LicenseStatus**, **ADActivationObjectName**, **ADActivationObjectDN**,
**ADActivationCsvlkPid**, and **ADActivationCsvlkSkuId** properties.

For the `ForestInstallationId` parameter set, it returns an object with **ProductKey** and
**ForestInstallationId** properties. For the `ActivationObjects` parameter set, it returns one
object for each activation object with **DistinguishedName**, **Name**, and **ObjectClass**
properties. When the `ActiveDirectory` module is available, each activation object also includes
**Created** and **Modified** properties.

If a top-level query fails, the cmdlet returns an object with **Success**, **ErrorCode**, and
**ErrorMessage** properties.

### System.Management.Automation.Job

When you use **AsJob** through an implicit-remoting wrapper, the cmdlet returns a job object. The
job's output contains the objects that the preceding section describes.

## NOTES

The default and **ProductKey** operations query the local Software Licensing service. The
**ActivationObjects** operation uses the `ActiveDirectory` module if it's available and otherwise
uses Active Directory Service Interfaces (ADSI). The computer must be able to reach the domain, and
your account must be able to read the activation-object container.

The source function doesn't define **AsJob**. The implicit-remoting wrapper adds the parameter,
which isn't available when you import the source function directly.

The cmdlet returns `$null` when it finds no applicable Windows licensing product or can't query
activation objects.

## RELATED LINKS

- [Active Directory-Based Activation overview](/windows/deployment/volume-activation/active-directory-based-activation-overview)
- [Activate using Active Directory-based activation](/windows/deployment/volume-activation/activate-using-active-directory-based-activation-client)
- [Slmgr.vbs Active Directory-based activation options](/windows-server/get-started/activation-slmgr-vbs-options#active-directory-based-activation-configuration-options)
- [about_Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs)
