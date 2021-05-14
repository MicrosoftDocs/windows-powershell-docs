---
external help file: WSUS_Cmdlets.xml
Module Name: UpdateServices
online version: https://docs.microsoft.com/powershell/module/updateservices/get-wsusupdate?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Get-WsusUpdate

## SYNOPSIS
Gets the Windows Server Update Services (WSUS) update object with details about the update.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Get-WsusUpdate [-Approval <WsusApprovedState>] [-Classification <WsusUpdateClassifications>]
 [-Status <WsusUpdateInstallationState>] [-UpdateServer <IUpdateServer>]
```

### UNNAMED_PARAMETER_SET_2
```
Get-WsusUpdate [-RevisionNumber <Int32>] [-UpdateServer <IUpdateServer>] -UpdateId <Guid>
```

## DESCRIPTION
The **Get-WsusUpdate** cmdlet gets the Windows Server Update Services (WSUS) update object with details about the update.
This cmdlet requires the update unique identifier (GUID) or a set of filter criteria such as classification, approval and status as parameter.

The **Get-WsusUpdate** cmdlet can be called in two ways: 

 -- Passing in the Update ID (GUID) and RevisionNumber.
This cmdlet will return a single update matching the specified Update ID and revision number. 

 -- Passing in filter parameters.
These parameters include **Classification**, **Approval**, and **Status**.
One or more updates matching the specified criteria will be returned.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-WsusUpdate -Classification All -Approval Unapproved -Status FailedOrNeeded
```

This example gets allunapproved updates with a status of failed or needed.

### EXAMPLE 2
```
PS C:\> Get-WsusUpdate -Classification Critical -Approval Unapproved -Status Any
Title                         Classification                    Installed/Not Applicable  Approved 
Percentage 
-----                         --------------                ----------------------------- -------- 
Windows XP Update Package,    Critical Updates                                            NotApproved 
October 25, 2001
```

This example gets allcriticalunapproved updates.

## PARAMETERS

### -Approval
Specifies the approved state of the one or more updates to be returned.
The acceptable values for this parameter are:

 -- Unapproved 

 -- Declined 

 -- Approved 

 -- AnyExceptDeclined

```yaml
Type: WsusApprovedState
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Classification
Specifies the classification of updates for which you want to get updates.
The acceptable values for this parameter are:

 -- All 

 -- Critical 

 -- Security 

 -- WSUS

```yaml
Type: WsusUpdateClassifications
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: WUUpdateClassification.All
Accept pipeline input: False
Accept wildcard characters: False
```

### -RevisionNumber
Specifies the revision number of a specific revision of an update.
To specify the latest revision, set to zero.

```yaml
Type: Int32
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Specifies the installation status for which to search.
An update will be included only if it has at least one computer with the specified status.
The acceptable values for this parameter are:

 -- Needed 

 -- FailedOrNeeded 

 -- InstalledNotApplicableOrNoStatus 

 -- Failed 

 -- InstalledNotApplicable 

 -- NoStatus 

 -- Any

```yaml
Type: WsusUpdateInstallationState
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateId
Specifies the update by its GUID.
The GUID uniquely identifies the Group Policy Object (GPO).

```yaml
Type: Guid
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateServer
Specifies the object that contains the WSUS server.
This value is obtained by calling the Get-WsusServer cmdlet and piping the resulting IUpdateServer object into this cmdlet.

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

## INPUTS

### None

## OUTPUTS

### Microsoft.UpdateServices.Commands.WsusUpdate
WsusUpdate

## NOTES

## RELATED LINKS

[Get-WsusServer](./Get-WsusServer.md)

