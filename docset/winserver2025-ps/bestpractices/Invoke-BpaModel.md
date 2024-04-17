---
description: Use this topic to help manage Windows and Windows Server technologies with Windows PowerShell.
external help file: Microsoft.BestPractices.Cmdlets.dll-Help.xml
Module Name: BestPractices
ms.date: 12/27/2016
online version: https://learn.microsoft.com/powershell/module/bestpractices/invoke-bpamodel?view=windowsserver2025-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-BpaModel
---

# Invoke-BpaModel

## SYNOPSIS
Starts a BPA scan for a specific model that is installed on a computer.

## SYNTAX

### ModelParameterSet (Default)
```
Invoke-BpaModel [-ModelId] <String> [-RepositoryPath <String>] [-Mode <ScanMode>] [<CommonParameters>]
```

### SubModelParameterSet
```
Invoke-BpaModel [-ModelId] <String> [-RepositoryPath <String>] [-Mode <ScanMode>] [-SubModelId <String>]
 [-Context <String>] [-ComputerName <String[]>] [-CertificateThumbprint <String>] [-ConfigurationName <String>]
 [-Credential <PSCredential>] [-Authentication <AuthenticationMechanism>] [-Port <Int32>]
 [-ThrottleLimit <Int32>] [-UseSsl] [<CommonParameters>]
```

## DESCRIPTION
The **Invoke-BpaModel** cmdlet starts a Best Practices Analyzer (BPA) scan for a specific model that is installed on a Windows-based computer.
The model is specified either by using the *ModelId* parameter, or by piping the results of the **Get-BpaModel** cmdlet into this cmdlet.
If a model is specified in the cmdlet after the BPA scan has been performed, then the results of the scan are available as an XML file.

This cmdlet cannot be canceled after it has been started.

Single-node XML is not supported by the BPA model schema.
For more information about what is supported by the BPA model schema, see the [Microsoft Baseline Configuration Analyzer Model Authoring Guide](https://www.microsoft.com/download/details.aspx?id=16475) on the [Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=16475).

## EXAMPLES

### Example 1: Start a BPA scan for a specified model ID
```
PS C:\> Invoke-BPAModel -ModelId "ModelId1"
```

This example starts a BPA scan on the model that is represented by ModelId1.

The same task can be completed by running either of the following cmdlets.


`Invoke-BPAModel -Id "ModelId1"`

OR

`Invoke-BPAModel "ModelId1"`

### Example 2: Start a BPA scan using the pipeline
```
PS C:\> Get-BPAModel | Invoke-BPAModel
```

This example gets all BPA models that are installed on the computer, and then pipes the results of the **Get-BpaModel** cmdlet to this cmdlet to start a BPA scan on all models.

### Example 3: Start a BPA scan and save the results to a variable
```
PS C:\> $BPAObj = Invoke-BPAModel ModelId1


This cmdlet displays the results of any specific object in the previous cmdlet by calling the variable into which the results of the previous cmdlet were saved, and then specifying the object in the results that the administrator wants. The object is identified by its numerical order in the collection of results (the [CODE_Snippit]0[CODE_Snippit], or first, object). The cmdlet then identifies which field of the results in that object (for this example, the Detail field) the administrator wants to view. The cmdlet shown returns the properties of the Detail field from the first object in the results of the preceding line.
PS C:\> $BPAObj[0].Detail
ModelId             : ModelId1
Success             : True
ScanTime            : 10/21/2008 3:08:47 PM
InformationMessages : 5
WarningMessages     : 4
ErrorMessages       : 0
Description         :
```

This example starts a BPA scan on the model specified by ModelId1, and saves the results of the cmdlet as a variable, $BPAObj.

## PARAMETERS

### -Authentication
Specifies the authentication mode to use when creating a remote connection for running a remote BPA scan.
For more information, type `Get-Help Invoke-Command`.

```yaml
Type: AuthenticationMechanism
Parameter Sets: SubModelParameterSet
Aliases:
Accepted values: Default, Basic, Negotiate, NegotiateWithImplicitCredential, Credssp, Digest, Kerberos

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateThumbprint
Specifies the certificate thumbprint to use when creating a remote connection via SSL for running a remote BPA scan.
For more information, type `Get-Help Invoke-Command`.

```yaml
Type: String
Parameter Sets: SubModelParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputerName
Specifies the target computer against which to run the BPA scan.

```yaml
Type: String[]
Parameter Sets: SubModelParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationName
Specifies the session configuration, such as the name of the endpoint, to use when creating a session for a remote BPA scan.
For more information, type `Get-Help Invoke-Command`.

```yaml
Type: String
Parameter Sets: SubModelParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Context
Scans a submodel in the context of a specific model (one that is different from the parent model of the submodel).
For example, an administrator wants to run a scan on the Backend submodel of the SQL model, but only those in the context of a third model, a technology that relies upon SQL Server.

```yaml
Type: String
Parameter Sets: SubModelParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Specifies the credentials to use when creating a remote connection for running a remote BPA scan.
For more information, type `Get-Help Invoke-Command`.

```yaml
Type: PSCredential
Parameter Sets: SubModelParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mode
Specifies the mode to use when running the BPA scan.
The acceptable values for this parameter are: All, Analysis, or Discovery.

```yaml
Type: ScanMode
Parameter Sets: (All)
Aliases:
Accepted values: All, Discovery, Analysis

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ModelId
Identities the model to be used for the BPA scan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: Id, BestPracticesModelId

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Port
Specifies the port to use when creating a remote connection for running a remote BPA scan.
For more information, type `Get-Help Invoke-Command`.

```yaml
Type: Int32
Parameter Sets: SubModelParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RepositoryPath
Specifies that the default location for reports specified by the ReportsRoot registry key should be overridden.
This parameter specifies the path where the results should be stored.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubModelId
Identifies the submodel to run for the model specified by the *ModelId* parameter.
For example, the Update Services model (`Microsoft/Windows/UpdateServices`) has two submodels (`UpdateServices-DB`, `UpdateServices-Services`).

```yaml
Type: String
Parameter Sets: SubModelParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ThrottleLimit
Specifies the throttle limit to use when creating a remote connection for running a remote BPA scan.
For more information, type `Get-Help Invoke-Command`.

```yaml
Type: Int32
Parameter Sets: SubModelParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseSsl
Specifies whether or not to use SSL when creating a remote connection for running a remote BPA scan.
For more information, type `Get-Help Invoke-Command`.

```yaml
Type: SwitchParameter
Parameter Sets: SubModelParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
The input string specified by the *ModelId* parameter.

## OUTPUTS

### System.Collections.Generic.List<Microsoft.BestPractices.CoreInterface.InvokeBpaModelOutput>
The output object encapsulates the results of the cmdlet that is entered.
The output object contains information such as the BPA model ID, the success or failure of the cmdlet, and other details.

## NOTES

## RELATED LINKS

[Get-BpaModel](./Get-BpaModel.md)

[Get-BpaResult](./Get-BpaResult.md)

[Set-BpaResult](./Set-BpaResult.md)

