# Chainer MN on Azure

ChainerMN��Azure��œ��������߂̃e���v���[�g  

�������A* �����_�ł� GPU �ɂ͖��Ή� *

# deploy and visualize

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fsatohiro%2FChainer-MN-on-Azure%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

<a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2Fsatohiro%2FChainer-MN-on-Azure%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="http://armviz.io/visualizebutton.png"/>
</a>

# �f�v���C����

�}�X�^�A�X���[�u�� Standard_A2�ANFS�T�[�o��Standard_A4�Ńf�v���C�����ꍇ�A
45�����x������B

# ����m�F���@

generaluser �Ń}�X�^�Ƀ��O�C����A�ȉ��̑����MNIST�����s�ł���B
CORE�ɂ́A�}�X�^�A�X���[�u�̑S�R�A�����w�肷��B

    cd
    cp /tmp/chainermn/examples/mnist/train_mnist.py .
    mpiexec  -n CORE python3 train_mnist.py
