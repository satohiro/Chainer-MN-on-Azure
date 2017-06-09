# Chainer MN on Azure

ChainerMNをAzure上で動かすためのテンプレート  

ただし、* 現時点では GPU には未対応 *

# deploy and visualize

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fsatohiro%2FChainer-MN-on-Azure%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

<a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2Fsatohiro%2FChainer-MN-on-Azure%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="http://armviz.io/visualizebutton.png"/>
</a>

# デプロイ時間

マスタ、スレーブを Standard_A2、NFSサーバをStandard_A4でデプロイした場合、
45分程度かかる。

# 動作確認方法

generaluser でマスタにログイン後、以下の操作でMNISTを実行できる。
COREには、マスタ、スレーブの全コア数を指定する。

    cd
    cp /tmp/chainermn/examples/mnist/train_mnist.py .
    mpiexec  -n CORE python3 train_mnist.py
