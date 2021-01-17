# Youtube-dl-with-IDM

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
ydl_opts = {'outtmpl':'%(id)s.%(ext)s',
            'format':'best'} 
            
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

Downloading Using IDM

```
from idm import IDMan

downloader = IDMan()
url = ""
destination_path = r"c:\DOWNLOADS"

downloader.download(url,destination_path, output=None, referrer=None, cookie=None, postData=None, user=None, password=None, confirm = False, lflag = None, clip=False)
```
