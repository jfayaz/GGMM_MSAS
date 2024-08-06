# **MAINSHOCK-AFTERSHOCK GENERALIZED GROUND MOTION MODEL (MSAS GGMM)**

This tool, named as Generalized Ground Motion Model for Mainshocks and Aftershocks (MSAS_GGMM), uses a hybrid Recurrent Neural Network (RNN) framework to estimate a 30×1 cross -dependent vectors for mainshocks and aftershocks (denoted as IMMS and IMAS) of RotD50 Spectral Acceleration (RotD50S_a) at 25 periods and geometric means of Arias Intensity (I_(a_geom )), Significant Duration (D_(〖5-95〗_geom )), Peak Ground Acceleration, (〖PGA〗_geom) and Peak Ground Velocity (〖PGV〗_geom) using a set of seismic source and site parameters as inputs. The source and site inputs to the RNN framework include a vector of 8 values including source fault slab mechanism (F), magnitude for mainshock (M_MS), magnitude for aftershock (M_AS), closest rupture distance of mainshock rupture (R_(rup,MS)), closest rupture distance of aftershock rupture (R_(rup,AS)), hypocentral depth of mainshock (Z_(hyp,MS)), hypocentral depth of aftershock (Z_(hyp,AS)), and site’s soil shear-wave velocity (V_s30). Hence, given the source and site parameters, this tool returns a median prediction of the IM and estimated uncertainty bands (±σ). The executable is developed by Jawad Fayaz (Jawad Fayaz (jfayaz.github.io)) and collaborator (Carmine Galasso). For further details please read the article mentioned in the “Reference”. Though the tool is based on the Fayaz and Carmine (2022) study, the model has been updated with more data from Chile and Japan. 

Download the application from the following Dropbox link

    https://www.dropbox.com/scl/fo/i3wwzw1tv2i9vj6tuwdjg/ABAaycbVDwTT3yUwAWIDl3E?rlkey=ktichpcsrpwuvfllu0zizuxmb&dl=0

1. 	**GGMM Inputs**

   	Fault Mechanism (F)

   	      Fault Mechanism (F)	Value
          Crustal	1
          Interface	2
          Intraslab	3
	
   Magnitudes of Mainshock and Aftershock (M): 3≤M_w≤9

   Closest Rupture Distance (Rrup) of Mainshock and Aftershock in kilometers: 0.01≤R_rup≤250 km
	
   Depth of Hypocenter (Zhyp) of Mainshock and Aftershock in kilometers: 0≤Z_hyp≤100 km
	
   Site’s Shear-Wave Velocity (Vs30) in meters per second (m/s): 0≤V_s30≤1800 m/s
	
   Name of Output Folder that the user wants the outputs to be located (OutputFolderName)

   
2	**Calling MSAS_GGMM**

The tool package consists of the executable application “MSAS_GGMM.exe” which can be easily called from any command line or programming language/software. An example to run the GGMM program is given below where the inputs can be in any order with the input tags. The generalized syntax to run the executable is as follows:

    MSAS_GGMM.exe --F --MagMS –MagAS --RrupMS --RrupAS --ZhypMS --ZhypAS --Vs30 --OutputFolder

Here is an example to run the program.

    MSAS_GGMM.exe --F 1 --MagMS 7.5 --MagAS 6.5 --RrupMS 20 --RrupAS 25 --ZhypMS 10 --ZhypAS 8 --Vs30 300 --OutputFolder Results 


3 	**MSAS_GGMM Outputs**

The tool creates a folder named as inputted by the user in the OutputFolderName (as described) within the current directory of the tool

The outputs consist of four files: 1) “GGMM_MS.out” file containing the estimated median IM predictions and its uncertainty bands for mainshock, 2) “GGMM_AS.out” file containing the estimated median IM predictions and its uncertainty bands for aftershock, 3) “User_Inputs.txt” containing the record of the inputs as entered by the user, and 4) “GGMM.jpg” file showing the median and sigma bands of the estimated intensity measures in IM vectors for both mainshock (blue) and aftershock (green). 


Reference

    Jawad Fayaz and Carmine Galasso (2022). "A Generalized Ground Motion Model for Consistent Mainshock-Aftershock Intensity Measures using Successive Recurrent Neural Networks". Bulletin of Earthquake Engineering, https://link.springer.com/article/10.1007/s10518-022-01432-w

