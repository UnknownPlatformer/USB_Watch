### USB Watch

_USB watch_ can tell the difference between a lightning cord, USB-A, and an audio jack in real time and points to exactly where it thinks the cord is in the stream. 

#### The Algorithm

USB Watch uses hundreds of photos of cords utilizing different backgrounds, colors, and poses to identify objects shown on the screen. It depends on mobilenet SSD object detection. In order to get the best detection the simpler the background and more of a color difference the background is from the cord, the easier and higher quality detections will be for the model. A complex background will work, but its accuracy will be noticeably lower, and it may have a hard time finding the object in real time.

#### Running this project

**Step 1:** Download the model from the github and ensure your system, and interface are properly configured.

**Step 2:** Open the terminal.

**Step 3:** Open the model path in the terminal with the following command:

'NET=~/USB_Watch/USB_model6'

**Step 4:** Run the model:

'detectnet \
  --model=$NET/ssd-mobilenet.onnx \
  --labels=$NET/labels.txt \
  --input-blob=input_0 \
  --output-cvg=scores \
  --output-bbox=boxes \
  /dev/video0'

#### Output

_Image of it working_

Where to read the accuracy.


[View a video explanation here](video link)

