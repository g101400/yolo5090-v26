# YOLOv5-Lite · YOLOv26 通道（预留通道）— 仓库 yolov5-lite-v26-5090

> 「5090」为本机 AI 推理产品线统一后缀；本仓库对应 **YOLOv26** 版本通道。
> 版本号区间（详见主仓库路线图）：**6.0.1 – 6.9.8**

## 状态
🔒 预留通道 / 待官方权重。当前为占位与方案备份仓库，尚未包含可编译代码。

## 背景
主仓库 [yolov5-lite-v5-5090](https://github.com/g101400/yolov5-lite-v5-5090) 已完成 YOLOv5（v5lite）安卓版 v1.2.1。
本仓库预留 **YOLOv26** 接入通道，版本号从 **6.0.1** 起。

## 说明
- 社区暂未发布官方 YOLOv26 权重与确定导出方式，故先占位；
- 待权重可用后，按主仓库统一的 `ModelRuntime` 接口接入（新增 `Yolov26Runtime` 实现），Java/UI 零改动；
- 推理后端仍为 ncnn 或 OpenCV DNN / ONNX Runtime（Windows 版）。

## 实施步骤（参考主仓库 规划与方案.md 第四节）
1. 确认 YOLOv26 官方权重与导出方式；
2. 抽 `ModelRuntime` 接口，迁移 v5 逻辑；
3. 导出 YOLOv26 ncnn / ONNX 权重（放入 `assets/`）；
4. 实现 `Yolov26Runtime` 后处理；
5. 复用主仓库的中文标签、状态栏、CSV 落盘、帮助/关于菜单；
6. 安卓 `./gradlew assembleRelease` + Windows PyInstaller/NSIS 打包。

## 许可
沿用主仓库约定（ncnn BSD-3-Clause + 上游 demo 许可）。
