---
document type: cmdlet
external help file: OSLicense-Help.xml
HelpUri: ''
Locale: en-US
Module Name: OSLicense
ms.date: 09/07/2026
PlatyPS schema version: 2024-05-01
title: Get-OSLicenseInfo
---

# Get-OSLicenseInfo

## SYNOPSIS
Gets Windows operating system licensing information.

## SYNTAX

### Default

```
Get-OSLicenseInfo [-AsJob] [<CommonParameters>]
```

### All

```
Get-OSLicenseInfo [-All] [-AsJob] [<CommonParameters>]
```

### ActivationID

```
Get-OSLicenseInfo [-ActivationID <String>] [-AsJob] [<CommonParameters>]
```

### TokenLicenses

```
Get-OSLicenseInfo [-TokenBasedLicenses] [-AsJob] [<CommonParameters>]
```

### TokenCertificates

```
Get-OSLicenseInfo [-TokenBasedCertificates] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION

The `Get-OSLicenseInfo` cmdlet queries the local Software Licensing CIM classes and returns
structured licensing information. Without parameters, the cmdlet returns the first Windows
operating system product that has a partial product key and isn't an add-on license.

Use **ActivationID** to query a specific product, **All** to query every product that has an
application ID and name, or the token parameters to query token-based licenses or certificates.

The cmdlet is available through an applicable Windows update. The KB number for that update is
pending confirmation.

## EXAMPLES

### Example 1: Get the primary Windows license status

```powershell
Get-OSLicenseInfo |
    Select-Object Name, ActivationID, LicenseStatus, PartialProductKey,
        GracePeriodRemaining, EvaluationEndDate
```

This example gets the primary Windows operating system license and selects properties useful for
checking its activation state and expiration.

### Example 2: Review token-based licenses

```powershell
Get-OSLicenseInfo -TokenBasedLicenses |
    Sort-Object ExpirationDate |
    Select-Object ILID, ILvID, AuthorizationStatus, Description, ExpirationDate
```

This example lists token-based licenses in expiration-date order and selects their identifying and
status properties.

## PARAMETERS

### -ActivationID

Specifies the activation ID of the software licensing product to return. The cmdlet performs an
exact match against the **ID** property of the `SoftwareLicensingProduct` CIM instance.

```yaml
Type: System.String
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: ActivationID
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -All

Returns every software licensing product whose **ApplicationID** and **Name** properties are
populated. The results can include products other than the primary Windows operating system
license.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: All
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
parameter is supplied by the wrapper and isn't declared by the local `OSLicense` module function.

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

### -TokenBasedCertificates

Returns token-based activation certificate information from the local software licensing service,
including the issued certificate thumbprint list, grant number, ILID, ILvID, and additional
information.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: TokenCertificates
  Position: Named
  IsRequired: false
  ValueFromPipeline: false
  ValueFromPipelineByPropertyName: false
  ValueFromRemainingArguments: false
DontShow: false
AcceptedValues: []
HelpMessage: ''
```

### -TokenBasedLicenses

Returns installed token-based activation licenses. Each result includes the ILID, ILvID,
authorization status, description, and expiration date.

```yaml
Type: System.Management.Automation.SwitchParameter
DefaultValue: ''
SupportsWildcards: false
Aliases: []
ParameterSets:
- Name: TokenLicenses
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

For the default, **All**, and **ActivationID** parameter sets, the cmdlet returns objects that
combine product and licensing-service data. Notable properties include **Name**, **ActivationID**,
**ApplicationID**, **PartialProductKey**, **LicenseStatus**, **LicenseStatusReason**,
**GracePeriodRemaining**, **EvaluationEndDate**, **OfflineInstallationId**, rearm counts,
**Version**, **ClientMachineID**, and **IsKeyManagementServiceMachine**. KMS properties such as
**KeyManagementServiceMachine**, **KeyManagementServicePort**, and activation and renewal intervals
are present only when KMS configuration or discovery data exists.

For **TokenBasedLicenses**, each object has **ILID**, **ILvID**, **AuthorizationStatus**,
**Description**, and **ExpirationDate** properties. For **TokenBasedCertificates**, the object has
**TokenBasedActivationCertificateIssuedList**, **TokenBasedActivationGrantNumber**,
**TokenBasedActivationILID**, **TokenBasedActivationILVID**, and
**TokenBasedActivationAdditionalInfo** properties.

### System.Management.Automation.Job

When you use **AsJob** through an implicit-remoting wrapper, the cmdlet returns a job object. Use
`Receive-Job` to retrieve the licensing objects from the completed job.

## NOTES

The cmdlet returns no object when it finds no matching licensing data or when its CIM query fails.
It returns unset date values as `$null`. It also converts licensing sentinel values to contextual
strings such as `Unlimited`, `No Limit`, `N/A`, or `Not Set` where applicable.

The **LicenseStatus** value is a localized status string. **LicenseStatusReason** is formatted as a
hexadecimal error code when the source value isn't `$null`.

## RELATED LINKS

- [Slmgr.vbs options for obtaining volume activation information](/windows-server/get-started/activation-slmgr-vbs-options)
- [Activate using Key Management Service](/windows/deployment/volume-activation/activate-using-key-management-service-vamt)
- [Monitor activation](/windows/deployment/volume-activation/monitor-activation-client)
- [SoftwareLicensingProduct class](/previous-versions/windows/desktop/sppwmi/softwarelicensingproduct)
- [SoftwareLicensingService class](/previous-versions/windows/desktop/sppwmi/softwarelicensingservice)
