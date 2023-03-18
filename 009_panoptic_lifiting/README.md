# How to run  

1. Build this image

2. clone panoptic-lifting

    ```bash
    git clone https://github.com/nihalsid/panoptic-lifting
    ```

3. Download data and pretrained models

    - [data](https://drive.google.com/file/d/1I6Y7IqSEmWl_T4CRUj-TmlUgejjexCa7/view?usp=sharing)
    - [pretrained models](https://drive.google.com/file/d/1dvkfZ9beYVsxG_RftZ6aguHP6FLgjAC3/view?usp=sharings)
    - [この章](https://drive.google.com/file/d/1dvkfZ9beYVsxG_RftZ6aguHP6FLgjAC3/view?usp=sharing)を参考に配置する

4. run inference

    ```bash
    python inference/render_panopli.py pretrained-examples/hypersim_ai001008/checkpoints/epoch=30-step=590148.ckpt False
    ```
