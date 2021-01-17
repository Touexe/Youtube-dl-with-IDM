# Youtube-dl-with-IDM
Download any video from supported sites by youtube-dl with IDM as downloader

# Requirements
 - Python 3.x
 - Internet Download Manager
 - youtube_dl
 - idm
 
# Installation
Install youtube_dl

```
pip install youtube_dl
```
install idm

```
pip install idm
```

Getting download url using youtube-dl

```
import youtube_dl

url = "" # The youtube video you want to download 
ydl_opts = {'format':'best'} 
            
def extractor(url):
    with youtube_dl.YoutubeDL(ydl_opts) as ydl:
            info_dict = ydl.extract_info(url, download=False)
    return info_dict

info = extractor(url)
title = info['title']
width = info['width']
height = info['height']
ext = info['ext']
download_url = info['url']
```

Downloading file Using IDM

```
from idm import IDMan

downloader = IDMan()
url = ""
destination_path = r"" # The folder path you want your downloading video to be saved

downloader.download(url,path_to_save = destination_path, output=None, referrer=None, cookie=None, postData=None, user=None, password=None, confirm = False, lflag = None, clip=False)
```

Using Youtube-dl with IDM

```
import youtube_dl
from idm import IDMan

url = "" # The youtube video you want to download 
downloader = IDMan()
destination_path = r"" # The folder path you want your downloading video to be saved

ydl_opts = {'format':'best'} # Choose the video format you want or using the best format available
            
def extractor(url):
    with youtube_dl.YoutubeDL(ydl_opts) as ydl:
            info_dict = ydl.extract_info(url, download=False)
    return info_dict

info = extractor(url)
title = info['title'] 
width = info['width']
height = info['height']
ext = info['ext']
download_url = info['url']

downloader.download(download_url,path_to_save = destination_path, output=f"{title}.{ext}", referrer= url, cookie=None, postData=None, user=None, password=None, confirm = False, lflag = None, clip=False)

```
