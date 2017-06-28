# Chainer MN on Azure

ChainerMN��Azure��œ��������߂̃e���v���[�g  

�}�X�^�A�X���[�u�ANFS�T�[�o�ō\��  

�}�X�^�ƃX���[�u�ɂ́ACPU���z�}�V��(��:Standard_A2)��GPU���z�}�V��(��:Standard_Nc6)���w��\

NFS�T�[�o�ɂ̓f�[�^�f�B�X�N10��ڑ��\�ȉ��z�}�V��(��:Standard_A4)���w��

# deploy and visualize

<a href="https://portal.azure.com/#create/Microsoft.Template/uri/https%3A%2F%2Fraw.githubusercontent.com%2Fsatohiro%2FChainer-MN-on-Azure%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="http://azuredeploy.net/deploybutton.png"/>
</a>

<a href="http://armviz.io/#/?load=https%3A%2F%2Fraw.githubusercontent.com%2Fsatohiro%2FChainer-MN-on-Azure%2Fmaster%2Fazuredeploy.json" target="_blank">
    <img src="http://armviz.io/visualizebutton.png"/>
</a>

# OS�ɂ���

Ubuntu16.04.0-LTS �ɑΉ�

# �f�v���C����

CPU/GPU�Ƃ�45�`50�����x������B

# ����m�F���@

generaluser �Ń}�X�^�Ƀ��O�C����A�ȉ��̑����MNIST�����s�ł���B

## CPU���z�}�V���̏ꍇ

    cd
    wget https://raw.githubusercontent.com/chainer/chainermn/master/examples/mnist/train_mnist.py
    mpiexec -n <CORE> python3 train_mnist.py

<CORE>�ɂ̓}�X�^�A�X���[�u�̑S�R�A�����w��B
�Ⴆ��Standard_A2��2VM�g���ꍇ�A4���w��B

## GPU���z�}�V���̏ꍇ

    cd
    wget https://raw.githubusercontent.com/chainer/chainermn/master/examples/mnist/train_mnist.py
    mpiexec -n <GPU> python3 train_mnist.py -g

<GPU>�ɂ̓}�X�^�A�X���[�u�̑SGPU�����w��B
�Ⴆ��Standard_Nc6��2VM�g���ꍇ�A2���w��B
