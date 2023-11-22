# User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio

This repository provides a step-by-step guide for an end-user to grade a Doppler venous gas emboli (VGE) recording based on the deep learning model our team has previously developed [1]. Upon completing a successful run of the code, the end-user will be able to see the prediction of VGE grade for the recorded Doppler ultrasound audio in precordial and subclavian modes, separately.

**Important disclaimer**: We make no claim to the accuracy of this program beyond what we originally published [1]. Based on that publication, our expectation is that our model results in 84.9% and 90.4% average ordinal accuracy for precordial and subclavian VGE grades, respectively (with a weighted kappa coefficient of 0.61 and 0.67 that indicates substantial agreement similar to human inter-rater agreement for this type of data). For details on expected accuracy and performance, please refer to the full publication. By using this program as described herein, the user confirms their understanding that (1) this model was developed and tested on previously acquired data, (2) the development team may release new models with expected better performance in the future, and (3) a risk always remains that it may not generalize well to new data. The user accepts all risks and potential consequences of use including, but not limited to, inaccurate results. We welcome feedback on usability and accuracy – please email papadopoulou@unc.edu or aazarang@unc.edu. 
## 1)	Anaconda installation and code setup
Download the GitHub zip-file of the Doppler code from the link below:

https://github.com/papadopoulouV/User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio/archive/refs/heads/main.zip

and extract the file to your Desktop (or your desired location). An example of the code placement is shown below: 

<p align="center">
<img src="https://github.com/papadopoulouV/User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio/assets/38727593/681dd6e9-5f5b-4283-ae2a-886303948004" width="800" align="center">
    <br>
    <em>Figure 1. Example of GitHub code placement in computer Desktop directory. </em>
</p>

Then, install Anaconda from the following website (the steps are straightforward): 

https://www.anaconda.com/download

Once the downloading and installation have been completed, open the software and install the built-in Jupyter Notebook as depicted below (please note that the window below is located under “Home” tab of Anaconda: 

<p align="center">
<img src="https://github.com/papadopoulouV/User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio/assets/38727593/27dbe842-80d2-4b92-9e99-b20aa864a270" width="800" align="center">
    <br>
    <em>Figure 2. Installation of Jupyter Notebook inside the Anaconda software. </em>
</p>

After successful installation, click on “Launch” button to be directed to default Internet browser of your computer. From the opened window, go the location of GitHub code under your Desktop and open the Jupyter Notebook file (named as _“UNC_Doppler_Grader.ipynb”_). An example of the step is shown below:

<p align="center">
<img src="https://github.com/papadopoulouV/User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio/assets/38727593/e07d3f24-d25b-46c2-aa0a-47d66c9cbc4e" width="800" align="center">
    <br>
    <em>Figure 3. Running the VGE detection in Doppler code in Jupyter Notebook. </em>
</p>

## 2)	Setup data folders
To setup the data folders properly, please note that a different folder must be created for each type of data collection. To do this end, create a folder inside the folder created above (i.e., _“Code_to_run”_), name it _“Data Folder”_. Next, go inside the “Data Folder” and create two sub-folders, “Precordial” and “Subclavian”. Later, depending on the recorded data, a proper model for assessment will be selected for precordial and subclavian, respectively. An example of the steps above is shown below:

<p align="center">
<img src="https://github.com/papadopoulouV/User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio/assets/38727593/b1008b64-6b47-4473-85c7-1d873944574b" width="800" align="center">
    <br>
    <em>Figure 4. An example of data folder setup. </em>
</p>

Within each folder listed above, place the corresponding recorded Doppler ultrasound audio files to be assessed. The user must create a third folder under _“Data Folder”_ and name it _"Models"_. The available models in this repository, i.e., **"RAW_PRECORDIAL.h5"** and **"RAW_SUBCLAVIAN.h5"** should be placed in this folder.
## 3)	Required Python package installation
To install the required packages, in your Anaconda environment under the “Environment” tab, click on “Open Terminal” (‘Environments’ → ‘Green circle button to the right of your environment name’ → ‘Open Terminal’). An example is shown below:

<p align="center">
<img src="https://github.com/papadopoulouV/User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio/assets/38727593/01feb94a-3a96-4022-aec4-03d0dffe71b8" width="800" align="center">
    <br>
    <em>Figure 5. Open terminal for required package installation. </em>
</p>

From the opened command window, change the directory to the location of the Jupyter notebook code (i.e., ‘cd path-on-your-computer/Desktop/Code_to_run’): 

<p align="center">
<img src="https://github.com/papadopoulouV/User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio/assets/38727593/5ffd7583-7ce0-4366-a6c9-1dfbfb326bca" width="800" align="center">
    <br>
    <em>Figure 6. Changing the directory to the location of the code. </em>
</p>

Then, write the following command in the terminal:
pip install -r requirements.txt
This line of code installs all the required packages in the environment for running the code. This step might take a few minutes as some packages (depending on the Internet speed) are large in size and the installation is lengthy process. Once it is complete, there will be a successful installation message in the opened terminal. Please note that this step must be completed before going into the next step, otherwise, the VGE detection will fail. 
## 4)	Running the code
To run the code, click on the “Run All” button under the “Cell” tab current window of Jupyter Notebook. As example of this step is shown below: 
<p align="center">
<img src="https://github.com/papadopoulouV/User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio/assets/38727593/adfbf093-d3cd-4934-91c8-53f7a62f75c5" width="800" align="center">
    <br>
    <em>Figure 7. Execution of code in Jupyter Notebook. </em>
</p>

Select your desired data folder to start: 
<p align="center">
<img src="https://github.com/papadopoulouV/User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio/assets/38727593/9c8c37fe-29e7-4384-83cf-1dc37b5bbc77" width="800" align="center">
    <br>
    <em>Figure 8. Proper data folder selection. </em>
</p>

This step sets the path of the data folder permanently and whenever you want to make changes to your data folder, you need to re-do this step. Next, the code checks for the sampling rate of the recorded Doppler ultrasound audio files. If needed, it gets resampled to 8 kHz. Upon successful run of this step, you will see a similar message in output: 
<p align="center">
<img src="https://github.com/papadopoulouV/User-guide-for-an-end-user-to-run-the-script-of-VGE-grading-in-Doppler-ultrasound-audio/assets/38727593/8156d6e0-6ea2-41f2-8ad0-8bed6cd18651" width="800" align="center">
    <br>
    <em>Figure 9. Successful resampling step. </em>
</p>

After this step, the proper model should be selected to be applied on pre-processed Doppler ultrasound audio files. Depending on the selected data to process (Precordial or Subclavian), the proper model will be selected automatically. 
Upon applying the proper model, the results are displayed in two different modes: 
-	Majority voting on non-overlapping 10-second audio segments
-	Majority voting on overlapping 10-second audio segments (50% overlap)

These two modes are annotated in the code in two different sections.

## Synthetic Doppler Dataset

https://datadryad.org/stash/dataset/doi:10.5061/dryad.xgxd254kp

## License 
The codes are licensed under GPL-2.0 license.

## References 
[1] Azarang, A., Le, D.Q., Hoang, A., Blogg, L.S., Dayton, P.A., Lance, R.M., Natoli, M., Gatrell, A., Tillmans, F., Moon, R.E. and Lindholm, P., 2022. Deep Learning-Based Venous Gas Emboli Grade Classification in Doppler Ultrasound Audio Recordings. IEEE Transactions on Biomedical Engineering.


