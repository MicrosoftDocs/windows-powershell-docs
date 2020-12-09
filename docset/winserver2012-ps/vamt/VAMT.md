---
Module Name: VAMT
Module Guid: C04E5406-950F-4CB4-9C5D-3E8C952214E6
Download Help Link: http://go.microsoft.com/fwlink/?linkid=285574
Help Version: 4.0.1.0
Locale: en-US
ms.assetid: 38E37D22-F0CF-4EBC-8E1D-8F75A0376C6A
manager: dansimp
ms.reviewer:
ms.author: v-anbarr
author: andreabarr
---

# VAMT Module
## Description
The enables network administrators and other IT professionals to automate and centrally manage the volume and retail-activation process for Windows, Microsoft Office, and select other Microsoft products. can manage volume activation using Multiple Activation Keys (MAKs) or the Windows Key Management Service (KMS). For more information about VAMT, see the [Volume Activation Management Tool Technical Reference](https://go.microsoft.com/fwlink/?LinkId=214550).

## VAMT Cmdlets
### [Add-VamtProductKey](./Add-VamtProductKey.md)
Adds the user-specified product key to a VAMT database.

### [Export-VamtData](./Export-VamtData.md)
Exports product data and product-key data from a VAMT database to a portable .cilx file.

### [Find-VamtManagedMachine](./Find-VamtManagedMachine.md)
Performs VAMT discovery operations.

### [Get-VamtConfirmationId](./Get-VamtConfirmationId.md)
Acquires confirmation IDs (CIDs) from the Microsoft licensing servers during proxy activation.

### [Get-VamtProduct](./Get-VamtProduct.md)
Retrieves the record of a product or list of products from a VAMT database.

### [Get-VamtProductKey](./Get-VamtProductKey.md)
Retrieves product-key records from a VAMT database.

### [Import-VamtData](./Import-VamtData.md)
Imports the data from a specified .cilx or .cil file into a VAMT database.

### [Initialize-VamtData](./Initialize-VamtData.md)
Initializes the VAMT database and removes all the data.

### [Install-VamtConfirmationId](./Install-VamtConfirmationId.md)
Installs Confirmation IDs (CID) acquired from Microsoft to the respective computers to complete proxy activation.

### [Install-VamtProductActivation](./Install-VamtProductActivation.md)
Activates products online, using the local computer's Internet connection.

### [Install-VamtProductKey](./Install-VamtProductKey.md)
Installs the specified product key on a product or a group of products.

### [Update-VamtProduct](./Update-VamtProduct.md)
Updates the VAMT database by querying the computers for their current status.

