---
document type: cmdlet
external help file: OSLicense-Help.xml
HelpUri: https://learn.microsoft.com/powershell/module/oslicense/get-kmslicenseinfo?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
Locale: en-US
Module Name: OSLicense
ms.date: 09/11/2026
PlatyPS schema version: 2024-05-01
title: Get-KmsLicenseInfo
---

# Get-KmsLicenseInfo

## SYNOPSIS
Gets Key Management Service (KMS) licensing information.

## SYNTAX

### __AllParameterSets

```
Get-KmsLicenseInfo [<CommonParameters>]
```

## ALIASES

This cmdlet has no aliases.

## DESCRIPTION

The `Get-KmsLicenseInfo` cmdlet queries the local software licensing service for KMS client and KMS
host configuration, activation intervals, discovery information, and request counts. The cmdlet is
read-only and doesn't change the licensing configuration.

The cmdlet returns KMS service properties for the local computer. When it finds a Windows operating
system licensing product with a partial product key, it also returns activation and renewal
intervals and information about the discovered KMS host.

> [!NOTE]
> `Get-KmsLicenseInfo` is available in [Windows Server vNext Preview Build 29651](https://techcommunity.microsoft.com/discussions/windowsserverinsiders/announcing-windows-server-vnext-preview-build-29651/4549702)
> and the [2026-09 security update for Windows 11 (KB5124008)](https://support.microsoft.com/help/5124008).

## EXAMPLES

### Example 1: Get KMS client configuration

```powershell
Get-KmsLicenseInfo |
    Select-Object KeyManagementServiceMachine, KeyManagementServicePort,
        KeyManagementServiceLookupDomain, KeyManagementServiceHostCaching
```

This example gets the configured KMS client host, port, lookup domain, and host-caching setting.

### Example 2: Review KMS host request counts

```powershell
Get-KmsLicenseInfo |
    Select-Object IsKeyManagementServiceMachine, KeyManagementServiceListeningPort,
        KeyManagementServiceCurrentCount, KeyManagementServiceLicensedRequests,
        KeyManagementServiceFailedRequests, KeyManagementServiceTotalRequests
```

This example selects KMS host configuration and request-count properties from the returned object.

## PARAMETERS

## INPUTS

### None

This cmdlet doesn't accept input from the pipeline.

## OUTPUTS

### System.Management.Automation.PSCustomObject

The cmdlet returns an object with the following KMS service properties:

- **KeyManagementServiceMachine**
- **KeyManagementServicePort**
- **KeyManagementServiceLookupDomain**
- **IsKeyManagementServiceMachine**
- **KeyManagementServiceListeningPort**
- **KeyManagementServiceDnsPublishing**
- **KeyManagementServiceHostCaching**
- **KeyManagementServiceLowPriority**
- **KeyManagementServiceCurrentCount**
- **KeyManagementServiceUnlicensedRequests**
- **KeyManagementServiceLicensedRequests**
- **KeyManagementServiceOOBGraceRequests**
- **KeyManagementServiceOOTGraceRequests**
- **KeyManagementServiceNonGenuineGraceRequests**
- **KeyManagementServiceTotalRequests**
- **KeyManagementServiceNotificationRequests**
- **KeyManagementServiceFailedRequests**

When a Windows operating system licensing product is available, the object also includes
**VLActivationInterval**, **VLRenewalInterval**, **DiscoveredKeyManagementServiceMachineName**, and
**DiscoveredKeyManagementServiceMachinePort**.

## NOTES

The cmdlet returns no object when it can't obtain the local **SoftwareLicensingService** CIM
instance or when a CIM query fails.

When KMS request-count or current-count data isn't available, the cmdlet returns `N/A` instead of
the numeric value that the licensing service uses to indicate unavailable data.

## RELATED LINKS

- [Key Management Services (KMS) activation planning for Windows Server](/windows-server/get-started/kms-activation-planning)
- [Activate using Key Management Service](/windows/deployment/volume-activation/activate-using-key-management-service-vamt)
- [Monitor activation](/windows/deployment/volume-activation/monitor-activation-client)
- [SoftwareLicensingService class](/previous-versions/windows/desktop/sppwmi/softwarelicensingservice)
- [SoftwareLicensingProduct class](/previous-versions/windows/desktop/sppwmi/softwarelicensingproduct)
