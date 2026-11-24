---
document type: cmdlet
external help file: OSLicense-Help.xml
HelpUri: https://learn.microsoft.com/powershell/module/oslicense/get-subscriptionlicenseinfo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
Locale: en-US
Module Name: OSLicense
ms.date: 09/11/2026
PlatyPS schema version: 2024-05-01
title: Get-SubscriptionLicenseInfo
---

# Get-SubscriptionLicenseInfo

## SYNOPSIS
Gets Windows subscription licensing information.

## SYNTAX

### __AllParameterSets

```
Get-SubscriptionLicenseInfo [<CommonParameters>]
```

## ALIASES

This cmdlet has no aliases.

## DESCRIPTION

The `Get-SubscriptionLicenseInfo` cmdlet queries the local software licensing service for the
Windows subscription type, status, expiration value, and edition. It returns both localized type
and status text and their underlying numeric values.

This cmdlet is read-only and doesn't enable, disable, refresh, acquire, or remove a subscription
license.

> [!NOTE]
> `Get-SubscriptionLicenseInfo` is available in [Windows Server vNext Preview Build 29651](https://techcommunity.microsoft.com/discussions/windowsserverinsiders/announcing-windows-server-vnext-preview-build-29651/4549702)
> and the [2026-09 security update for Windows 11 (KB5124008)](https://support.microsoft.com/help/5124008).

## EXAMPLES

### Example 1: Get subscription licensing information

```powershell
Get-SubscriptionLicenseInfo
```

This example gets the subscription type, status, expiration value, and edition for the local
computer.

### Example 2: Check whether subscription licensing is active

```powershell
$subscription = Get-SubscriptionLicenseInfo

if ($subscription.SubscriptionStatusValue -eq 1) {
    'Subscription licensing is active.'
}
```

This example checks the underlying numeric status value. A value of `1` represents an active
subscription.

## PARAMETERS

## INPUTS

### None

This cmdlet doesn't accept input from the pipeline.

## OUTPUTS

### System.Management.Automation.PSCustomObject

The cmdlet returns an object with the following properties:

- **SubscriptionType** - Localized text for the subscription type.
- **SubscriptionTypeValue** - The underlying numeric subscription type.
- **SubscriptionStatus** - Localized text for the subscription status.
- **SubscriptionStatusValue** - The underlying numeric subscription status.
- **SubscriptionExpiry** - The subscription expiration value returned by the licensing service.
- **SubscriptionEdition** - The Windows edition associated with the subscription.

For **SubscriptionTypeValue**, the cmdlet maps `0` to `User Based Subscription`, `9999` to
`Invalid`, and `120` to `Not Installed`. It formats other values as `Unknown (<value>)`.

For **SubscriptionStatusValue**, the cmdlet maps `0` to `Not Active`, `1` to `Active`, `100` to
`Disabled`, `110` to `Expired`, and `120` to `Not Installed`. It formats other values as
`Unknown (<value>)`.

## NOTES

The cmdlet returns no object when it can't obtain the local **SoftwareLicensingService** CIM
instance or when the query fails. It returns **SubscriptionExpiry** without converting the value
that the licensing service provides.

## RELATED LINKS

- [Windows subscription activation](/windows/deployment/windows-subscription-activation)
- [SoftwareLicensingService class](/previous-versions/windows/desktop/sppwmi/softwarelicensingservice)
