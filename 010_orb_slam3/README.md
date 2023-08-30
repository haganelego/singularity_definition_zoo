# ORB-SLAM3 for ros-noetic

- ビルドコマンド(sandbox)

```bash
singularity build --fakeroot --sandbox orb_slam3_sandbox Definitionfile.def
```

- ORB_SLAM3の用意（ローカルでの作業）
  - 本セットアップもsingularityの中で行いたい方は，Defファイルの後半部分をコメントアウトしてください．
    - `install ORB_SLAM3`，`install orb_slam3_ros_wrapper`
  - ローカル環境の，`~/ros_ws/vslam_ws`を使用します．（無ければ作成）
  - 異なるパスで作業したい場合は，適宜パス指定を読み替えながら利用してください．

```bash
singularity shell orb_slam3_sandbox # 仮想環境の起動
source /entrypoint.sh

### 仮想環境の中で実行
# build ORB_SLAM
cd ~/
mkdir -p ~/ros_ws/vslam_ws/src/include && cd ~/ros_ws/vslam_ws/src/include/
git clone https://github.com/UZ-SLAMLab/ORB_SLAM3.git
cd ORB_SLAM3/
chmod +x build.sh
sed -i 's/++11/++14/g' CMakeLists.txt
./build.sh

# build ORB_SLAM3_ros_noetic_wrapper
cd ~/ros_ws/vslam_ws/src/
git clone https://github.com/thien94/orb_slam3_ros_wrapper
cd orb_slam3_ros_wrapper

# set orb_slam path to cmakelists
sed -i "s/Packages/ros_ws\/vslam_ws\/src\/include/g" CMakeLists.txt
# copy ORBvoc.txt
cp ~/ros_ws/vslam_ws/src/include/ORB_SLAM3/Vocabulary/ORBvoc.txt ~/ros_ws/vslam_ws/src/orb_slam3_ros_wrapper/config/ORBvoc.txt

cd ~/ros_ws/vslam_ws/src/
catkin build -j4
```

- ORB_SLAM3の起動
  - 事前に[euroc_dataset](http://robotics.ethz.ch/~asl-datasets/ijrr_euroc_mav_dataset/machine_hall/)からrosbagをダウンロード

- terminal1

```bash
singularity shell orb_slam3_sandbox # 仮想環境の起動
source /entrypoint.sh

cd ~/ros_ws/vslam_ws/src/
source devel/setup.bash
roslaunch orb_slam3_ros_wrapper euroc_mono.launch
```

- terminal2

```bash
singularity shell orb_slam3_sandbox # 仮想環境の起動
source /entrypoint.sh

cd your/rosbag/path
rosbag play MH_01_easy.bag
```

## 参考

- ORB-SLAM3をnoeticで動かす[https://handaru.net/blog/2022/09/15/376/]

## FAQ

- 以下の原因で，build_ros.shが通らない．

```bash
c++: fatal error: Killed signal terminated program cc1plus
```

- メモリ不足によるエラー
- build_ros.shの7行目を以下のように変更
  - `make -j` → `make -j4`

- gtk2 error
  - [opencv gtk](https://stackoverflow.com/questions/22029939/opencv-getting-picture-from-default-webcam-in-c-c-gtk-issues)