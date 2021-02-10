---
external help file: MSFT_NetQosPolicy.cdxml-help.xml
Module Name: NetQos
online version: 
schema: 2.0.0
title: Get-NetQosPolicy
description: 
keywords: powershell, cmdlet
author: Kateyanne
manager: jasgro
ms.date: 10/29/2017
ms.topic: reference
ms.prod: powershell
ms.assetid: 7E4D1383-2439-4F10-A86D-AA2BD4EC54E6
ms.author: v-kaunu
ms.reviewer: brianlic
---

# Get-NetQosPolicy

## SYNOPSIS
Retrieves network Quality of Service (QoS) policies.

## SYNTAX

```
Get-NetQosPolicy [[-Name] <String[]>] [-PolicyStore <String>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-NetQosPolicy** cmdlet allows users to retrieve Quality of Service (QoS) policies from a computer.
QoS policies can originate from many sources, such as from the administrator of a local computer, from a domain controller, or from applications that use the QoS Windows Management Instrumentation (WMI) APIs.
Therefore, the QoS policies are stored in different locations.
If the location as provided by the **PolicyStore** parameter is not specified, then this cmdlet retrieves all the policies stored on the local computer (localhost).

ActiveStore is a special location.
If ActiveStore is specified as the location, then the user will see all the effective QoS policies, regardless of where the QoS policies are stored.

## EXAMPLES

### EXAMPLE 1
```
PS C:\> Get-NetQoSPolicy
Name           : Backup 
Owner          : Group Policy (Machine) 
NetworkProfile : Domain 
Precedence     : 127 
IPProtocol     : Both 
IPDstPrefix    : 10.1.1.176/28 
DSCPValue      : 40 
 
Name               : ntttcp 1 
Owner              : Group Policy (Machine) 
NetworkProfile     : All 
Precedence         : 127 
AppPathName        : ntttcp.exe 
MinBandwidthWeight : 30 
 
Name           : SMB Policy 
Owner          : Group Policy (Machine) 
NetworkProfile : All 
Precedence     : 127 
Template       : SMB 
PriorityValue  : 3
```

This example gets a list of QoS policies stored on the local computer (localhost).

### EXAMPLE 2
```
PS C:\> Get-NetQosPolicy -PolicyStore ActiveStore
Name           : smb policy 
Owner          : Group Policy (Machine) 
NetworkProfile : All 
Precedence     : 127 
Template       : SMB 
PriorityValue  : 3 
                       
Name               : ntttcp 1 
Owner              : Group Policy (Machine) 
NetworkProfile     : All 
Precedence         : 127 
AppPathName        : ntttcp.exe 
MinBandwidthWeight : 30 
                       
Name           : backup 
Owner          : Group Policy (Machine) 
NetworkProfile : Domain 
Precedence     : 127 
IPProtocol     : Both 
DSCPValue      : 40 
                       
Name           : ftp 
Owner          : PowerShell / WMI 
NetworkProfile : All 
Precedence     : 127 
AppPathName    : ftp.exe 
ThrottleRate   : 1 MBytes/sec
```

This example gets a list of QoS policies currently effective on the computer.

### EXAMPLE 3
```
PS C:\> Get-NetQosPolicy -Name "SMB policy" | Format-List -Property *
User                         : 
AppPathName                  : 
Template                     : SMB 
NetDirectPort                : 0 
IPProtocol                   : None 
IPPort                       : 0 
IPSrcPrefix                  : 
IPSrcPortStart               : 0 
IPSrcPortEnd                 : 0 
IPDstPrefix                  : 
IPDstPortStart               : 0 
IPDstPortEnd                 : 0 
URI                          : 
URIRecursive                 : False 
PriorityValue                : 3 
DSCPValue                    : -1 
MinBandwidthWeight           : 0 
ThrottleRate                 : 0 
NetworkProfile               : All 
TemplateMatchCondition       : SMB 
UserMatchCondition           : 
AppPathNameMatchCondition    : 
NetDirectPortMatchCondition  : 0 
IPProtocolMatchCondition     : None 
IPPortMatchCondition         : 0 
IPSrcPrefixMatchCondition    : 
IPSrcPortStartMatchCondition : 0 
IPSrcPortEndMatchCondition   : 0 
IPDstPrefixMatchCondition    : 
IPDstPortStartMatchCondition : 0 
IPDstPortEndMatchCondition   : 0 
URIMatchCondition            : 
URIRecursiveMatchCondition   : False 
PriorityValue8021Action      : 3 
DSCPAction                   : -1 
MinBandwidthWeightAction     : 0 
ThrottleRateAction           : 0 
Caption                      : 
Description                  : 
ElementName                  : 
InstanceID                   : {382ACFAD-1E73-46BD-A0A0-64EE0E587B95}\SMB Policy 
Name                         : SMB Policy 
Owner                        : Group Policy (Machine) 
Precedence                   : 127 
Version                      : 2.0 
PSComputerName               : 
ComputerName                 : CHARLEY-MP1 
ClassName                    : MSFT_NetQosPolicySettingData 
Class                        : ROOT/StandardCimv2:MSFT_NetQosPolicySettingData 
CimClass                     : ROOT/StandardCimv2:MSFT_NetQosPolicySettingData 
Namespace                    : ROOT/StandardCimv2 
Properties                   : {Caption, Description, ElementName, InstanceID...} 
CimInstanceProperties        : {Caption, Description, ElementName, InstanceID...} 
CimSystemProperties          : Microsoft.Management.Infrastructure.CimSystemProperties
```

This example gets all of the properties of a specific QoS policy.
Some parameters on the left side of the output are actually aliases for real parameters.
For example, the `AppName` parameter is an alias for the **AppPathNameMatchCondition** parameter.

## PARAMETERS

### -AsJob
ps_cimcommon_asjob

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a New-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227967 or Get-CimSessionhttp://go.microsoft.com/fwlink/p/?LinkId=227966 cmdlet.
The default is the current session on the local computer.

```yaml
Type: CimSession[]
Parameter Sets: (All)
Aliases: Session

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Specifies the QoS policy name.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PolicyStore
Specifies the location of the policy that is stored.
The acceptable values for this parameter are:
                         
 - ActiveStore 
                         
 - COMPUTERNAME
                         
 - GPO:COMPUTERNAME
                         
 - GPO:DOMAIN\GPONAME
                         
 - LDAP://LDAP-URL

```yaml
Type: String
Parameter Sets: (All)
Aliases: store

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the maximum number of concurrent operations that can be established to run the cmdlet.
If this parameter is omitted or a value of `0` is entered, then Windows PowerShell® calculates an optimum throttle limit for the cmdlet based on the number of CIM cmdlets that are running on the computer.
The throttle limit applies only to the current cmdlet, not to the session or to the computer.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### None

## OUTPUTS

### Microsoft.Management.Infrastructure.CimInstance#ROOT/StandardCimv2/MSFT_NetQosPolicySettingData
The `Microsoft.Management.Infrastructure.CimInstance` object is a wrapper class that displays Windows Management Instrumentation (WMI) objects.
The path after the pound sign (`#`) provides the namespace and class name for the underlying WMI object.
                         
The MSFT_NetQosPolicySettingData object contains a QoS policy.

## NOTES

## RELATED LINKS

[Format-List](https://go.microsoft.com/fwlink/p/?LinkId=113302)

[New-NetQosPolicy](./New-NetQosPolicy.md)

[Remove-NetQosPolicy](./Remove-NetQosPolicy.md)

[Set-NetQosPolicy](./Set-NetQosPolicy.md)

