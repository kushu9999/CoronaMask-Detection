# CoronaMask-Detection
Mask Detection in Real-time with 99% Accuracy

## if you are using anaconda then create new environment for easy of use

1)conda create --name mask
2)conda activate mask

then install requirments


"Requirments"

pip install  opencv-python
pip install  opencv-contrib-python
pip install  Cython
pip install  contextlib2
pip install  pillow
pip install  lxml
pip/conda install  jupyter
pip/conda install  matplotlib
pip/conda install  tensorflow-gpu==1.15 <-- "Note i used 1.15 version for cuda enable gpu"

### if you don't have Nvidia Graphics which compatiblity >5.0 or AMD Graphics
### you can use cpu version

pip/conda install  tensorflow==1.15 <-- "Note i used 1.15 version for cpu"



(step-1) Download tensorflow object detection api model from github "https://github.com/tensorflow/models"

(step-2) Goto models/research/object_detection and change protos folder with my protos folder then run in terminal " ./bin/protoc object_detection/protos/*.proto --python_out=. "  <-- without inverted comma

(step-3) Goto models/research and run command python setup.py build then run python setup.py install

(step-4) Goto models/research/slim change file name BUILD to BUILDD

(step-5) Goto models/research/slim and run command python setup.py build then run python setup.py install

(step-6) Goto models/research/object_detection and paste inference_graph,training,run.py,train.record,test.record and finalmask.mp4

(step-7) open your terminal goto models/research/object_detection and run python run.py

(step-8) if you want to use your own video then change videofile in run.py at line no 89 and you want to use your ip/rtsp camera chnage http/rtsp link at line no 89 and comment line no 88

# (optional) 
if you want to export tflite graph and you can use this command

Goto models/research/object_detection and run

python export_tflite_ssd_graph.py --input_type image_tensor --pipeline_config_path training/ssd_mobilenet_v2_coco.config --trained_checkpoint_prefix training/model.ckpt-43979 --output_directory inference_graph2

now you can check in models/research/object_detection/inference_graph2 in this folder you can fild tflite_graph.pb and tflite_graph.pbtxt files , you can use in micro-computers like rasberrypie/nvidia jetson nano etc 
