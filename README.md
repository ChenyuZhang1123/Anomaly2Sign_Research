# Anomaly2Sign Research 项目

这是一个通过……方法，从网络流量数据中自动生成异常检测签名的研究项目。

## 功能与特性

*   **数据预处理**: 包含对原始流量数据的完整清洗和特征工程流程。
*   **多种采样技术**: 实现了包括 SMOTE, TLink-RUS 等在内的多种数据采样方法，以解决数据不平衡问题。
*   **模型训练**: 基于决策树（Decision Tree）进行模型训练。
*   **规则自动生成**: 从训练好的模型中自动提取可解释的检测规则。

## 如何运行

1.  **环境配置**:
    ```bash
    conda env create -f environment.yml
    conda activate anomaly2sign
    ```

2.  **数据准备**:
    - 原始数据存放于 `/data/raw/` 目录下。
    - 本项目使用 Git LFS 管理原始数据，请确保已安装 Git LFS。

3.  **执行流程**:
    - **第一步：数据预处理**
      运行 `data_process.ipynb` 来生成处理好的数据。
    - **第二步：数据采样**
      运行 `sample.ipynb` 来对数据进行采样（实现了前三种方法）。
    - **第三步：模型训练与规则生成**
      运行 `train.ipynb` 来使用其中一种采样方法的数据进行训练，并生成最终规则。

## 文件结构说明

- `data_process.ipynb`: 完成数据预处理。
- `sample.ipynb`: 完成数据采样（前三种方法）。
- `train.ipynb`: 完成一种采样方法+DT训练，并生成规则。
- `/data/raw/`: 存放原始数据集（通过 Git LFS 追踪）。
- `/output/`: 存放生成的规则和报告。
