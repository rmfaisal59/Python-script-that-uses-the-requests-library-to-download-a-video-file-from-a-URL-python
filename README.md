# rmfaisal59.github.io
import requests

def download_video(url, filename):
    r = requests.get(url, stream=True)

    if r.status_code == 200:
        with open(filename, 'wb') as f:
            for chunk in r.iter_content(chunk_size=1024):
                if chunk:
                    f.write(chunk)
    else:
        print("Failed to download video. Status code: ", r.status_code)

# Usage
download_video('http://example.com/video.mp4', 'video.mp4')


pip install requests


Please note that this script will only work for URLs that point directly to a video file. If the video is hosted on a platform like YouTube, you'll need to use a more complex method or a dedicated library like youtube_dl, because these platforms usually do not provide direct URLs to video files.
