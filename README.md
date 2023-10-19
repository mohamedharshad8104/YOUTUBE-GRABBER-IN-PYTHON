# YOUTUBE-GRABBER-IN-PYTHON
Helps us to download YouTube videos in both video and audio formats.
# importing the module  
from pytube import YouTube  
# download location of the file  
DOWNLOAD_PATH = " C:/Users/USER/Desktop/"   
# link of the video to be downloaded  
link="https://youtu.be/oQdxL_WW3aE"  
try:  
    # creating youtube object using YouTube  
    youtube_obj = YouTube(link)  
except:  
    print("Connection Error") #to handle exception  
# filters out all the files with "mp4" extension  
mp4files = youtube_obj.streams.filter('mp4')  
#to set the name of the file  
youtube_obj.set_filename('Downloaded Video')  
# get the video with the extension and  
# resolution passed in the get() function  
d_video = youtube_obj.get(mp4files[-1].extension,mp4files[-1].resolution)  
try:  
    # downloading the video  
    d_video.download(DOWNLOAD_PATH)  
except:  
    print("The is Some Error!")  
print('Task is Completed!')  
