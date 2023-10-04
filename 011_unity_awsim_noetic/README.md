# AWSIM

## AWSIMのダウンロード

- 以下のコマンドをダウンロードしたいパスに移動後に実行する
  - バージョンは最新でない場合があることに注意

- 動作確認済み（バージョン1.0.1）

```bash
wget https://github.com/tier4/AWSIM/releases/download/v1.0.1/AWSIM_v1.0.1.zip
unzip ./AWSIM_v1.0.1.zip
rm ./AWSIM_v1.0.1.zip
chmod +x ./AWSIM/AWSIM.x86_64
./AWSIM/AWSIM.x86_64
```

- 動作未確認（最新バージョン）

```bash
cd your/path
wget https://github.com/tier4/AWSIM/releases/download/v1.1.0/AWSIM_v1.1.0.zip  # 約900MB
unzip ./AWSIM_v1.1.0.zip
rm ./AWSIM_v1.1.0.zip
chmod +x ./AWSIM_v1.1.0/AWSIM_demo.x86_64
./AWSIM_v1.1.0/AWSIM_demo.x86_64  # 起動
```

### map file downloads

```bash
cd your/path
wget https://github.com/tier4/AWSIM/releases/download/v1.0.0/nishishinjuku_autoware_map.zip
unzip ./nishishinjuku_autoware_map.zip
rm ./nishishinjuku_autoware_map.zip
```

## Autowareのインストール

```bash
cd your/path
git clone https://github.com/autowarefoundation/autoware.git
cd autoware
git checkout awsim-stable
./setup-dev-env.sh
```
