---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.Windows.Whea.WheaMemoryPolicy.dll-Help.xml
Module Name: WHEA
ms.date: 12/20/2016
online version: https://learn.microsoft.com/powershell/module/whea/set-wheamemorypolicy?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Set-WheaMemoryPolicy
---

# Set-WheaMemoryPolicy

## SYNOPSIS
Sets the WHEA memory policy for a computer.

## SYNTAX

```
Set-WheaMemoryPolicy [-ComputerName <String>] [-DisableOffline <Boolean>] [-DisablePFA <Boolean>]
 [-PersistMemoryOffline <Boolean>] [-PFAPageCount <UInt32>] [-PFAErrorThreshold <UInt32>]
 [-PFATimeout <UInt32>] [<CommonParameters>]
```

## DESCRIPTION
The **Set-WheaMemoryPolicy** cmdlet sets the elements of the WHEA (Windows Hardware Error Architecture) memory policy on the specified computer.

WHEA receives memory errors, corrected and uncorrected, from the platform and implements a Predictive Failure Analysis (PFA) algorithm based on corrected errors.
WHEA attempts to remove from the available system memory the pages that have uncorrected errors, or are predicted to fail based on corrected errors.
The removal decisions can be persisted across reboots.
You can change the WHEA decision criteria against memory errors by tuning the WHEA memory policy.
These policy elements can be set independently of each other.
The new policy element values take effect immediately.

WHEA memory policy elements are:

- DisableOffline. Disable decisions to take memory offline based on corrected or uncorrected errors.
- DisablePFA. Disable predictive failure analysis (PFA) of memory pages based on the number of corrected errors reported in the page.
- PersistMemoryOffline. Persist the decisions to take memory offline across reboots. This element applies to both corrected and uncorrected errors.
- PFAPageCount. The maximum number of memory pages that WHEA monitors using PFA.
- PFAErrorThreshold. The number of errors that need to occur within the timeout period for the page to be candidate for removal.
- PFATimeout. The number of seconds before PFA takes a page out of the monitoring list.

## EXAMPLES

### Example 1: Enable WHEA predictive failure analysis
```
PS C:\> Set-WheaMemoryPolicy -DisablePFA $False
```

This command enables predictive failure analysis on the local computer.

### Example 2: Change the memory time out policy on a remote computer
```
PS C:\> Set-WHEAMemoryPolicy -ComputerName "TestPC" -PFATimeout 600
```

This command changes the WHEA memory policy on the remote computer named TestPC to use a timeout of 600 seconds.

### Example 3: Get and set WHEA memory policy in a script
```
PS C:\> $X = Get-WheaMemoryPolicy
PS C:\> $X.DisableOffline = $True
PS C:\> $X | Set-WheaMemoryPolicy
```

This command gets the memory policy in the variable $X, sets the value of X. DisableOffline to True, and then uses $X to set the memory policy.

## PARAMETERS

### -ComputerName
Specifies the name of the remote computer from which to retrieve policy information.
If you do not specify a computer name, the command returns the policy of the local computer.
The alias for *ComputerName* is cn.

```yaml
Type: String
Parameter Sets: (All)
Aliases: CN

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableOffline
Disables WHEA from taking memory pages offline in response to corrected or uncorrected memory errors.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DisablePFA
Disables the predictive failure analysis algorithm and stops WHEA from monitoring memory pages that have corrected errors.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PFAErrorThreshold
Specifies the number of corrected errors that must occur before a memory page in the PFA monitoring list is considered bad and is taken offline.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PFAPageCount
Specifies the maximum size of the PFA monitoring list for pages that experience corrected memory errors.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PFATimeout
Specifies the number of seconds that WHEA monitors a memory page using PFA.
WHEA starts monitoring a memory page when the page has its first corrected error.
WHEA stops monitoring a memory page when one of the following events occurs:

- The monitoring interval exceeds the *PfaTimeout* value.

or

- The number of detected errors exceeds the *PfaErrorThreshold* value.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PersistMemoryOffline
Indicates whether to persist memory-offline decisions across computer reboots.

```yaml
Type: Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WheaMemoryPolicy](./Get-WheaMemoryPolicy.md)

