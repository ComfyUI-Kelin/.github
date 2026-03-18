# ComfyUI-Kelin 分类规范

这个文件用于统一 `ComfyUI-Kelin` 组织下私有 ComfyUI 节点仓库的分类写法。

目标只有两个：

- 在 ComfyUI 前端中更快找到节点
- 让不同私有仓库的分类风格保持一致

## 一级分类规则

所有私有节点统一使用同一个一级分类前缀：

`🚦 ComfyUI-Kelin`

规则：

- 一级分类必须带 `🚦`
- 一级分类必须写成 `ComfyUI-Kelin`
- 不再给每个仓库单独发明一套一级分类名字

标准写法：

```python
CATEGORY = "🚦 ComfyUI-Kelin/xxx"
```

## 二级分类规则

二级分类不加 emoji，只写功能本身。

规则：

- 二级分类必须是纯功能名
- 尽量短、清晰、稳定
- 一个节点归到“它主要解决的问题”里，而不是按模型名或项目名随意拆分

推荐二级分类：

- `api`
- `image`
- `mask`
- `video`
- `audio`
- `text`
- `json`
- `dataset`
- `save`
- `iterator`
- `loader`
- `utility`

标准示例：

```python
CATEGORY = "🚦 ComfyUI-Kelin/api"
CATEGORY = "🚦 ComfyUI-Kelin/image"
CATEGORY = "🚦 ComfyUI-Kelin/mask"
CATEGORY = "🚦 ComfyUI-Kelin/video"
```

## 分类判断规则

如果一个节点的功能不明显，按“核心用途”归类：

- 主要调用远程服务、配置客户端、发请求：`api`
- 主要做图像生成、图像处理、图像修复：`image`
- 主要处理抠图、透明度、前景背景分离：`mask`
- 主要做视频生成、视频加载、视频轮询、视频处理：`video`
- 主要做语音生成、音频转写、音频处理：`audio`
- 主要处理字符串、模板、提示词、文本流程：`text`
- 主要处理 JSON 构造、提取、修复、迭代：`json`
- 主要做数据集读写、样本整理：`dataset`
- 主要做保存输出：`save`
- 主要做遍历、批次推进、顺序取样：`iterator`
- 主要做模型或客户端加载：`loader`
- 杂项辅助工具：`utility`

## 当前已采用的分类

目前已经统一过的私有仓库：

- `ComfyUI-FastForegroundEstimation` → `🚦 ComfyUI-Kelin/mask`
- `ComfyUI-LightCC-API` → `🚦 ComfyUI-Kelin/image`
- `ComfyUI_WenWen_Nodes`
  - API 设置 → `🚦 ComfyUI-Kelin/api`
  - 图像生成 → `🚦 ComfyUI-Kelin/image`
  - 音频相关 → `🚦 ComfyUI-Kelin/audio`
  - 视频 / Sora / Kling / 视频加载 → `🚦 ComfyUI-Kelin/video`

## 显示名规则

显示名是否带 `🚦`，可以按仓库需要决定。

当前建议：

- 如果你希望在节点搜索里更快看到自己的节点，可以在显示名加 `🚦`
- 但分类规范本身只强制一级分类带 `🚦`

也就是说：

- `NODE_DISPLAY_NAME_MAPPINGS` 是否带 `🚦` 可选
- `CATEGORY` 的一级前缀带 `🚦` 是固定规则

## 不适用范围

这个规范目前只用于：

- `ComfyUI-Kelin` 组织下的私有节点仓库

默认不强制用于：

- 开源仓库
- fork 仓库
- 第三方项目

## 新增节点时的检查清单

新增一个私有节点前，先检查这 4 件事：

1. 一级分类是不是 `🚦 ComfyUI-Kelin`
2. 二级分类是不是明确功能名
3. 二级分类有没有复用已有分类，而不是重新发明名字
4. README 里是否同步写清楚节点所在分类
