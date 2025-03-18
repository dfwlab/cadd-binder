FROM jupyter/scipy-notebook:latest

# 安装 RDKit
RUN conda install -c conda-forge rdkit

RUN pip install --no-cache-dir --pre deepchem &&\
    pip3 install --no-cache-dir torch torchvision torchaudio &&\
    pip install --no-cache-dir transformers selfies

# 安装 PyTorch（无 GPU 版本）
# RUN conda install -c pytorch pytorch cpuonly -y

# 复制所有文件到 /home/jovyan/work
COPY ./data /home/jovyan/work

# 设置工作目录，使 Jupyter 直接打开 /home/jovyan/work
WORKDIR /home/jovyan/work

# 确保 Notebook 启动目录正确
CMD ["start-notebook.sh", "--NotebookApp.token=''"]
