<!-- Improved compatibility of back to top link -->
<a id="readme-top"></a>

<!-- PROJECT SHIELDS -->
[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]

<!-- PROJECT LOGO -->
<br />
<div align="center">
  <h3 align="center">🌙 Lucid</h3>
  <p align="center">
    多模态 AR 白日梦平台 — 让现实世界变成一首实时谱曲的梦境
    <br />
    环境视觉 · 听觉 · 脑电 · 音乐 → 半透明韵律视觉场
  </p>
</div>

## 理念

Lucid 不是"根据环境生成音乐"的播放器，而是一个**多模态实时融合的 AR 体验平台**：

```
👁️ 视觉(Camera)              │
👂 听觉(Mic)                  │── Fusion Engine ──▶  🥽 半透明滤镜/overlay
🧠 脑电(EEG)                  │                     🎧 空间音频
🎵 音乐(muon-beatcraft)      │                     ⏱️ 韵律驱动一切
```

把现实世界模糊成一首可漫步其中的曲子。

## 核心设计

- **韵律是基础设施** — beatcraft 节拍信号驱动视觉变换
- **脑电是调制层** — 专注度→密度，放松度→速度，情绪→色调
- **视觉是最终输出** — 炫彩眼镜的半透 OLED/MicroLED，不显示文字

## 架构

```
INPUTS                         FUSION                         OUTPUTS
────────────────────────────────────────────────────────────────────
👁️ 视觉 (Camera)           │                               │
   - 场景/颜色/光照         │                               │  🥽 AR Overlay
   - 人流/物体检测          │      Fusion Engine            │     - 颜色场 (拍点呼吸)
   - 姿态/运动              │      (每帧实时)              │     - 粒子系统 (节拍触发)
                            │                               │     - 场景变形 (EEG调制)
👂 听觉 (Mic)              │    视觉+听觉+脑电+音乐        │     - AR元素 (淡入现实)
   - 环境音分类/声场定位    │     → 状态向量                │
   - 节奏提取               │     → 韵律信号                │  🎧 空间音频
                            │     → 输出渲染矩阵            │     - 环境采样→合成器
🧠 脑电 (EEG)              │                               │     - muon-beatcraft 音乐
   - 专注/放松             │                               │     - 脑电→音色调制
   - 情绪效价 (valence)    │                               │
                            │                               │  ⏱️ 韵律
🎵 muon-beatcraft          │     HARDWARE                   │     - 视觉切换锁定拍点
   - BPM/节拍              │     - 炫彩AR眼镜               │     - 沉浸强度 = f(EEG)
   - 和弦进行              │     - bone conduction耳机      │
   - 段落结构              │     - 消费级EEG (v2)          │
```

## 一个场景

> 戴上眼镜出门。步频 → 底鼓节奏。树叶沙沙声 → 合成器音色。人群距离 → 人声切片打击乐密度。晚霞色温 → 和弦进行（暖色=大调上行，冷色=小调下行）。EEG 专注度 → overlay 密度随注意力起伏。
>
> **结束时，今天的路线被保存为一首曲子 + 一段 visual recap。**

## 技术栈

| 要素 | 方案 | 状态 |
|------|------|------|
| 音乐引擎 | muon-beatcraft | ✅ 已有 |
| 端侧推理 | MiniCPM5-1B | 🔍 评估中 |
| AR 眼镜 | 炫彩 AR (IMU + Camera) | 🟡 待定 |
| 脑电 (v2) | 消费级 EEG | 🔴 待定 |

## Roadmap

- [x] 概念验证
- [ ] **MVP**: 环境光→音乐→视觉 overlay 原型（无脑电）
- [ ] v1: EEG 调制层
- [ ] v2: 多人共感体验
- [ ] 开源发布

## License

MIT © MUON | 默川

<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- MARKDOWN LINKS -->
[contributors-shield]: https://img.shields.io/github/contributors/ToussaintKnight/lucid.svg?style=for-the-badge
[contributors-url]: https://github.com/ToussaintKnight/lucid/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/ToussaintKnight/lucid.svg?style=for-the-badge
[forks-url]: https://github.com/ToussaintKnight/lucid/network/members
[stars-shield]: https://img.shields.io/github/stars/ToussaintKnight/lucid.svg?style=for-the-badge
[stars-url]: https://github.com/ToussaintKnight/lucid/stargazers
[issues-shield]: https://img.shields.io/github/issues/ToussaintKnight/lucid.svg?style=for-the-badge
[issues-url]: https://github.com/ToussaintKnight/lucid/issues
[license-shield]: https://img.shields.io/github/license/ToussaintKnight/lucid.svg?style=for-the-badge
[license-url]: https://github.com/ToussaintKnight/lucid/blob/master/LICENSE
