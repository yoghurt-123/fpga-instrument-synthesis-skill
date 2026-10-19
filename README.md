# FPGA Instrument Synthesis Skill

可复用的中文AI skill：根据参考WAV与现有RTL，生成、调整和验证低存储的钢琴与电吉他音色。

入口：[SKILL.md](skills/fpga-instrument-synthesis/SKILL.md)

覆盖分音DDS、独立包络、吉他清音与过载、和弦混音、定点运算和音频输出验证。它是工作方法，不是开箱即用的完整FPGA工程；不附第三方录音、烧录文件或未经核验的提取参数。

## 使用

Codex：把 `skills/fpga-instrument-synthesis` 整个目录放到本机的 `~/.codex/skills/` 下，在新会话中调用：

> 使用 $fpga-instrument-synthesis，读取我的工程和参考WAV，先优化一个电吉他E2清音的起音，保留现有过载效果。先生成试听，确认后再改RTL。

DeepSeek等其他助手：提供SKILL.md和与任务有关的references文件，明确工程路径、参考音频和本次目标。助手需具备文件读取/代码执行能力，才能实际分析WAV或修改工程。

建议先改一个音并试听，再扩展到其他音、和弦和曲目。不要只比较音量，也不要把编译通过当成听感达标。

## 内容

近期记录与计划（不等同于已实现功能）：

- [四和弦音高身份修复](docs/chord-identity-repair-20261019.md)：独立槽参数、品位与表情资格、统一提交；区分音高与Fmax问题。
- [架子鼓实时合成计划](docs/drum-synthesis-plan-20261019.md)：WAV提取、模态与噪声算法、定点资源、三乐器并发和网口。

- `wav-analysis.md`：起音对齐、单位统一、分音和衰减参数提取。
- `piano.md`：钢琴音色、音符和复音。
- `guitar.md`：清音、拨弦、弦号与品位、过载和尾音。
- `rtl-validation.md`：定点数、计算资源、输出和验证。
- `project-context.md`：已有项目经验，注明哪些参数只是历史实例。

音源链接仅作来源索引；使用或分发第三方素材前核对其许可。
