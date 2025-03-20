# Object-Detection-based-on-paddle
The tutorial for object detection based on PaddlePaddle.

envs: Python 3.8 ~ 3.10

1. open the Anaconda PowerShell Prompt

   conda create -n test python=3.10
   conda activate test

1. Paddle install

# cpu
python -m pip install paddlepaddle==3.0.0b1 -i https://www.paddlepaddle.org.cn/packages/stable/cpu/

# gpu，cuda=11.8
python -m pip install paddlepaddle-gpu==3.0.0b1 -i https://www.paddlepaddle.org.cn/packages/stable/cu118/

# gpu，cuda=12.3
python -m pip install paddlepaddle-gpu==3.0.0b1 -i https://www.paddlepaddle.org.cn/packages/stable/cu123/

2.PaddleX install

pip install https://paddle-model-ecology.bj.bcebos.com/paddlex/whl/paddlex-3.0.0b1-py3-none-any.whl

3. paddlex --pipeline [pipeline] --input [url or local path] --device [gpu or cpu]

   paddlex --pipeline object_detection --input https://paddle-model-ecology.bj.bcebos.com/paddlex/imgs/demo_image/general_object_detection_002.png --device gpu:0

##run the code in Pycharm
from paddlex import create_pipeline

pipeline = create_pipeline(pipeline="small_object_detection")

output = pipeline.predict("the input image's path or url")
for res in output:
    res.print() 
    res.save_to_img("the output path") 
    res.save_to_json("the output path") 


The result based on Paddle:

![images](https://github.com/user-attachments/assets/d08ccb2d-7aca-467a-ac9a-2a0d18e32442)

![2](https://github.com/user-attachments/assets/48af4a61-a261-4723-9946-2b590e4946e0)

![small_object_detection](https://github.com/user-attachments/assets/473043b2-d5d1-4154-a231-f4bcc281f15c)
