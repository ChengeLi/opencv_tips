### install cv:
```
conda install -c https://conda.binstar.org/jjhelmus opencv
Fetching package metadata: ...
Solving package specifications: .............
Package plan for installation in environment /Users/Chenge/anaconda:

The following packages will be downloaded:

    package                    |            build
    ---------------------------|-----------------
    conda-3.10.0               |           py27_0         164 KB
    conda-env-2.1.3            |           py27_0          15 KB
    numpy-1.9.2                |           py27_0         2.9 MB
    opencv-2.4.10              |       np19py27_0         8.4 MB
    openssl-1.0.1k             |                1         2.5 MB
    python-2.7.9               |                1        11.3 MB
    requests-2.6.0             |           py27_0         594 KB
    sqlite-3.8.4.1             |                1         824 KB
    tk-8.5.18                  |                0         1.9 MB
    zlib-1.2.8                 |                0          83 KB
    ------------------------------------------------------------
                                           Total:        28.6 MB

The following NEW packages will be INSTALLED:

    conda-env: 2.1.3-py27_0     
    opencv:    2.4.10-np19py27_0

The following packages will be UPDATED:

    conda:     3.7.0-py27_0 --> 3.10.0-py27_0    
    numpy:     1.9.0-py27_0 --> 1.9.2-py27_0     
    openssl:   1.0.1h-1     --> 1.0.1k-1         
    python:    2.7.8-1      --> 2.7.9-1          
    requests:  2.4.1-py27_0 --> 2.6.0-py27_0     
    sqlite:    3.8.4.1-0    --> 3.8.4.1-1        
    tk:        8.5.15-0     --> 8.5.18-0         
    zlib:      1.2.7-1      --> 1.2.8-0          

Proceed ([y]/n)? y

Fetching packages ...
conda-3.10.0-p 100% |###############################################################################| Time: 0:00:00 776.08 kB/s
conda-env-2.1. 100% |###############################################################################| Time: 0:00:00 358.68 kB/s
numpy-1.9.2-py 100% |###############################################################################| Time: 0:00:03 840.82 kB/s
opencv-2.4.10- 100% |###############################################################################| Time: 0:00:09 911.17 kB/s
openssl-1.0.1k 100% |###############################################################################| Time: 0:00:02 869.23 kB/s
python-2.7.9-1 100% |###############################################################################| Time: 0:00:14 823.66 kB/s
requests-2.6.0 100% |###############################################################################| Time: 0:00:00 693.23 kB/s
sqlite-3.8.4.1 100% |###############################################################################| Time: 0:00:01 721.20 kB/s
tk-8.5.18-0.ta 100% |###############################################################################| Time: 0:00:02 981.19 kB/s
zlib-1.2.8-0.t 100% |###############################################################################| Time: 0:00:00 768.74 kB/s
Extracting packages ...
[      COMPLETE      ] |#################################################################################################| 100%
Unlinking packages ...
[      COMPLETE      ] |#################################################################################################| 100%
Linking packages ...
[      COMPLETE      ] |#################################################################################################| 100%
172-16-26-247:pkgs Chenge$ 

```

###1
no cv2.so in the site-packages folder, 
still segmentation error even inside this folder


### 2
linked the conda cv to site-packages still not OK:  

```

ln -s /Users/Chenge/anaconda/pkgs/opencv-2.4.10-np19py27_0/lib/python2.7/site-packages/cv.py cv.py
ln -s /Users/Chenge/anaconda/pkgs/opencv-2.4.10-np19py27_0/lib/python2.7/site-packages/cv2.so cv2.so

```

###3
 LINK to the homebrew version
 
 ```
 **firstly delted all 3 cv files:
  sudo rm cv.pyc ...**
 
 cd /Users/Chenge/anaconda/lib/python2.7/site-packages/ln -s /usr/local/Cellar/opencv/2.4.10.1/lib/python2.7/site-packages/cv.py cv.pyln -s /usr/local/Cellar/opencv/2.4.10.1/lib/python2.7/site-packages/cv2.so cv2.so
```
This cv2.so looks like:  
  


```  cv2.so:
	/usr/local/lib/python2.7/site-packages/cv2.so (compatibility version 0.0.0, current version 0.0.0)
	/usr/local/Frameworks/Python.framework/Versions/2.7/Python (compatibility version 2.7.0, current version 2.7.0)
	/usr/local/Cellar/opencv/2.4.10.1/lib/libopencv_contrib.2.4.dylib (compatibility version 2.4.0, current version 2.4.10)
	/usr/local/Cellar/opencv/2.4.10.1/lib/libopencv_nonfree.2.4.dylib (compatibility version 2.4.0, current version 2.4.10)
	/usr/local/Cellar/opencv/2.4.10.1/lib/libopencv_gpu.2.4.dylib (compatibility version 2.4.0, current version 2.4.10)
	/usr/local/Cellar/opencv/2.4.10.1/lib/libopencv_legacy.2.4.dylib (compatibility version 2.4.0, current version 2.4.10)
	/usr/local/Cellar/opencv/2.4.10.1/lib/libopencv_photo.2.4.dylib (compatibility version 2.4.0, current version 2.4.10)
	/usr/local/Cellar/opencv/2.4.10.1/lib/libopencv_ocl.2.4.dylib (compatibility version 2.4.0, current version 2.4.10)
	/usr/local/Cellar/opencv/2.4.10.1/lib/libopencv_calib3d.2.4.dylib (compatibility version 2.4.0, current version 2.4.10)
	/usr/local/Cellar/opencv/2.4.10.1/lib/libopencv_features2d.2.4.dylib (compatibility version 2.4.0, current version 2.4.10)
	/usr/local/Cellar/opencv/2.4.10.1/lib/libopencv_flann.2.4.dylib (compatibility version 2.4.0, current version 2.4.10)
	/usr/local/Cellar/opencv/2.4.10.1/lib/libopencv_ml.2.4.dylib (compatibility version 2.4.0, current version 2.4.10)
	/usr/local/Cellar/opencv/2.4.10.1/lib/libopencv_video.2.4.dylib (compatibility version 2.4.0, current version 2.4.10)
	/usr/local/Cellar/opencv/2.4.10.1/lib/libopencv_objdetect.2.4.dylib (compatibility version 2.4.0, current version 2.4.10)
	/usr/local/Cellar/opencv/2.4.10.1/lib/libopencv_highgui.2.4.dylib (compatibility version 2.4.0, current version 2.4.10)
	/usr/local/Cellar/opencv/2.4.10.1/lib/libopencv_imgproc.2.4.dylib (compatibility version 2.4.0, current version 2.4.10)
	/usr/local/Cellar/opencv/2.4.10.1/lib/libopencv_core.2.4.dylib (compatibility version 2.4.0, current version 2.4.10)
	/usr/lib/libc++.1.dylib (compatibility version 1.0.0, current version 120.0.0)
	/usr/lib/libSystem.B.dylib (compatibility version 1.0.0, current version 1213.0.0)
```

### change the first line in this file

notice the first line in this file is not dylib file..??
It's 
/usr/local/Frameworks/Python.framework/Versions/2.7/Python (compatibility version 2.7.0, current version 2.7.0)
	to avoid overwritten, delete the linked 3 files, copy and paste these same two files from cellar
but there's no cv.pyc now pyc just automatically appears after changing the first line!!now is working!!!!
OK... still not OK if out of the folder
### delete all 3 files and linking them. overwrite the original file

after linking the 2 files, the pyc doesn't appear 

**change the first line!!**

changed! still no pyc
after run python>> pyc appears!


but only work inside the folder, still can't work outside folder.



## uninstall conda opencv, these 3 files disappered!

but there are still opencv packages inside the pkgs file!!!




### relink the homebrew version 
still _in OK, out NO_


## delete all the opencv file from conda pkgs folder!
come back the site-pakages folder, these 3 files are linked with homebrewed version now, and opencv is working both inside and outside the folder now!!! yeah!!!



