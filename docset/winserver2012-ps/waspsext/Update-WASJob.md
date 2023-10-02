---
external help file: WasPsExt_Cmdlets.xml
Module Name: WasPSExt
online version: https://learn.microsoft.com/powershell/module/waspsext/update-wasjob?view=windowsserver2012-ps&wt.mc_id=ps-gethelp
schema: 2.0.0
---

# Update-WASJob

## SYNOPSIS
Adds assets and assessments to a specified job.

## SYNTAX

### UNNAMED_PARAMETER_SET_1
```
Update-WASJob [-Job] <WASJob[]> -Assessment <WASAssessment[]>
```

### UNNAMED_PARAMETER_SET_2
```
Update-WASJob [-Job] <WASJob[]> [-Computer] <WASComputer[]> [[-Image] <WASImage>] [[-UnattendFile] <String>]
 [-CustomImage]
```

## DESCRIPTION
The **Update-WASJob** cmdlet is used to add assessments, computers, and images to the job object in memory.
After you add assets or assessments, you can invoke the job but you can't save it back to the Windows Assessment Services server.

The **AddAssessment** parameter set adds assessments.
The **AddAsset** parameter set adds computers, images, and unattended answer files.
However, you can't combine these two parameter sets on the same command line.

The **Job** parameter is required, and either the **Assessment** or the **Computer** parameter is also required.

## EXAMPLES

### Example 1:  Add assessments to a job and then run it
```
The first command gets the job and saves it as a variable. 
PS C:\> $job = Get-WASJob -JobName "Automated Job"

The second command gets the assessments and saves it as a variable.
PS C:\> $assessments = Get-WASAssessment -AssessmentName minifilter*

The third command adds the assessments to the job.
PS C:\> Update-WASJob -Job $job -Assessment $assessments

This command runs the job.
PS C:\> Invoke-WASJob -Job $job
```

### Example 2: Add computers to a job and then run it
```
The first command gets the job and saves it as a variable.
PS C:\> $job = Get-WASJob -JobName "Automated Job"

The second command gets the computers and saves the objects as a variable.
PS C:\> $computers = Get-WASComputer -ComputerName *toast

The third command tells Windows Assessment Services that no image deployment is necessary.
PS C:\> $job.ApplyImage = $false

The fourth command adds the computers to the job.
PS C:\> Update-WASJob -Job $job -Computer $computers

This command runs the job.
PS C:\> Invoke-WASJob -Job $job
```

### Example 3: Add computers and images to a job and then run it
```
The first command gets the job and saves it as a variable.
PS C:\> $job = Get-WASJob -JobName "Automated Job"

The second command gets the computers and saves the objects as a variable.
PS C:\> $computers = Get-WASComputer -ComputerName *toast

The third command gets the image and saves it as a variable.
PS C:\> $image = Get-WASImage -ImageName *Consumer*

The fourth command tells Windows Assessment Services to deploy the image to the computers.
PS C:\> $job.ApplyImage = $true

The fifth command adds the computers, and the image to the job.
PS C:\> Update-WASJob -Job $job -Computer $computers -Image $image

This command runs the job.
PS C:\> Invoke-WASJob -Job $job
```

## PARAMETERS

### -Assessment
Specifies a list of assessments to add the job.
The assessments that are added use the recommended settings.
If you create a custom assessment that does not include default assessment settings, the assessment could fail at run time.

To get a list of available assessments, use the **Get-WASAssessment** cmdlet.

```yaml
Type: WASAssessment[]
Parameter Sets: UNNAMED_PARAMETER_SET_1
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Computer
Specifies a list of computer objects to add to the job.
To get the computer object, use the **Get-WASComputer** cmdlet.

```yaml
Type: WASComputer[]
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CustomImage
Specifies that a predefined image is applied to the computers being added to the job.
This means that you use a deployment method other than Windows Assessment Services.
The job holds the computer until the image is deployed to the computers.

```yaml
Type: SwitchParameter
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Image
Specifies the image object to apply to the computers being added to the job.
This means that you use Windows Assessment Services for deployment.
To get the image object, use the **Get-WASImage** cmdlet.

```yaml
Type: WASImage
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Specifies the job to update.
This is a required parameter.
To get the job object, use the **Get-WASJob** cmdlet.
The job you update can't be saved to the Windows Assessment Services server.

```yaml
Type: WASJob[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -UnattendFile
Specifies the unattended answer file to use when deploying the image to the computer.
The string is the path to the unattend file stored in the /relax/unattendfiles share on the Windows Assessment Services server.

```yaml
Type: String
Parameter Sets: UNNAMED_PARAMETER_SET_2
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Windows Assessment Services Technical Reference](https://go.microsoft.com/fwlink/?LinkId=215628)

[Get-WASAssessment](./Get-WASAssessment.md)

[Get-WASComputer](./Get-WASComputer.md)

[Get-WASImage](./Get-WASImage.md)

[Get-WASJob](./Get-WASJob.md)

