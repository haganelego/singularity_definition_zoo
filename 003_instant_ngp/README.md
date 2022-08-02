# How to run NeRF Fox  
1. clone repositopry  
    ```bash
    git clone --recursive https://github.com/nvlabs/instant-ngp  
    ```  
2. build  
    ```bash
    cd instant-ngp  
    cmake . -B build  
    cmake --build build --config RelWithDebInfo -j  
    ```
3. run  
    ```bash  
    ./build/testbed --scene data/nerf/fox  
    ```

# How to prepare your datasets from video  
1. hogehoge
    ```bash  
    mkdir [path-to-instant-ngp]/data/[dataset_name]
    cp [Video file] [path-to-instant-ngp]/data/[dataset_name]
    ```
2. Extract images from video and predict camera parameter  
    ```bash    
    cd [path-to-instant-ngp]/data/[dataset_name]
    python [path-to-instant-ngp]/scripts/colmap2nerf.py --video_in <video file> --video_fps 2 --run_colmap --aabb_scale 16
    ```
    For detail, please refer https://github.com/NVlabs/instant-ngp/blob/master/docs/nerf_dataset_tips.md

3. run  
    ```bash
    ./build/testbed --scene data/[dataset_name]
    ```