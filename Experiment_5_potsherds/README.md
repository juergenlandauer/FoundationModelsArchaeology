# Automatic potsherd detection in drone (UAV) videos or orthophotos

This Jupyter Notebook can run on Google Colab (https://colab.google.com) and demonstrate the use of SAM 2.1 (Segment Anything Model) by Meta AI for the automated detection of potsherds in video or images (such as ortophotos).

The test data used here is a set of video frames from a drone video of a site in the Mediterranean. Available for download from  https://www.dropbox.com/scl/fi/u0htcr0kllnohu7hwsfox/DroneVideo.zip?rlkey=zxj171l892fgogi4mo8h5ej8e&st=33q8o1ka&dl=0


You can use your own data, too. Simply replace the ZIP file URL in the Notebook with the URL of your own ZIP file (e.g. stored in Google Drive or the like). The ZIP file must contain one or more images in its root folder. No sub-directories!

If you have no images but a video instead, you must extract a series of JPEG frames from this video first, for example by using ffmpeg (https://ffmpeg.org/) as follows:

    ffmpeg -i <your_video>.mp4 -q:v 2 -start_number 0 <output_dir>/'%05d.jpg'

where -q:v generates high-quality JPEG frames and -start_number 0 asks ffmpeg to start the JPEG file from 00000.jpg.

CAUTION: use -q:v with care and make sure your output data is not too big. The reason is that SAM is very resource intensive and processing might take a very long time. Several hours are not uncommon. Consider using a small sample first.

## Output: 
The file out.mp4 contains a sample of the output from the input frames mentioned above. It has been modified from the original input by cutting out a smaller part of the original video input for performance reasons. Also slow motion is applied for easier viewing.
