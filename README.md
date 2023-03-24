
# Lafeef System
### yolov7 + SORT + Optical Flow : Track the object direction
In order to user this application localy

```bash
pip install -r requirements.txt
python manage.py makemigrations
python manage.py migrate
python manage.py runserver
```

## Detected video not playing by web browser

### Solution
Most of the browsers are support H264 encodec video for this we use `ffmpeg-python` 


##### After detection use ffmpeg package to encode video into `H264`

```bash
pip install ffmpeg-python
sudo apt-get update
sudo apt-get install ffmpeg
```
After this call the detect() funtion by passing the arrgument h264=true
`detect(source, h264=True)` at line 38 in video/views.py

##### Accuracy
At line 38 in video/views.py assign `bbox` or `centroid` to track_points flag
