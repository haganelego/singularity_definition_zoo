# How to run  
1. Build this image
2. clone DietNeRF
3. Install CLIP in developer mode
    ```
    cd CLIP
    pip install -e .
    cd ..
    ```
4. Download and shuring dataset
    ```
    mkdir dietnerf/logs/ dietnerf/data/
    cd dietnerf/data
    gdown --id 18JxhpWD-4ZmuFKLzKlAw-w5PpzZxXOcG -O nerf_synthetic.zip
    unzip nerf_synthetic.zip
    rm -r __MACOSX
    ```