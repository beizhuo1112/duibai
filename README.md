# 对白 Duibai

Windows x64 本地人物配音与对白制作工具。3.6 版采用软件与模型分别下载，模型准备好后在本机离线生成，不调用云端配音服务。

## 联网安装（推荐）

[下载对白 3.6 安装器](https://github.com/beizhuo1112/duibai/releases/download/v3.6.0/Duibai-3.6-Windows-x64-Setup.exe)（约 12.7 MiB）。选择安装目录和原精度／8 位／4 位模型，点击安装，自动下载、校验、解压并创建快捷方式，无需手动合并分卷。安装后直接离线使用所选模型。

软件加模型总下载约 5.36～6.25 GiB；安装向导显示所选方案的下载量和磁盘需求。支持断点续传、失败重试和取消安装。下载需要能够访问 GitHub；无需登录账号。原精度支持 CPU／NVIDIA，8 位与 4 位需要兼容的 NVIDIA GPU，量化不保证相同音质或更快生成。

[安装说明](https://github.com/beizhuo1112/duibai/releases/download/v3.6.0/INSTALLER-INSTRUCTIONS.md) · [安装器源码](https://github.com/beizhuo1112/duibai/releases/download/v3.6.0/Duibai-3.6-Installer-Source.zip)

## 手动下载 / 离线准备 3.6

[打开正式下载页](https://github.com/beizhuo1112/duibai/releases/tag/v3.6.0)。下载软件包，再选择一种模型包：原精度、8 位或 4 位保守量化。

GitHub 的每个附件须小于 2 GiB，因此每个完整 ZIP 分成两卷。分卷没有重新压缩或修改 ZIP 内容，合并后校验值与原始已验证发布包完全一致。

| 下载内容 | 第一卷 | 第二卷 | 校验并合并 |
|---|---|---|---|
| 软件包（不含模型） | [下载](https://github.com/beizhuo1112/duibai/releases/download/v3.6.0/Duibai-3.6-Windows-x64.zip.001) | [下载](https://github.com/beizhuo1112/duibai/releases/download/v3.6.0/Duibai-3.6-Windows-x64.zip.002) | [合并脚本](https://github.com/beizhuo1112/duibai/releases/download/v3.6.0/Merge-Duibai-3.6-Windows-x64.cmd) |
| 原精度模型包 | [下载](https://github.com/beizhuo1112/duibai/releases/download/v3.6.0/Duibai-3.6-Qwen3TTS-0.6B-original.zip.001) | [下载](https://github.com/beizhuo1112/duibai/releases/download/v3.6.0/Duibai-3.6-Qwen3TTS-0.6B-original.zip.002) | [合并脚本](https://github.com/beizhuo1112/duibai/releases/download/v3.6.0/Merge-Duibai-3.6-Qwen3TTS-0.6B-original.cmd) |
| 8 位模型包 | [下载](https://github.com/beizhuo1112/duibai/releases/download/v3.6.0/Duibai-3.6-Qwen3TTS-0.6B-int8.zip.001) | [下载](https://github.com/beizhuo1112/duibai/releases/download/v3.6.0/Duibai-3.6-Qwen3TTS-0.6B-int8.zip.002) | [合并脚本](https://github.com/beizhuo1112/duibai/releases/download/v3.6.0/Merge-Duibai-3.6-Qwen3TTS-0.6B-int8.cmd) |
| 4 位模型包（保守量化） | [下载](https://github.com/beizhuo1112/duibai/releases/download/v3.6.0/Duibai-3.6-Qwen3TTS-0.6B-nf4.zip.001) | [下载](https://github.com/beizhuo1112/duibai/releases/download/v3.6.0/Duibai-3.6-Qwen3TTS-0.6B-nf4.zip.002) | [合并脚本](https://github.com/beizhuo1112/duibai/releases/download/v3.6.0/Merge-Duibai-3.6-Qwen3TTS-0.6B-nf4.cmd) |

## 安装与启动

1. 将所选包的两卷（`.001` 和 `.002`）及对应 `Merge-*.cmd` 放在同一个目录。软件包和选定的模型包各下载一组。
2. 双击对应合并脚本。脚本使用 Windows 自带 PowerShell，先核验每卷 SHA-256，再合并并核验完整 ZIP。脚本原文也提供在同名 `.ps1.txt` 文件中。目录需有存放合并 ZIP 的空闲空间。
3. 完整解压软件 ZIP 和选定模型 ZIP。软件双击 `启动对白.cmd`；进入“设置 → 语音模型”选择模型包目录或其中的 `models` 目录，保存并应用设置。
4. 模型可以存放在软件之外。更新软件时保留模型目录即可，不必重新下载模型。

如需要手动校验，请下载 [SHA256SUMS.txt](https://github.com/beizhuo1112/duibai/releases/download/v3.6.0/SHA256SUMS.txt) 与 [下载清单](https://github.com/beizhuo1112/duibai/releases/download/v3.6.0/Duibai-3.6-downloads.json)。合并不会覆盖校验不符的现有 ZIP；出现缺卷、损坏或已有 `.merging` 文件时，先保存这些文件，再排查下载是否完整。

GitHub 自动生成的 `Source code.zip` 是这个下载仓库的文档源码。运行软件请下载上表的软件分卷；应用对应的可编辑 Python 源码已包含在软件 ZIP 的 `source` 目录内。

## 模型选择

| 模型 | 完整 ZIP 下载大小 | 模型准备后磁盘占用 | 说明 |
|---|---:|---:|---|
| 原精度 | 3.26 GiB | 4.03 GiB | 官方固定版本原始权重 |
| 8 位 | 2.59 GiB | 3.07 GiB | 本项目导出，量化 231 个线性层 |
| 4 位保守量化 | 2.37 GiB | 2.81 GiB | 本项目导出，量化 196 层，保留声学预测部分的原推理精度 |

软件 ZIP 下载大小 2.99 GiB，解压约 4.95 GiB。用户需要软件加一种模型，分包不会消除本地运行库和模型的总占用。模型准备时相同附件优先建立硬链接；不能使用硬链接时占用会增加约 0.64 GiB。

每个模型包均含 Qwen3-TTS 12Hz 0.6B Base、CustomVoice 和未量化的音频解码器。8 位、4 位需要兼容的 NVIDIA GPU；本次验证显卡为 GTX 1650 Ti 4GB。量化不能保证相同音质或更快生成。两个量化包为本项目制作，模型来源、固定版本、原始哈希、量化配置和许可证随包提供。

[Qwen3-TTS 官方项目](https://github.com/QwenLM/Qwen3-TTS) · [官方 Base](https://huggingface.co/Qwen/Qwen3-TTS-12Hz-0.6B-Base) · [官方 CustomVoice](https://huggingface.co/Qwen/Qwen3-TTS-12Hz-0.6B-CustomVoice)

## 验证范围

三种模型保存后重新载入，成人及儿童配音、界面、滑块调音、功能和储存验收通过。软件 ZIP 独立解压及逐文件 SHA-256 核验通过，实际 CMD 启动入口使用包内 Python 和精简 PATH 验证通过。开发源码在新虚拟环境恢复依赖，通过 61 项单元测试并重新构建运行。

验证使用同一台 Windows 电脑，未覆盖干净 Windows 虚拟机、其他显卡或完整 CPU 配音测试。4 位采用通过验收的保守方案；初始方案的音高调节检查未通过，未作为本次发布模型。

## 许可

对白应用按 GPL-3.0-or-later 提供，应用对应源代码和资源在软件包 `source` 目录中；第三方许可保留在软件包 `licenses` 及运行库的许可元数据中。Qwen 原始模型与本项目量化衍生包保留 Apache-2.0 许可和来源说明；bitsandbytes 运行库保留其 MIT 许可。各组件以其随包许可文件为准。
