## Installing Gamma 2020 Ubuntu

December 15, 2020, on Ubuntu 18.04. This readme is meant to work in combination with Gamma's 'INSTALL_Linux.html' file for linux installation.  Open INSTALL_linux.html. I will be following all instructions there. 

#### PSYCH!
GAMMA_SOFTWARE-20200713 is really only designed to work on Focal (20.04), not Bionic (18.04), because of the version of gdallib (gdallib26) that it expects. (But there's also a typo in the html so you would never know.)
In order for GAMMA_SOFTWARE-20200713 to work after the installation steps below, I needed to upgrade my machine to Focal (20.04). That fixed evereything - upgrading to 20.04 automatically replaced libgdal20 with libgdal26, I was done with installation.
To avoid issues, I would recommend moving to 20.04 before beginning and then just following the instructions here.   


#### 1. Expanding the Gamma Software package
1. I choose to install the software in /usr/local. I copy the tar into /usr/local, using sudo for permissions.
2. sudo -i for the two gunzip and tar commands in Section 1.1. Then I control+d to get out.
3. Set environment variables.  I open my .bashrc and add lines for GAMMA_HOME, ISP_HOME, ***MSP_HOME*** (the html doc is missing this one), DIFF_HOME, DISP_HOME, LAT_HOME, IPTA_HOME, GEO_HOME, PATH, OS, PYTHONPATH, HDF5_DISABLE_VERSION_CHECK
4. Set default raster format in the bashrc. I'm trying "BMP" for the moment. 

#### 2. Installing FFTW Libraries
1. sudo apt install libfftw3-3 libfftw3-dev libfftw3-single3

### 3. Install Gnuplot and GIMP programs
1. sudo apt install gnuplot gnuplot-data gimp
2. Test my installation by doing the steps in the html file (it works)

#### 4. Install the GDAL library
1. sudo apt install gdal-bin libgdal-dev ~~libgdal20~~ 
***libgdal26***

#### 5. Install the HDF5 library
1. sudo apt install libhdf5-dev libhdf5-100 (the html says sudo apt-y, but I think that's a typo)

#### 6. Install LAPACK and BLAS libraries
1. sudo apt install libblas-dev libblas3 libblas-doc liblapack-dev liblapack3 liblapack-doc. The result is I needed to remove libblas-doc from the string, because it apparently doesn't exist anymore. I installed all the other packages. 

#### 7. Test the installation
1. disras (and you should get output)
