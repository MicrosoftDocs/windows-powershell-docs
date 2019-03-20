---
Module Name: PKIClient
Module Guid: CF094C6B-63D1-4DDA-BF70-15A602C4EB2B
Download Help Link: http://go.microsoft.com/fwlink/?LinkID=216900
Help Version: 3.0.0.0
Locale: en-US
ms.assetid: 8008D3A6-4E97-4977-92F7-795EF45B4A27
ms.reviewer:
ms.author: kenwith
author: kenwith
---

# PKIClient Module
## Description
This reference provides cmdlet descriptions and syntax for all public key infrastructure (PKI) client-specific cmdlets. It lists the cmdlets in alphabetical order based on the verb at the beginning of the cmdlet.

## PKIClient Cmdlets
### [Add-CertificateEnrollmentPolicyServer](./Add-CertificateEnrollmentPolicyServer.md)
Adds an enrollment policy server to the current user or local system configuration.

### [Export-Certificate](./Export-Certificate.md)
Exports a certificate from a certificate store into a file.

### [Export-PfxCertificate](./Export-PfxCertificate.md)
Exports a certificate or a PFXData object to a Personal Information Exchange (PFX) file.

### [Get-Certificate](./Get-Certificate.md)
Submits a certificate request to an enrollment server and installs the response or retrieves a certificate for a previously submitted request.

### [Get-CertificateAutoEnrollmentPolicy](./Get-CertificateAutoEnrollmentPolicy.md)
Retrieves certificate auto-enrollment policy settings.

### [Get-CertificateEnrollmentPolicyServer](./Get-CertificateEnrollmentPolicyServer.md)
Returns all of the certificate enrollment policy server URL configurations.

### [Get-CertificateNotificationTask](./Get-CertificateNotificationTask.md)
Returns all registered certificate notification tasks.

### [Get-PfxData](./Get-PfxData.md)
Extracts the content of a Personal Information Exchange (PFX) file into a structure without importing it to certificate store.

### [Import-Certificate](./Import-Certificate.md)
Imports one or more certificates into a certificate store.

### [Import-PfxCertificate](./Import-PfxCertificate.md)
Imports certificates and private keys from a Personal Information Exchange (PFX) file to the destination store.

### [New-CertificateNotificationTask](./New-CertificateNotificationTask.md)
Creates a new task in the Task Scheduler that will be triggered when a certificate is replaced, expired, or about to expired.

### [New-SelfSignedCertificate](./New-SelfSignedCertificate.md)
Creates a new self-signed certificate for testing purposes.

### [Remove-CertificateEnrollmentPolicyServer](./Remove-CertificateEnrollmentPolicyServer.md)
Removes an enrollment policy server and the URL of the enrollment policy server from the current user or local computer configuration.

### [Remove-CertificateNotificationTask](./Remove-CertificateNotificationTask.md)
Removes a certificate notification task from Task Scheduler.

### [Set-CertificateAutoEnrollmentPolicy](./Set-CertificateAutoEnrollmentPolicy.md)
Sets local certificate auto-enrollment policy.

### [Switch-Certificate](./Switch-Certificate.md)
Marks one certificate as having been replaced by another certificate.

### [Test-Certificate](./Test-Certificate.md)
Verifies a certificate according to the input parameters.

