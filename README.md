# Ziyang Ye (叶子扬)

🌐 <https://ziyang-ye.github.io/> ・ 📄 [CV](files/CV_ZiyangYe.pdf) ・ ✉️ yeziyang777@gmail.com

## 研究简介

聚焦视频世界模型（Video World Model）与世界-动作模型（WAM）：让生成模型不止于"看起来像"，而是成为可以被进入、被操纵、被托付决策的世界。

**LIVE** 重写了自回归视频生成的训练范式。长时序生成的真正敌人不是画质，而是模型踩进自己的预测里越走越偏。LIVE 以 cycle-consistency 为训练目标——先无梯度地向前 rollout，再沿动作与相机信号反向重构，用 flow-matching 监督把轨迹拉回真实起点——把误差累积约束在闭环之内，在 256 帧 rollout 上取得 SOTA，已被 ICML 2026（CCF-A）录用，目前正扩展至更大规模视频基座（Wan）并引入记忆机制。

**WorldCast** 是首个分布式多玩家世界模型。单人可玩的生成世界只是 demo，真正的考验是联机：多名玩家在同一个被生成出来的场景里同时行动、彼此可见、各自拥有私有视角。WorldCast 不靠一个中心模型替所有人渲染，而是让每个玩家在本地各跑一份世界模型，以网络速度互发显式状态、把彼此的模型状态直接连起来——这是联机游戏沿用多年的状态同步思路，第一次被搬到生成模型上。配合场景时间同步与共享隐式记忆，它在多人同时施加动作时维持跨视角一致性；指向的终点，是 CS 式的联机对战直接跑在生成模型之上，而不是跑在手写的游戏引擎里。（ICLR 2027 在投）

**Iso-WAM** 解决世界模型"会看不会动"的问题。像素级预测天然把物理动态和无关外观缠在一起，换一套光照或背景，策略就把外观变化误读成状态变化。Iso-WAM 以动态信息瓶颈把可执行动态从视觉外观中剥离，将 DINOv3 的语义状态转移与 VGGT 的时空几何转移统一为一套隐式动作表征，让模型预测的是"控制一致的未来变化"而非"视觉一致的静态未来"，在 LIBERO-Plus 与真机的分布外场景下显著提升控制鲁棒性。（ICLR 2027 在投）

三项工作对应世界模型的三种形态：能长时序自持演化的模拟器、能多人共享并联机的可玩世界、能驱动具身体去行动的控制引擎。下一步是把它们收敛成同一个模型——在同一套表征里完成预测、交互与行动，让"想象出的未来"既可以被玩，也可以被执行。

---

<details>
<summary>本站基于 AcadHomepage 模板构建，以下为模板原始说明</summary>

<h1 align="center">
AcadHomepage
</h1>

<div align="center">

[![](https://img.shields.io/github/stars/RayeRen/acad-homepage.github.io)](https://github.com/RayeRen/acad-homepage.github.io)
[![](https://img.shields.io/github/forks/RayeRen/acad-homepage.github.io)](https://github.com/RayeRen/acad-homepage.github.io)
[![](https://img.shields.io/github/issues/RayeRen/acad-homepage.github.io)](https://github.com/RayeRen/acad-homepage.github.io)
[![](https://img.shields.io/github/license/RayeRen/acad-homepage.github.io)](https://github.com/RayeRen/acad-homepage.github.io/blob/main/LICENSE)  | [中文文档](./docs/README-zh.md) 
</div>

<p align="center">A Modern and Responsive Academic Personal Homepage</p>

<p align="center">
    <br>
    <img src="docs/screenshot.png" width="100%"/>
    <br>
</p>

Some examples:
- [Demo Page](https://rayeren.github.io/acad-homepage.github.io/)
- [Personal Homepage of the author](https://rayeren.github.io/)

## Key Features
- **Automatically update google scholar citations**: using the google scholar crawler and github action, this REPO can update the author citations and publication citations automatically.
- **Support Google analytics**: you can trace the traffics of your homepage by easy configuration.
- **Responsive**: this homepage automatically adjust for different screen sizes and viewports.
- **Beautiful and Simple Design**: this homepage is beautiful and simple, which is very suitable for academic personal homepage.
- **SEO**: search Engine Optimization (SEO) helps search engines find the information you publish on your homepage easily, then rank it against similar websites.

## Quick Start

1. Fork this REPO and rename to `USERNAME.github.io`, where `USERNAME` is your github USERNAME.
1. Configure the google scholar citation crawler:
    1. Find your google scholar ID in the url of your google scholar page (e.g., https://scholar.google.com/citations?user=SCHOLAR_ID), where `SCHOLAR_ID` is your google scholar ID.
    1. Set GOOGLE_SCHOLAR_ID variable to your google scholar ID in `Settings -> Secrets -> Actions -> New repository secret` of the REPO website with `name=GOOGLE_SCHOLAR_ID` and `value=SCHOLAR_ID`.
    1. Click the `Action` of the REPO website and enable the workflows by clicking *"I understand my workflows, go ahead and enable them"*. This github action will generate google scholar citation stats data `gs_data.json` in `google-scholar-stats` branch of your REPO. When you update your main branch, this action will be triggered. This action will also be trigger 08:00 UTC everyday.
1. Generate favicon using [favicon-generator](https://redketchup.io/favicon-generator) and download all generated files to `REPO/images`.
1. Modify the configuration of your homepage `_config.yml`:
    1. `title`: the title of your homepage
    1. `description`: the description of your homepage
    1. `repository`: USER_NAME/REPO_NAME  
    1. `google_analytics_id` (optional): google analytics ID
    1. SEO Related keys (optional): get these keys from search engine consoles (e.g. Google, Bing and Baidu) and paste here.
    1. `author`: the author information of this homepage, including some other websites, emails, city and univeristy.
    1. More configuration details are described in the comments.
1. Add your homepage content in `_pages/about.md`.
    1. You can use html+markdown syntax just same as jekyll.
    1. You can use a `<span>` tag with class `show_paper_citations` and attribute `data` to display the citations of your paper. Set the data to the google scholar paper ID. For
        ```html
        <span class='show_paper_citations' data='DhtAFkwAAAAJ:ALROH1vI_8AC'></span>
        ``` 
        > Q: How to get the google scholar paper ID?   
        > A: Enter your google scholar homepage and click the paper name. Then you can see the paper ID from `citation_for_view=XXXX`, where `XXXX` is the required paper ID.
1. Your page will be published at `https://USERNAME.github.io`.

## Debug Locally

1. Clone your REPO to local using `git clone`.
1. Install Jekyll building environment, including `Ruby`, `RubyGems`, `GCC` and `Make` following [the installation guide](https://jekyllrb.com/docs/installation/#requirements).
1. Run `bash run_server.sh` to start Jekyll livereload server.
1. Open http://127.0.0.1:4000 in your browser.
1. If you change the source code of the website, the livereload server will automatically refresh.
1. When you finish the modification of your homepage, `commit` your changings and `push` to your remote REPO using `git` command.

# Acknowledges

- AcadHomepage incorporates Font Awesome, which is distributed under the terms of the SIL OFL 1.1 and MIT License.
- AcadHomepage is influenced by the github repo [mmistakes/minimal-mistakes](https://github.com/mmistakes/minimal-mistakes), which is distributed under the MIT License.
- AcadHomepage is influenced by the github repo [academicpages/academicpages.github.io](https://github.com/academicpages/academicpages.github.io), which is distributed under the MIT License.

</details>
