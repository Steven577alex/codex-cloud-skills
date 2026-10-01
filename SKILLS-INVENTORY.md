# Codex Skills Inventory

本清单记录当前仓库内从两个公开仓库迁移并审核的 Codex/Agent Skills。所有安装项均位于 `.agents/skills/<skill-name>/SKILL.md`；源仓库的安装脚本**未执行、未复制**。

## 来源与审核基线

| 来源仓库 | 审核提交 | 许可证 | 安装数 | 迁移说明 |
|---|---|---|---:|---|
| [xbtlin/ai-berkshire](https://github.com/xbtlin/ai-berkshire) | `55be4f77ba9c1aeb0cfb98c0eed78babc2433706` | MIT | 22 | 优先采用上游 `codex-skills/`；按 Skill 实际引用捆绑 `tools/*.py` 到各自 `scripts/`，并将调用路径改为相对 Skill 定位。 |
| [makinotes/elab-trading-skills](https://github.com/makinotes/elab-trading-skills) | `b5fb111a3ba1da8027aa4c6200b386d1218ad131` | CC-BY-NC-4.0 | 12 | 保留各 Skill 的 `scripts/`、`references/`、`agents/`；把套件级 `_shared/` 捆绑为各 Skill 的 `references/shared/`，避免依赖安装目录外的隐式路径。 |

## AI Berkshire Skills（22）

| Skill | 安装路径 | 依赖说明 |
|---|---|---|
| `bottleneck-hunter` | `.agents/skills/bottleneck-hunter/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py`, `twstock_data.py` |
| `deep-company-series` | `.agents/skills/deep-company-series/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py` |
| `dyp-ask` | `.agents/skills/dyp-ask/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py` |
| `earnings-review` | `.agents/skills/earnings-review/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py`, `report_audit.py`, `twstock_data.py` |
| `earnings-team` | `.agents/skills/earnings-team/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py`, `report_audit.py` |
| `era-alpha` | `.agents/skills/era-alpha/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py` |
| `financial-data` | `.agents/skills/financial-data/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py`, `twstock_data.py` |
| `income-investment` | `.agents/skills/income-investment/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py`, `report_audit.py` |
| `industry-funnel` | `.agents/skills/industry-funnel/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py`, `report_audit.py` |
| `industry-research` | `.agents/skills/industry-research/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py`, `report_audit.py` |
| `investment-checklist` | `.agents/skills/investment-checklist/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py` |
| `investment-memo-craft` | `.agents/skills/investment-memo-craft/SKILL.md` | Python 3（标准库）；无必需脚本 |
| `investment-research` | `.agents/skills/investment-research/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py`, `report_audit.py`, `terminal_value.py` |
| `investment-team` | `.agents/skills/investment-team/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py`, `report_audit.py`, `twstock_data.py` |
| `management-deep-dive` | `.agents/skills/management-deep-dive/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py` |
| `news-pulse` | `.agents/skills/news-pulse/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py`, `xueqiu_scraper.py`；该可选抓取器另需 `playwright` 与浏览器运行时，并仅在用户要求抓取雪球时运行 |
| `portfolio-review` | `.agents/skills/portfolio-review/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py` |
| `private-company-research` | `.agents/skills/private-company-research/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py` |
| `quality-screen` | `.agents/skills/quality-screen/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py` |
| `thesis-drift` | `.agents/skills/thesis-drift/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py` |
| `thesis-tracker` | `.agents/skills/thesis-tracker/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py` |
| `wechat-article` | `.agents/skills/wechat-article/SKILL.md` | Python 3（标准库）；捆绑脚本：`financial_rigor.py` |

## EdgeLab Skills（12）

| Skill | 安装路径 | 依赖说明 |
|---|---|---|
| `elab` | `.agents/skills/elab/SKILL.md` | 路由入口；共享规范已捆绑于 `references/shared/`。 |
| `elab-benchmark` | `.agents/skills/elab-benchmark/SKILL.md` | 无第三方 Python 依赖；共享规范已捆绑。 |
| `elab-coach` | `.agents/skills/elab-coach/SKILL.md` | 自带训练参考资料；本地状态默认写入 `~/.elab/coach/`，写入前遵循用户授权。 |
| `elab-deconstruct` | `.agents/skills/elab-deconstruct/SKILL.md` | 无第三方 Python 依赖；共享规范已捆绑。 |
| `elab-diagnosis` | `.agents/skills/elab-diagnosis/SKILL.md` | 无第三方 Python 依赖；共享规范已捆绑。 |
| `elab-futu-research` | `.agents/skills/elab-futu-research/SKILL.md` | `futu_research.py` 使用 Python 3 标准库联网访问公开页面；仅按用户要求运行，不绕过登录、CAPTCHA 或访问控制。 |
| `elab-model` | `.agents/skills/elab-model/SKILL.md` | Python 3 标准库；`strategy_models.py` 同目录导入 `ev_model.py`；阈值文件 `thresholds.json` 必须保留。 |
| `elab-report` | `.agents/skills/elab-report/SKILL.md` | 依赖由 `elab-save` 创建的本地会话存档。 |
| `elab-research` | `.agents/skills/elab-research/SKILL.md` | 本地脚本使用 Python 3 标准库；会员 API 需用户自行配置受保护 token；OpenBB、yfinance、edgartools 等均为按研究任务选装依赖，不自动安装。 |
| `elab-restore` | `.agents/skills/elab-restore/SKILL.md` | 依赖现有 `~/.elab/sessions/` 存档。 |
| `elab-save` | `.agents/skills/elab-save/SKILL.md` | `session_store.py` 需 Python 3.9+ 和 POSIX 安全文件操作；只在用户要求保存时写入 `~/.elab/sessions/`。 |
| `elab-trade` | `.agents/skills/elab-trade/SKILL.md` | 可选券商连接器需用户授权、各自官方客户端/凭据；默认不安装、不连接、不下单。 |

## 兼容性调整与安全结论

1. **Frontmatter**：每个已安装 `SKILL.md` 均保留且规范化为 Codex 所需的 `name` 与 `description`；目录名与 `name` 一致。
2. **资源自包含**：AI Berkshire 原先指向仓库根 `tools/` 的脚本改为 Skill 内 `scripts/`；EdgeLab 原先指向套件根 `_shared/` 的文件改为 Skill 内 `references/shared/`。这样从 `.agents/skills/` 单独加载时不会丢依赖。
3. **平台兼容**：保留 AI Berkshire 的 Codex adapter，并把 `investment-team` 中读取 `.claude/settings.local.json`、`/permissions` 的 Claude 专属预检改为 Codex 的联网能力预检；无法使用协作 Agent 时要求在当前线程顺序执行。
4. **依赖**：绝大多数捆绑脚本只用 Python 标准库。唯一明确的额外运行依赖是 AI Berkshire `news-pulse` 的可选 `xueqiu_scraper.py`（`playwright`）；EdgeLab 外部市场数据包和券商客户端均保持按需可选，不做静默安装。
5. **脚本安全**：未执行任何源仓库安装/更新脚本。保留的脚本主要进行数值计算、受限网络读取或用户明确要求的本地状态保存；网络、凭据和文件写入能力均在对应 Skill 中受授权/路径约束。`financial_rigor.py` 的表达式计算使用禁用 builtins 的受限 `eval`，只应传入数值算式。

## 跳过项

- EdgeLab `skill-template/SKILL.md` 是含 `<功能>`、`YYYY-MM-DD` 等占位符的开发模板，不是可调用 Skill，缺少合法的最终名称与说明，因此未安装。
- 两个仓库的安装器、自动更新脚本、测试夹具、示例报告和项目级文档不属于单个 Skill 的运行资源，且安装器会修改用户全局配置或目录，因此未复制、未执行。
