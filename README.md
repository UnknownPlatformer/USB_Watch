### USB Watch

_USB watch_ can tell the difference between a lightning cord, USB-A, and an audio jack in real time and points to exactly where it thinks the cord is in the stream. 

#### The Algorithm

USB Watch uses hundreds of photos of cords utilizing different backgrounds, colors, and poses to identify objects shown on the screen. It depends on the mobilenet SSD object detection algorithm. In order to get the best detection use a simple background and good contrast with the cord type. A complex background will work, but its accuracy will be slightly lower, and it may be harder for it to find the object in real time.

#### Running this project

**Step 1:** Download the model from the github and ensure your system, and interface are properly configured. Place the model file inside visual studio code, the path should be: USB_Watch/Model_Final

**Step 2:** Open a terminal in your headless desktop session

**Step 3:** Access the model path in the terminal with the following command:

`NET=~/USB_Watch/Model_Final`

**Step 4:** Run the model in the same terminal with this command:

`detectnet \
  --model=$NET/ssd-mobilenet.onnx \
  --labels=$NET/labels.txt \
  --input-blob=input_0 \
  --output-cvg=scores \
  --output-bbox=boxes \
  /dev/video0`

**Step 5:** A livestream will open (video0) to use it show one of the 3 listed cord types to your camera.

#### Image

<img width="913" height="685" alt="Screenshot 2026-07-15 110640" src="https://github.com/user-attachments/assets/702a1e33-3194-4819-95b9-8d9ab60c4de0" />

#### Video

https://drive.google.com/file/d/1soy5HpBBvp-PjYgSYgVvK96l_WT000Tf/view?usp=sharing

