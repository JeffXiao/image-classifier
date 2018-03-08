# Step0: install libraries using requirements.txt:
$ pip install -r requirements.txt

# Step1: download flowers image:

$ curl -O http://download.tensorflow.org/example_images/flower_photos.tgz

# Step2: extract flowers photo files and put them under the current folder as sub folder flower_photos

# Step3: run retain.py to classify images:

$ python ./retain.py --bottleneck_dir=/tmp/tf_files/bottlenecks --how_many_retaining_steps 500 --model_dir=/tmp/tf_files/inception --output_graph=/tmp/tf_files/retrained_graph.pb --output_labels=/tmp/tf_files/retrained_labels.txt --image_dir ./flower_photos

# Step4: classify image:

$ python ./label_image.py ./flower_photos/roses/295257304_de893fc94d.jpg

It will display the following output:

roses (score = 0.98676)

tulips (score = 0.01321)

sunflowers (score = 0.00001)

daisy (score = 0.00001)

dandelion (score = 0.00000)

Process finished with exit code 0
