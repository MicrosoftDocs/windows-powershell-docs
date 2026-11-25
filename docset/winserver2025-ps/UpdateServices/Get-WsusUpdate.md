---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.UpdateServices.Commands.dll-Help.xml
Module Name: UpdateServices
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/updateservices/get-wsusupdate?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Get-WsusUpdate
---

# Get-WsusUpdate

## SYNOPSIS

Gets the WSUS update object with details about the update.

## SYNTAX

### ID

```powershell
Get-WsusUpdate [-UpdateServer <IUpdateServer>] -UpdateId <Guid> [-RevisionNumber <Int32>] [<CommonParameters>]
```

### Scoped

```powershell
Get-WsusUpdate [-UpdateServer <IUpdateServer>] [-Classification <WsusUpdateClassifications>]
 [-Approval <WsusApprovedState>] [-Status <WsusUpdateInstallationState>] [<CommonParameters>]
```

## DESCRIPTION

The **Get-WsusUpdate** cmdlet gets the Windows Server Update Services (WSUS) update object with details about the update. This cmdlet requires the update unique identifier (GUID) or a set of filter criteria such as classification, approval and status as parameter.

The **Get-WsusUpdate** cmdlet can be called in two ways:

- Passing in the Update ID (GUID) and **RevisionNumber**. This cmdlet returns a single update matching the specified Update ID and revision number.
- Passing in filter parameters. These parameters include **Classification**, **Approval**, and **Status**. One or more updates matching the specified criteria are returned.

## EXAMPLES

### Example 1: Get updates by status

```powershell
PS C:\> Get-WsusUpdate -Classification All -Approval Unapproved -Status FailedOrNeeded
```

This command gets all unapproved updates with a status of failed or needed.

### Example 2: Get critical unapproved updates

```text
PS C:\> Get-WsusUpdate -Classification Critical -Approval Unapproved -Status Any
Title                         Classification                    Installed/Not Applicable  Approved
Percentage
-----                         --------------                ----------------------------- --------
Windows XP Update Package,    Critical Updates                                            NotApproved
October 25, 2001
```

This command gets all critical unapproved updates.

## PARAMETERS

### -Approval

Specifies the approved state of the one or more updates to be returned. The acceptable values for this parameter are:

- Unapproved
- Declined
- Approved
- AnyExceptDeclined

```yaml
Type: WsusApprovedState
Parameter Sets: Scoped
Aliases:
Accepted values: Approved, Unapproved, AnyExceptDeclined, Declined

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Classification

Specifies the classification of updates for which you want to get updates. The acceptable values for this parameter are:

- All
- Critical
- Security
- WSUS

```yaml
Type: WsusUpdateClassifications
Parameter Sets: Scoped
Aliases:
Accepted values: All, Critical, Security, WSUS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RevisionNumber

Specifies the revision number of a specific revision of an update. To specify the latest revision, set to zero.

```yaml
Type: Int32
Parameter Sets: ID
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status

Specifies the installation status for which to search. An update will be included only if it has at least one computer with the specified status. The acceptable values for this parameter are:

- Needed
- FailedOrNeeded
- InstalledNotApplicableOrNoStatus
- Failed
- InstalledNotApplicable
- NoStatus
- Any

```yaml
Type: WsusUpdateInstallationState
Parameter Sets: Scoped
Aliases:
Accepted values: NoStatus, InstalledOrNotApplicable, InstalledOrNotApplicableOrNoStatus, Failed, Needed, FailedOrNeeded, Any

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateId

Specifies the update by its GUID. The GUID uniquely identifies the Windows Update package.

```yaml
Type: Guid
Parameter Sets: ID
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateServer

Specifies the object that contains the WSUS server. This value is obtained by calling the [Get-WsusServer](./Get-WsusServer.md) cmdlet and passing the resulting **IUpdateServer** object into this cmdlet.

```yaml
Type: IUpdateServer
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters

This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.UpdateServices.Administration.IUpdateServer

## OUTPUTS

### Microsoft.UpdateServices.Commands.WsusUpdate

## NOTES

## RELATED LINKS

[Approve-WsusUpdate](./Approve-WsusUpdate.md)

[Deny-WsusUpdate](./Deny-WsusUpdate.md)

[Get-WsusServer](./Get-WsusServer.md)
