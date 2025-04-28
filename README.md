# bc
initial b with raiting and cancel threshold




```
sudo apt update
sudo apt-get update
sudo apt install gstreamer1.0-tools -y
sudo apt-get install gstreamer1.0-plugins-good -y
sudo apt-get install gstreamer1.0-plugins-bad -y
```

```
gst-launch-1.0 -vvv \
v4l2src device=/dev/video0 ! \
"video/x-raw,framerate=30/1,format=UYVY" ! \
v4l2h264enc extra-controls="controls,h264_profile=4,h264_level=13,video_bitrate=10000000;" ! \
"video/x-h264,profile=high,level=(string)4.2" ! \
h264parse ! \
queue ! \
matroskamux name=mux ! \
filesink location=output_high_bitrate.mkv
```
