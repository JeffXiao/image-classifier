Step0: requirements:
Python=3.5
EasyProcess=0.23
Keras=2.14
Markdown=2.6.11
Pillow=5.0.0
PyVirtualDisplay=0.2.1
PyYAML=3.12
Werkzeug=0.14.1
absl-py=0.1.10
beautifulsoup4=4.6.0
bleach=1.5.0
bs4=0.0.1
certifi=2018.1.18
chardet=3.0.4
click=6.7
decorator=4.0.11
face-recognition-models=3.0.0
fake-useragent=0.1.10
h5py=2.7.1
html5lib=0.99999999
idna=2.6
imageio=2.1.2
lxml=4.1.1
moviepy=0.2.3.2
numpy=1.14.1
opencv-python=3.4.0.12
pip=9.0.1
protobuf=3.5.1
pytube=9.0.6
requests=2.18.4
scipy=1.0.0
selenium=3.9.0
setuptools=38.5.1
six=1.11.0
tensorflow=1.5.0
tensorflow-tensorboard=1.5.1
tqdm=4.19.6
urllib3=1.22
wheel=0.30.0

Step1: download flowers image:
curl -O http://download.tensorflow.org/example_images/flower_photos.tgz

Step2: extract flowers photo files and put them under the current folder as sub folder flower_photos

Step3: run retain.py to classify images:
$ python ./retain.py --bottleneck_dir=/tmp/tf_files/bottlenecks --how_many_retaining_steps 500 --model_dir=/tmp/tf_files/inception --output_graph=/tmp/tf_files/retrained_graph.pb --output_labels=/tmp/tf_files/retrained_labels.txt --image_dir ./flower_photos

Step4: classify image:
$ python ./label_image.py ./flower_photos/roses/295257304_de893fc94d.jpg

It will display the following output:
roses (score = 0.98676)
tulips (score = 0.01321)
sunflowers (score = 0.00001)
daisy (score = 0.00001)
dandelion (score = 0.00000)

Process finished with exit code 0
