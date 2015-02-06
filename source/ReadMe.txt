	Implementation of Constrained Local Models 
		        for Face Alignment
                (OpenCV version)
---------------
Disclaimer
---------------
Like all source code that comes for free, this one
comes with no warranty, and by using the code, you 
acknowledge that the author does not claim responsibility 
for any damage related to using this code.

Optimization uses QuadProg++ by Luca Di Gaspero, released
under GNU license, you should observe the licence there.

TinyXML is used as XML parser.

That being said, I hope this code can be helpful.

I would appreciate if you cite my homepage: 
    http://sites.google.com/site/xgyanhome/home/projects/clm-implementation
if you think this code is helpful to you.

-------------------
How to run?
-------------------
1. Unzip files to any directory, say c:\clm_opencv

2. Download 'talking face video' image files, 'First 1000 images', 'Second 1000 images' ..., from http://www-prima.inrialpes.fr/FGnet/data/01-TalkingFace/talking_face.html
   Unzip images to one directory.

3. Set 'IMAGE_FILE_DIR' in OpenCV_CLM.cpp to your image directory.

4. Open 'OpenCV_CLM.sln', compile and run.

Note: 
    1. This code uses OpenMP to speed up SVM search. If you don't have OpenMP, just comment out the corresponding functions, it will not affect the result.
    2. OpenCV version of CLM only implements CLM search. Models are XML files, generated from Matlab CLM implementation.
    
-------------------------
Something to play with?
-------------------------
'CLM_OPTM_ERROR_WEIGHT' in CLM.h is the weight of shape constraints used in CLM optimization. You can try modify this value and observe the difference it makes on results.

--------------------------------
More technical details?
--------------------------------
Check out my homepage at google:
    http://sites.google.com/site/xgyanhome/home/projects/clm-implementation
There is a tutorial on CLM that explains the algorithm in detail.
    


--------------------------------------------------------------------------------
                                                            Xiaoguang Yan
                                                        xiaoguang.yan@gmail.com
                                                            
                                                            June 11, 2011.