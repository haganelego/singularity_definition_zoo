pip uninstall opencv-python

pip install  opencv-contrib-python opencv-python-headless

--nv
python annotator.py --app_resolution 1000,1600 --model_type vit_b --keep_input_size True --max_size 720