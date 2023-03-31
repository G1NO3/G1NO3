1.将以下几个地址配置进高级系统设置-环境变量-系统变量-Path-编辑  
C:\ProgramData\anaconda3  
C:\ProgramData\anaconda3\Lib  
C:\ProgramData\anaconda3\Scripts  
C:\ProgramData\anaconda3\Library\bin  
C:\ProgramData\anaconda3\Library\mingw-w64\bin  

2.运行conda，安装新的虚拟环境  
conda create -n [NAME] python=*.*  
conda activate [NAME]  

3.与Jupyter连接：  
conda install ipython ipykernel nb_conda_kernels  
将环境写入jupyter notebook的kernel中：python-m ipykernel install --user --name=[NAME]  


4.设置清华镜像  
Anaconda 安装包可以到 https://mirrors.tuna.tsinghua.edu.cn/anaconda/archive/ 下载。  
TUNA 还提供了 Anaconda 仓库与第三方源（conda-forge、msys2、pytorch等，查看完整列表，更多第三方源可以前往校园网联合镜像站查看）的镜像，各系统都可以通过修改用户目录下的 .condarc 文件来使用 TUNA 镜像源。Windows 用户无法直接创建名为 .condarc 的文件，可先执行 conda config --set show_channel_urls yes 生成该文件之后再修改。  
注：由于更新过快难以同步，我们不同步pytorch-nightly, pytorch-nightly-cpu, ignite-nightly这三个包。  
channels:  
  - defaults  
show_channel_urls: true  
default_channels:  
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main  
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r  
  - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2  
custom_channels:  
  conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud  
  msys2: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud  
  bioconda: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud  
  menpo: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud  
  pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud  
  pytorch-lts: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud  
  simpleitk: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud  
即可添加 Anaconda Python 免费仓库。  
运行 conda clean -i 清除索引缓存，保证用的是镜像站提供的索引。  


5.安装常用包(torch,tf之类的去官网搜安装命令)：  
conda install numpy pandas matplotlib sklearn tqdm  
