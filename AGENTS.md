# CS144 项目 Agent 配置

## 文件命名规范

| 章节 | 主题 | 文件名 |
|---|---|---|
| 1 | Introduction & IP | `ch01-internet-and-ip.md` |
| 2 | UDP & TCP | `ch02-udp-and-tcp.md` |
| 3 | Routing & Forwarding | `ch03-routing-and-forwarding.md` |
| **4** | **Congestion Control（拥塞控制）** | **`ch04-congestion-control.md`** |
| 5 | Applications & NATs | `ch05-Applications-and-NATs.md` |
| 6 | Routing | `ch06-Routing.md` |
| 7 | Physical & Link Principles | `ch07-Physical-and-Link-Principles.md` |
| 8 | Resource management | `ch08-resource-management.md` |

> ⚠️ ch04 是**拥塞控制**（Congestion Control），不是路由（Routing）。README 第 14 行原本写错了，已纠正。

## 写入路径

- **权威位置**：`~/.minimax/workspace/cs144/`
- **副本位置**：`~/Desktop/CS144/`
- 每次写完用 `cp workspace → Desktop` 同步

## 写入模式

- **append-only**：新 H4/H3 只在文件末尾追加，anchor 用末尾 `---` 或最后一行
- **绝不用中间行作 anchor**：会破坏用户手改的不可见字符
- **图片格式**（README § 📐）：
  - HTML `<img>` 不用 `![]()`
  - `width="70%"` + `style="display: block;"` + `alt="..."`
  - 图和图说之间空一行
  - 图说 `*图：...*`（纯斜体）

## H4 段落缩进规则（句首靠边、延续缩进）

- **句首行**（一段内容的开始 / 句号后的新句子）：**0 缩进**，靠最左边
  - 包括：首段、中间新开段、末段
  - "X 包括 N 个：" / "以下是..." 这类 list intro 也算句首，靠最左边
- **非句首的延续内容**（段内的补充、说明、举例，跟在前一句后面但没开新段）：**2 全角缩进**（`　　`）
  - 实际很少用——多数情况下一个段落就是一个完整句子
- **编号列表 / 无序列表**：**0 缩进**
- **代码块**：4 半角空格 + ` ```text `

```
[H4 标题]
                          ← 空行
首段内容 0 缩进            ← 靠最左边
                          ← 空行
句首新段 0 缩进            ← 靠最左边
非句首的延续 　　2 全角缩进
                          ← 空行
末段内容 0 缩进            ← 靠最左边
```

**示例**（公平分配问题 H4）：
- 首段："当多个流共享一个瓶颈资源时..." → 0 缩进（句首）
- 第二段："一种直观的公平分配方式..." → 0 缩进（句首）
- 第三段："在单个瓶颈链路的简单情况下，最大最小公平意味着：" → 0 缩进（句首 + list intro）
- list items → 0 缩进

**判断口诀**：这一行是「新句子的开始」还是「上一句的延续」？前者靠边，后者缩进。

**为什么这样**：句首行靠最左边让视觉节奏清晰，读者一眼能扫到段落的"主题起点"；只有真正"挂在前一句后面"的延续内容才用 `　　` 缩进，作为视觉软连接。
