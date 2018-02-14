---
ms.mktglfcycl: manage
ms.sitesec: library
ms.author: brianlic
author: brianlic-msft
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: ServerManagerTasks.cdxml-help.xml
keywords: powershell, cmdlet
manager: alanth
ms.date: 12/20/2016
ms.prod: w10
ms.technology: powershell-windows
ms.topic: reference
online version: 
schema: 2.0.0
title: Get-SMServerBpaResult
ms.assetid: CF4ACB47-4167-415D-85FF-D2D107539188
---

# Get-SMServerBpaResult

## SYNOPSIS
Gets the results of BPA scans.

## SYNTAX

```
Get-SMServerBpaResult -BpaXPath <String[]> [-BatchSize <UInt32>] [-CimSession <CimSession[]>]
 [-ThrottleLimit <Int32>] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
The **Get-SMServerBpaResult** cmdlet retrieves raw XML results of Best Practices Analyzer (BPA) scans on server roles, role services, or features, for one or more specified XPaths.
To get BPA scan results, we recommend that you run the [Get-BpaResult](http://technet.microsoft.com/library/hh868083.aspx) cmdlet instead of this cmdlet.

## EXAMPLES

### Example 1: Get BPA scan results, as raw XML, for a scan on Hyper-V
```
PS C:\>Get-SmServerBpaResult -BpaXPath 'Microsoft/Windows/Hyper-V:$reports$\*\Result.xml:/$ResultDatabase$/$Result$' | Format-List
BpaXPath       : Microsoft/Windows/Hyper-V:$reports$\*\Result.xml:/$ResultDatabase$/$Result$
Values         : {<Result ResultNumber="1" ResultId="3656124781" ModelId="Microsoft/Windows/Hyper-V" SubModelId=""
                 ComputerName="SERVER_01" Context="" Source="SERVER_01">
                     <Severity>Information</Severity>
                     <NeutralSeverity>Info</NeutralSeverity>
                     <Category>Configuration</Category>
                     <NeutralCategory>Configuration</NeutralCategory>
                     <Title>The Hyper-V Virtual Machine Management Service should be configured to start
                 automatically</Title>
                     <Compliance>The Hyper-V Best Practices Analyzer scan has determined that you are in compliance
                 with this best practice.</Compliance>
                     <SchemaContext>/dp0:schema/dp0:pattern[3]/dp0:rule/dp0:report</SchemaContext>
                 </Result>, <Result ResultNumber="2" ResultId="182728195" ModelId="Microsoft/Windows/Hyper-V"
                 SubModelId="" ComputerName="SERVER_01" Context="" Source="SERVER_01">
                     <Severity>Information</Severity>
                     <NeutralSeverity>Info</NeutralSeverity>
                     <Category>Configuration</Category>
                     <NeutralCategory>Configuration</NeutralCategory>
                     <Title>Hyper-V should be the only enabled role</Title>
                     <Compliance>The Hyper-V Best Practices Analyzer scan has determined that you are in compliance
                 with this best practice.</Compliance>
                     <SchemaContext>/dp0:schema/dp0:pattern[4]/dp0:rule/dp0:report</SchemaContext>
                 </Result>, <Result ResultNumber="3" ResultId="1932770375" ModelId="Microsoft/Windows/Hyper-V"
                 SubModelId="" ComputerName="SERVER_01" Context="" Source="SERVER_01">
                     <Severity>Warning</Severity>
                     <NeutralSeverity>Warning</NeutralSeverity>
                     <Category>Configuration</Category>
                     <NeutralCategory>Configuration</NeutralCategory>
                     <Title>The Server Core installation option is recommended for servers running Hyper-V</Title>
                     <Problem>This server is running a full installation instead of a Server Core
                 installation.</Problem>
                     <Impact>Running a full installation exposes a larger attack surface and may require more
                 maintenance, such as installing updates.</Impact>
                     <Resolution>Reconfigure the server to run a Server Core installation by using Server Manager to
                 remove the features under the User Interfaces and Infrastructure category.</Resolution>
                     <Help>http://go.microsoft.com/fwlink/?LinkId=227981</Help>
                     <SchemaContext>/dp0:schema/dp0:pattern[5]/dp0:rule/dp0:assert</SchemaContext>
                 </Result>, <Result ResultNumber="4" ResultId="1941517451" ModelId="Microsoft/Windows/Hyper-V"
                 SubModelId="" ComputerName="SERVER_01" Context="" Source="SERVER_01">
                     <Severity>Information</Severity>
                     <NeutralSeverity>Info</NeutralSeverity>
                     <Category>Configuration</Category>
                     <NeutralCategory>Configuration</NeutralCategory>
                     <Title>Domain membership is recommended for servers running Hyper-V</Title>
                     <Compliance>The Hyper-V Best Practices Analyzer scan has determined that you are in compliance
                 with this best practice.</Compliance>
                     <SchemaContext>/dp0:schema/dp0:pattern[6]/dp0:rule/dp0:report</SchemaContext>
                 </Result>...}
PSComputerName :
```

This command gets the raw XML results of a BPA scan that was run on the Hyper-V role.
Before you can run this command, run a BPA scan on the role, or verify that there are existing BPA scan results.
For a better view of the command results, pipe the command to the [Format-List](http://technet.microsoft.com/library/hh849957.aspx) cmdlet, another **Format-*** cmdlet, or to a file by using [Out-File](http://technet.microsoft.com/library/hh849882.aspx).

### Example 2: Get BPA scan results for File Services, and pipe them to a text file
```
PS C:\>Get-SmServerBpaResult -BpaXPath 'Microsoft/Windows/FileServices:$reports$\*\Result.xml:/$ResultDatabase$/$Result$' | Format-List | Out-File -FilePath C:\Users\SashaD\Desktop\FSResults.txt
```

This command gets the raw XML results of a BPA scan that was run on the File Services role, and pipes those results to a plain text file.

## PARAMETERS

### -AsJob
Runs the cmdlet as a background job. Use this parameter to run commands that take a long time to complete.

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

### -BatchSize
Specifies the batch size, or number of result entries, that you want displayed in command results.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BpaXPath
Specifies one or more BPA XPaths where BPA scan results are available.
Specify the BPA XPath in the following format: BpaModelId:BpaFilepath:BpaXPath.

To get the names for BPA models that are installed on the target server, run the cmdlet [Get-BpaModel](http://technet.microsoft.com/library/hh868082.aspx).
There is no file path available for results for a BPA model on a server until at least one set of scan results is available; that is, at least one scan has been run on the role or feature that is represented by the model.
For best results, and to avoid errors, enclose the value of this parameter in single quotation marks.
The following is a sample *BpaXPath* parameter value for results from a BPA scan on Hyper-V.

'Microsoft/Windows/Hyper-V:$reports$\*\Result.xml:/$ResultDatabase$/$Result$'

```yaml
Type: String[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CimSession
Runs the cmdlet in a remote session or on a remote computer.
Enter a computer name or a session object, such as the output of a [New-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227967) or [Get-CimSession](http://go.microsoft.com/fwlink/p/?LinkId=227966) cmdlet.
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
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

