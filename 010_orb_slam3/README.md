# ORB-SLAM3 for ros-noetic

- ビルドコマンド(sand box版)

```bash
sudo singularity build --sandbox orb_slam3_sandbox Definitionfile.def
```

- 現状は，ORB_SLAM3のbuild_ros.shのみ手動で入れ直す必要あり．

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