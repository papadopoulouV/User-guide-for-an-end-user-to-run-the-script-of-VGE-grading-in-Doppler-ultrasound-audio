# User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio

This repository provides a step-by-step guide for an end-user to grade a Doppler venous gas emboli (VGE) recording based on the deep learning model our team has previously developed [1]. Upon completing a successful run of the code, the end-user will be able to see the prediction of VGE grade for the recorded Doppler ultrasound audio in precordial and subclavian modes, separately.

**Important disclaimer**: We make no claim to the accuracy of this program beyond what we originally published [1]. Based on that publication, our expectation is that our model results in 84.9% and 90.4% average ordinal accuracy for precordial and subclavian VGE grades, respectively (with a weighted kappa coefficient of 0.61 and 0.67 that indicates substantial agreement similar to human inter-rater agreement for this type of data). For details on expected accuracy and performance, please refer to the full publication. By using this program as described herein, the user confirms their understanding that (1) this model was developed and tested on previously acquired data, (2) the development team may release new models with expected better performance in the future, and (3) a risk always remains that it may not generalize well to new data. The user accepts all risks and potential consequences of use including, but not limited to, inaccurate results. We welcome feedback on usability and accuracy – please email papadopoulou@unc.edu or aazarang@unc.edu. 
## 1)	Anaconda installation and code setup
Download the GitHub zip-file of the Doppler code from the link below:
https://github.com/papadopoulouV/User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio/archive/refs/heads/main.zip
and extract the file to your Desktop (or your desired location). An example of the code placement is shown below: 

<p align="center">
<img src="https://github.com/papadopoulouV/User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio/assets/38727593/ee050475-382f-40ae-b387-ad3388b819b8" width="800" align="center">
    <br>
    <em>Figure 1. Example of GitHub code placement in computer Desktop directory. </em>
</p>

Then, install Anaconda from the following website (the steps are straightforward): 
https://www.anaconda.com/download
Once the downloading and installation have been completed, open the software and install the built-in Jupyter Notebook as depicted below (please note that the window below is located under “Home” tab of Anaconda: 

<p align="center">
<img src="https://github.com/papadopoulouV/User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio/assets/38727593/9466d9e4-f5c5-4d28-b198-b6617c54b070" width="800" align="center">
    <br>
    <em>Figure 2. Installation of Jupyter Notebook inside the Anaconda software. </em>
</p>

After successful installation, click on “Launch” button to be directed to default Internet browser of your computer. From the opened window, go the location of GitHub code under your Desktop and open the Jupyter Notebook file (named as _“GitHub Repository for Doppler VGE Detection Inference.ipynb”_). An example of the step is shown below:

<p align="center">
<img src="https://github.com/papadopoulouV/User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio/assets/38727593/20a7022d-344f-4ddc-a7a9-d3a9ff10aff5" width="800" align="center">
    <br>
    <em>Figure 3. Running the VGE detection in Doppler code in Jupyter Notebook. </em>
</p>

## 2)	Setup data folders
To setup the data folders properly, please note that a different folder must be created for each type of data collection. To do this end, create a folder inside the folder created above (i.e., _“Code_to_run”_), name it _“Data Folder”_. Next, go inside the “Data Folder” and create two sub-folders, “Precordial” and “Subclavian”. Later, depending on the recorded data, a proper model for assessment will be selected for precordial and subclavian, respectively. An example of the steps above is shown below:

<p align="center">
<img src="https://github.com/papadopoulouV/User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio/assets/38727593/0371a69d-d0d7-4e6d-895f-72ff6df46ebe" width="800" align="center">
    <br>
    <em>Figure 4. An example of data folder setup. </em>
</p>

Within each folder listed above, place the corresponding recorded Doppler ultrasound audio files to be assessed. 
## 3)	Required Python package installation
To install the required packages, in your Anaconda environment under the “Environment” tab, click on “Open Terminal” (‘Environments’ → ‘Green circle button to the right of your environment name’ → ‘Open Terminal’). An example is shown below:

<p align="center">
<img src="https://github.com/papadopoulouV/User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio/assets/38727593/4b213a07-b971-45fe-9089-f67706824538" width="800" align="center">
    <br>
    <em>Figure 5. Open terminal for required package installation. </em>
</p>

From the opened command window, change the directory to the location of the Jupyter notebook code (i.e., ‘cd path-on-your-computer/Desktop/Code_to_run’): 

<p align="center">
<img src="https://github.com/papadopoulouV/User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio/assets/38727593/b51fb284-7574-4305-b5d3-1f7130aeac53" width="800" align="center">
    <br>
    <em>Figure 6. Changing the directory to the location of the code. </em>
</p>

Then, write the following command in the terminal:
pip install -r requirements.txt
This line of code installs all the required packages in the environment for running the code. This step might take a few minutes as some packages (depending on the Internet speed) are large in size and the installation is lengthy process. Once it is complete, there will be a successful installation message in the opened terminal. Please note that this step must be completed before going into the next step, otherwise, the VGE detection will fail. 
## 4)	Running the code
To run the code, click on the “Run All” button under the “Cell” tab current window of Jupyter Notebook. As example of this step is shown below: 
<p align="center">
<img src="https://github.com/papadopoulouV/User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio/assets/38727593/6fa133b2-f654-4009-8326-b9534146ed55" width="800" align="center">
    <br>
    <em>Figure 7. Execution of code in Jupyter Notebook. </em>
</p>

select your desired data folder to start: 
<p align="center">
<img src="https://github.com/papadopoulouV/User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio/assets/38727593/8e578449-e8fb-4a54-a533-e07a7a2047ac" width="800" align="center">
    <br>
    <em>Figure 8. Proper data folder selection. </em>
</p>

This step sets the path of the data folder permanently and whenever you want to make changes to your data folder, you need to re-do this step. Next, the code checks for the sampling rate of the recorded Doppler ultrasound audio files. If needed, it gets resampled to 8 kHz. Upon successful run of this step, you will see a similar message in output: 
<p align="center">
<img src="https://github.com/papadopoulouV/User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio/assets/38727593/e286fb7e-1e5c-4b41-ac0e-86acd3005726" width="800" align="center">
    <br>
    <em>Figure 9. Successful resampling step. </em>
</p>

After this step, the proper model should be selected to be applied on pre-processed Doppler ultrasound audio files. Depending on the selected data to process (Precordial or Subclavian), the proper model will be selected automatically. 
Upon applying the proper model, the results are displayed in two different modes: 
-	Majority voting on non-overlapping 10-second audio segments
-	Majority voting on overlapping 10-second audio segments (50% overlap)
These two modes are annotated in the code in two different sections.

