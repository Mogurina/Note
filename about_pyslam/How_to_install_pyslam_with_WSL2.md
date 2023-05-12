# Pyslamのインストール方法
## 環境
* windows10 home
* WSL2(ubuntu18.04)
* anaconda
  
## インストール手順
### WSL2のインストールとubuntu18のセットアップが完了していることを前提に進める。
1. 下記のコマンド実行し、anaconda3をubuntuにインストールする。
   [anacondaのインストーラ](https://www.anaconda.com/download#downloads)  
   リンクから最新のインストーラを選択するとよい
   ```
   wget https://repo.anaconda.com/archive/Anaconda3-2023.03-1-Linux-x86_64.sh`  
   ```
2. 下記のコマンドを任意のディレクトリで実行し、`pyslam`をローカル環境にクローンする。
   ```
   git clone --recursive https://github.com/luigifreda/pyslam.git
   ```  
   
3. pyslamのディレクトリに移動し、下記のコマンドを実行する。  
   pyslam用のanaconda仮想環境の構築と必要なライブラリのインストールを行う。
   ```
   cd pyslam
   . install_all_conda.sh  
   ``` 
   >**注意**  
   >- .の後は/ではなく必ず半角で空白を入れる  
   >- opencvのダウンロード中に読み込み続ける不具合が発生する場合があるが、ctrl+cで強制的にキャンセルするとよい。  
   >- cmakeがインストールされてない場合は`sudo apt install cmake`を実行する  
   処理が途中で止まってしまうため、正しくライブラリがインストールされない。

4. 下記のコマンドを実行しサードパーティーのライブラリ群をインストールする。  
    g20など`main_slam.py`を動作させるために必要な外部ライブラリをインストールしている。
    ```
    ./install_all.sh
    ```
 
    >**参考**  
    >[anaconda環境でのpyslamのインストール方法詳細](https://github.com/luigifreda/pyslam/blob/master/CONDA.md)  
    >[問題が発生した際に参照するページ](https://github.com/luigifreda/pyslam/blob/master/TROUBLESHOOTING.md)
  
---
