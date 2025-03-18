FROM jupyter/scipy-notebook:latest

# 安装 RDKit
RUN conda install -c conda-forge rdkit

# 安装 DeepChem（无 GPU 版本）
RUN pip install --pre deepchem

# 安装 PyTorch（无 GPU 版本）
RUN conda install -c pytorch pytorch cpuonly -y

# 安装 Transformers 和 Selfies
RUN pip install transformers selfies

# 复制所有文件到 /home/jovyan/work
COPY ./data /home/jovyan/work

# 设置工作目录，使 Jupyter 直接打开 /home/jovyan/work
WORKDIR /home/jovyan/work

# 确保 Notebook 启动目录正确
CMD ["start-notebook.sh", "--NotebookApp.token=''"]
