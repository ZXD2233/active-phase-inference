# Active Phase Inference

Bayesian measurement selection for physical-state identification with fewer measurements.
An exploratory Bayesian feedback demonstration of physical-state identification in an extended SSH chain. Includes adaptive measurements, model-mismatch monitoring, inconclusive decisions and three result figures.

## Results

In the extended-SSH simulation, physical-class information reduced mean measurement shots by **24.5%** compared with a fixed schedule: **940.3 → 709.9** across 120 identification runs (60 simulated devices, two noise repeats each, five in-family parameter regimes). It returned **63 correct, 1 incorrect and 56 inconclusive** outcomes, giving **98.4% accuracy among its 64 definitive answers**. Calibration shots are counted separately.

## Reuse

The reusable method combines Bayesian updates, information-gain measurement selection and predictive mismatch monitoring for count-based state identification. To adapt it, replace the physical model, candidate measurements, outcome probabilities and class definitions, then recalibrate the alarm threshold. The current calculation uses four classes and three count outcomes; their array dimensions and corresponding formulas need to follow the new task.

## Run

Requires Python 3.12 or newer. Run from this folder:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install "numpy>=1.26,<3" "scipy>=1.12,<2" "matplotlib>=3.8,<4" ipykernel
```

Open `ActivePhaseInference.ipynb` in VS Code, select this folder's `.venv` Python kernel, and click **Run All**. Edit parameters in the second code cell. Results and all three figures appear in the notebook.

Model: [Critical Topological Photonics in Synthetic Dimensions](https://arxiv.org/abs/2608.21791). Bayesian and monitoring utilities adapted from nhqctrl; see [LICENSE](LICENSE).

## 中文

用贝叶斯反馈在有限测量下识别扩展 SSH 链的物理状态，比较固定测量、参数信息和物理类别信息三种策略。包含自适应测量、模型失配报警、证据不足判断，以及反馈过程、测量开销和分类结果三类图。

**结果：**在扩展 SSH 链模拟中，对五类参数情形下的 60 个模拟设备各进行两次噪声重复，共 120 次识别。物理类别信息策略相较固定测量方案，将平均测量次数从 **940.3 降至 709.9，减少 24.5%**；取得 **63 次正确、1 次错误、56 次证据不足**，明确判断中的正确率为 **98.4%（63/64）**。以上为设备识别阶段的测量，校准测量单独计数。

**复用与迁移：**可复用贝叶斯更新、信息增益选测量和预测失配判据的计算流程。迁移到其他基于计数测量的状态识别任务时，替换物理模型、候选测量、读数概率和分类定义，并重新校准报警阈值。当前示例采用四类状态、三种计数读数，相关数组维度和公式需随新任务调整。

需要 Python 3.12 或更新版本。先在项目目录执行上方命令建立环境并安装依赖。

用 VS Code 打开 `ActivePhaseInference.ipynb`，选择本目录 `.venv` 对应的 Python 内核，然后点击“全部运行”。参数在第二个代码单元格中修改；结果和三类图直接显示在 Notebook 中。

模型来源和许可见上方链接。
