# Chainer MN on Azure

ChainerMNをAzure上で動かすためのテンプレート  

マスタ、スレーブ、NFSサーバで構成  

マスタとスレーブには、CPU仮想マシン(例:Standard_A2)やGPU仮想マシン(例:Standard_Nc6)を指定可能

NFSサーバにはデータディスク10個を接続可能な仮想マシン(例:Standard_A4)を指定

# deploy and visualize

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fsatohiro%2FChainer-MN-on-Azure%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

<a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2Fsatohiro%2FChainer-MN-on-Azure%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="http://armviz.io/visualizebutton.png"/>
</a>

# OSについて

Ubuntu16.04.0-LTS に対応

# デプロイ時間

CPU/GPUとも45～50分程度かかる。

# 動作確認方法

generaluser でマスタにログイン後、以下の操作でMNISTを実行できる。

## CPU仮想マシンの場合

    cd
    wget https://raw.githubusercontent.com/chainer/chainermn/master/examples/mnist/train_mnist.py
    mpiexec -n <CORE> python3 train_mnist.py

<CORE>にはマスタ、スレーブの全コア数を指定。
例えばStandard_A2を2VM使う場合、4を指定。

## GPU仮想マシンの場合

    cd
    wget https://raw.githubusercontent.com/chainer/chainermn/master/examples/mnist/train_mnist.py
    mpiexec -n <GPU> python3 train_mnist.py -g

<GPU>にはマスタ、スレーブの全GPU数を指定。
例えばStandard_Nc6を2VM使う場合、2を指定。
