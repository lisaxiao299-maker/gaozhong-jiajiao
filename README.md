# 高中教学 · 学习入口

给孩子用的高中辅导资源导航页，手机/平板打开即用。

**在线地址**：https://lisaxiao299-maker.github.io/gaozhong-jiajiao/

## 目录

| 路径 | 内容 | 来源 | 许可证 |
|---|---|---|---|
| `index.html` | 导航首页（移动端优先，支持深浅色） | 本仓库 | — |
| `taxonomy/` | 中小学·高中知识图谱 + 自适应诊断 + 题库 | [cn-math-taxonomy](https://github.com/xiaoyang111222/cn-math-taxonomy) | CC BY-NC 4.0 |

其余入口（K12 图谱全景、物理仿真、Anki 教程、理科笔记、OI Wiki）**直接链接官方站点**，不在本仓库转载：

- K12 图谱：https://bewho.github.io/China-K12-knowledge-taxonomy/ （仓库未声明许可证）
- 物理仿真：https://lisa94destiny.github.io/physics-simulation/ （仓库未声明许可证）
- Anki 高考手册：https://github.com/L-M-Sherlock/AnkigaokaoTutorial
- 理科知识体系：https://github.com/Ayvytr/KnowledgeHierarchy
- OI Wiki：https://oi-wiki.org/

## 部署方式

GitHub Pages，`main` 分支根目录，纯静态、无需构建。

## 更新 taxonomy 镜像

```bash
cd /mnt/data/ai家教/高中教学/cloud/gaozhong-jiajiao
rm -rf /tmp/cnmath && git clone --depth 1 https://github.com/xiaoyang111222/cn-math-taxonomy.git /tmp/cnmath
rsync -a --delete \
  --exclude='.git' --exclude='screenshots' --exclude='scripts' \
  --exclude='tests' --exclude='.github' \
  /tmp/cnmath/ taxonomy/
git add -A && git commit -m "sync taxonomy $(date +%F)" && git push
```

## 许可与署名

- `taxonomy/` 内容版权归 [xiaoyang111222/cn-math-taxonomy](https://github.com/xiaoyang111222/cn-math-taxonomy) 作者所有，
  以 **CC BY-NC 4.0** 授权用于个人学习与教学，**不得商用**（付费课程、付费 App、机构收费服务需单独授权）。
  本仓库仅作家庭自用的镜像，未修改内容。
- 导航页 `index.html` 为本仓库原创。
