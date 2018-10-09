# AVT_presentation_code-screening

Code to run the participant screening part of the AVT fMRI study. 

Also contains the code used to generate trial sequences for this screening as well as the main fMRI experiment (see [AVT_presentation_code-fMRI](https://github.com/Remi-Gau/AVT_presentation_code-fMRI))

Originally run on windows Vista with Presentation (v18.1).


## Dependencies: 
- runs with the software [Presentation](https://www.neurobs.com/menu_presentation/menu_features/features_overview)
- requires the [palamedes toolbox v1.8.1](http://www.palamedestoolbox.org) for the analysis of the psychometric functions
- scripts with eyetracking require a proper Windows installation of the Tobii X120 eytetracker.


## Presentation files

### Test scripts
`StaticImage.sce` : present a static image to test the video projector.adn calibration scripts

`PiezoTest.sce` : brief test of the tactile stimulator.

`PiezoStimTarget.sce` : presents a tactile stimulus and targets.


### Experiment scripts

`EyeTrack_Calibration.sce` : quick routine to test and calibrate the eyetracker

`AudioLoc_PsyPhy.sce` : run the auditory localization task (+/- 5 degrees).

`AVT_PsyPhy.sce` : run the psychophysics task (method of constant stimuli : 0, +/-1, +/-3, +/-5, +/-8, +/-12 degrees)

`AVT_fMRI.sce` : main experiment (in case the eyetracker failed to work)

`AVT_fMRI_EyeTrack.sce` : main experiment with eyetracking


## Analysis scripts (matlab)

Example data is provided to run those scripts on.

`AnalyzeResultsBehavioral_A.m` : scritps to analyze the results of the auditory localization task.

`AnalyzeResultsBehavioral_AwithFB.m` : scritps to analyze the results of the auditory localization task with feedback.

`AnalyzeResultsBehavioral_PsyPhy_A.m` : scritps to analyze and plot the psychometric function of the psychophysics auditory localization task.

`FeedbackBehavioral_AVT_fMRI_training.m` and `FeedbackBehavioral_AVT_fMRI.m` : give feedbacks to the participant on his performance on the previous runs.


## Trial sequences generation scripts (matlab)

For the fMRI scripts you can also compute the efficiency of the most basic contrasts using Rik Henson's `fMRI_GLM_efficiency.m` function (available [here](https://github.com/MRC-CBU/riksneurotools)).

`TrialsRandomA.m`: creates trial sequence for the auditory localization task.

`TrialsRandomAVT_TargetPresentation.m`: creates a trial sequence to present targets to the participant.

`TrialsRandomPsyPhy.m`: creates a trial sequence for the psychophysics auditory localization task. 

`TrialsRandomAVT.m` and `TrialsRandomAVT_Training.m`: creates a trial sequence for the main fMRI experiment and its training counterpart ot the screening sessions.


## sounds folder

`sounds.zip` contains the sounds used for the screening as well as the main [fMRI experiment](https://github.com/Remi-Gau/AVT_presentation_code-fMRI).

`Create_VE_wavefile_MIT.m` will generate the sounds fron this experiment using the head related transfer functions extracted from the [MIT database](http://sound.media.mit.edu/resources/KEMAR.html) and stored in a .mat file in the `MIT_hrtf_database` folder