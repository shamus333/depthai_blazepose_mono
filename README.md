# Blazepose tracking with DepthAI In MonoCamera

Reference from: [depthai_blazepose](https://github.com/geaxgx/depthai_blazepose)

The purpose of the code is to use the mono camera as the input source of the blazepose algorithm, and the color camera as a virtual camera for other applications.

The source code is from the above link.For academic exchange only
<p align="center"> <img src="C:\Users\Shamus33\Desktop\效果图.png" alst="Demo"></p>


## Pipeline
<p align="center"> <img src="C:\Users\Shamus33\Desktop\pipeline.png" alst="Demo"></p>

## Install


Install the python packages (depthai, opencv, open3d) with the following command:

Notice: UVC Camera Setting Reference from: [OAK as a webcam](https://docs.luxonis.com/en/latest/pages/oak_webcam/)
If you can't use the color camera for the time being, you can comment it out in the code and run it again
```
python3 -m pip install -r requirements.txt
```

## Run

**Usage:**

```
python3 demo.py -e --lm_m lite      # Purpose: to obtain the fastest FPS
```
```
-> python3 demo.py -h
usage: demo.py [-h] [-e] [-i INPUT] [--pd_m PD_M] [--lm_m LM_M] [-xyz] [-c]
               [--no_smoothing] [-f INTERNAL_FPS]
               [--internal_frame_height INTERNAL_FRAME_HEIGHT] [-s] [-t]
               [--force_detection] [-3 {None,image,mixed,world}]
               [-o OUTPUT]

optional arguments:
  -h, --help            show this help message and exit
  -e, --edge            Use Edge mode (postprocessing runs on the device)

Tracker arguments:
  -i INPUT, --input INPUT
                        'rgb' or 'rgb_laconic' or path to video/image file to
                        use as input (default=rgb)
  --pd_m PD_M           Path to an .blob file for pose detection model
  --lm_m LM_M           Landmark model ('full' or 'lite' or 'heavy') or path
                        to an .blob file
  -xyz, --xyz           Get (x,y,z) coords of reference body keypoint in
                        camera coord system (only for compatible devices)
  -c, --crop            Center crop frames to a square shape before feeding
                        pose detection model
  --no_smoothing        Disable smoothing filter
  -f INTERNAL_FPS, --internal_fps INTERNAL_FPS
                        Fps of internal color camera. Too high value lower NN
                        fps (default= depends on the model)
  --internal_frame_height INTERNAL_FRAME_HEIGHT
                        Internal color camera frame height in pixels
                        (default=640)
  -s, --stats           Print some statistics at exit
  -t, --trace           Print some debug messages
  --force_detection     Force person detection on every frame (never use
                        landmarks from previous frame to determine ROI)

Renderer arguments:
  -3 {None,image,mixed,world}, --show_3d {None,image,mixed,world}
                        Display skeleton in 3d in a separate window. See
                        README for description.
  -o OUTPUT, --output OUTPUT
                        Path to output video file
```
