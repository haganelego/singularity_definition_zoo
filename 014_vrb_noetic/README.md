# vrb

- [VRB: Affordances from Human Videos as a Versatile Representation for Robotics](https://github.com/shikharbahl/vrb)

## buildコマンド

```bash
singularity build --fakeroot --sandbox <path>/singularity_definition_zoo/013_clrnet_cuda_11_7/sandbox_clrnet Definitionfile.def 
```

## 起動コマンド

```bash
singularity shell --nv -B /run/user/1000,/var/lib/dbus/machine-id env/sigverse_sandbox/
source /entrypoint.sh
```

## vrb使用メモ

```bash
git clone https://github.com/shikharbahl/vrb.git
cd vrb/
mkdir models
```

- [model](https://drive.google.com/file/d/1nzahuDh4Wa0SXCPwpu9Z_MwkQGerGAhp/view?usp=sharing)をダウンロード
  - `model_checkpoint_1249.pth.tar`を`models`に配置

```bash
cd vrb/
python demo.py --image ./kitchen.jpeg --model_path ./models/model_checkpoint_1249.pth.tar
```

## プロンプト調整

- [この行](https://github.com/shikharbahl/vrb/blob/a3aaa272fddfa6c766d1a0069b486c6cece60f31/inference.py#L55)で調整可能
- 引数指定などは対応していない

## 環境概要

| | |
| --- | --- |
| OS | Ubuntu20.04 |
| Cuda | 11.7.1 |
| ROS | Noetic |
| Torch | 2.0.0 |
