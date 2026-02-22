# GitHub Organization Profile README 创建计划

## TL;DR

> **Quick Summary**: 为 token-is-token GitHub 组织创建多语言品牌营销型 README 文件，包含中文、英文、日语、韩语四个版本，用于组织首页展示。
> 
> **Deliverables**:
> - `profile/README.md` (中文，默认展示)
> - `profile/README_EN.md` (英文)
> - `profile/README_JA.md` (日语)
> - `profile/README_KO.md` (韩语)
> - 语言切换导航与占位符社交链接
> 
> **Estimated Effort**: Short
> **Parallel Execution**: YES - 4 waves
> **Critical Path**: Task 1 → Task 2-5 (并行)

---

## Context

### Original Request
用户需要为 token-is-token GitHub 组织创建组织首页说明文件，展示项目的愿景、功能、架构等核心信息，支持多语言版本。

### Interview Summary
**Key Discussions**:
- **语言版本**: 中文（默认）+ 英文 + 日语 + 韩语
- **内容风格**: 品牌营销型，强调市场机会与商业价值
- **合规措辞**: 弱化"突破限制"等敏感表述，使用"全球可用性/低摩擦结算"
- **外部链接**: 使用占位符（# 或 Coming Soon）

**Research Findings**:
- GitHub 组织主页通过 `.github` 仓库的 `profile/README.md` 渲染
- 只有一个 README 会自动展示，其他语言需通过导航链接切换
- 项目基于 0G Chain 构建，核心口号："Token（LLM）即 Token（ERC20）"

### Metis Review
**Identified Gaps** (addressed):
- **多语言渲染机制**: 明确 profile/README.md 为中文默认，其他语言通过顶部导航切换
- **合规红线**: 弱化敏感表述，不承诺"绕过限制"的确定性结果
- **可变信息**: Tokenomics/比例/模型清单标注为"当前设计/拟议"
- **验收标准**: 使用可执行的 bash 命令校验文件存在与关键词

---

## Work Objectives

### Core Objective
创建专业、一致的多语言 GitHub 组织首页 README，展示 LLM API Share Network 的愿景、价值主张、技术架构与代币经济。

### Concrete Deliverables
- `profile/README.md` - 中文版（默认展示在组织首页）
- `profile/README_EN.md` - 英文版
- `profile/README_JA.md` - 日语版
- `profile/README_KO.md` - 韩语版

### Definition of Done
 [x] 4个 README 文件创建完成
 [x] 所有文件包含语言切换导航
 [x] 核心口号与关键信息出现
 [x] 关键段落结构一致（Opportunity / How it works / Token / Tech / Social）
 [x] bash 验收命令全部通过

### Must Have
- 四种语言版本完整
- 每个版本顶部有语言切换链接
- 包含愿景、价值主张、技术架构、代币经济、社交链接占位
- 使用合规措辞

### Must NOT Have (Guardrails)
- 不新增白皮书、路线图、融资材料
- 不承诺"绕过限制"的确定性结果
- 不编造合作方、用户规模、性能指标
- 不放实际的合约地址（除非用户提供）
- 不创建技术实现文档

---

## Verification Strategy (MANDATORY)

### Test Decision
- **Infrastructure exists**: NO (文档任务，无需测试框架)
- **Automated tests**: None
- **Framework**: N/A
- **Agent-Executed QA**: YES - 使用 bash 命令验证

### QA Policy
每个任务包含 agent-executed QA scenarios，使用 bash 命令验证文件存在性与内容完整性。

---

## Execution Strategy

### Parallel Execution Waves

```
Wave 1 (Start Immediately — 基础结构):
├── Task 1: 创建 profile 目录结构 [quick]

Wave 2 (After Wave 1 — 内容创建，MAX PARALLEL):
├── Task 2: 创建中文 README (profile/README.md) [writing]
├── Task 3: 创建英文 README (profile/README_EN.md) [writing]
├── Task 4: 创建日语 README (profile/README_JA.md) [writing]
└── Task 5: 创建韩语 README (profile/README_KO.md) [writing]

Wave 3 (After Wave 2 — 验证):
└── Task 6: 文件验证与一致性检查 [quick]

Critical Path: Task 1 → Task 2-5 → Task 6
Parallel Speedup: 4个语言版本并行创建
Max Concurrent: 4 (Wave 2)
```

### Dependency Matrix

- **1**: — — 2-5
- **2-5**: 1 — 6
- **6**: 2-5 — —

### Agent Dispatch Summary

- **Wave 1**: **1** — T1 → `quick`
- **Wave 2**: **4** — T2-T5 → `writing`
- **Wave 3**: **1** — T6 → `quick`

---

## TODOs

 [x] 1. **创建 profile 目录结构**

  **What to do**:
  - 创建 `profile/` 目录
  - 确认目录结构正确

  **Must NOT do**:
  - 不创建任何其他内容文件或代码目录
  - 注意：可以创建 .sisyphus/evidence/ 目录用于存放 QA 证据

  **Recommended Agent Profile**:
  - **Category**: `quick`
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: NO
  - **Parallel Group**: Wave 1
  - **Blocks**: Tasks 2-5
  - **Blocked By**: None

  **Acceptance Criteria**:
  - [ ] profile/ 目录存在

  **QA Scenarios**:
  ```
  Scenario: Directory created
    Tool: Bash
    Steps:
      1. test -d profile/ && echo "OK"
    Expected Result: "OK"
    Evidence: .sisyphus/evidence/task-1-dir-created.txt
  ```

  **Commit**: NO

 [x] 2. **创建中文 README (profile/README.md)**

  **What to do**:
  - 创建品牌营销风格的中文 README
  - 包含以下结构：
    - 语言切换导航（顶部）
    - 项目 Logo 与口号
    - 愿景与使命
    - 市场机会
    - 核心价值主张
    - 如何工作
    - 代币经济
    - 技术架构
    - 社交链接（占位符）
  - 使用合规措辞（弱化敏感表述）

  **Must NOT do**:
  - 不承诺"绕过限制"的确定性结果
  - 不编造用户规模、性能指标
  - 不放实际合约地址

  **Recommended Agent Profile**:
  - **Category**: `writing`
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 2 (with Tasks 3, 4, 5)
  - **Blocks**: Task 6
  - **Blocked By**: Task 1

  **References**:
  - `.prompts/01_business_plan.md` - 商业计划内容
  - `.prompts/LLM_API_Share_Network_完整白皮书.md` - 完整白皮书
  - `.prompts/02_technical_architecture.md` - 技术架构
  - `.prompts/03_blockchain_tokenomics.md` - 代币经济

  **Acceptance Criteria**:
  - [ ] 文件存在: profile/README.md
  - [ ] 包含语言切换链接
  - [ ] 核心口号出现: "Token（LLM）即 Token（ERC20）"
  - [ ] 包含所有必要段落

  **QA Scenarios**:
  ```
  Scenario: File exists and has required content
    Tool: Bash
    Steps:
      1. test -f profile/README.md
      2. grep -q "README_EN.md" profile/README.md
      3. grep -q "Token（LLM）即 Token（ERC20）" profile/README.md
    Expected Result: All commands exit 0
    Evidence: .sisyphus/evidence/task-2-cn-readme.txt
  ```

  **Commit**: NO

 [x] 3. **创建英文 README (profile/README_EN.md)**

  **What to do**:
  - 创建品牌营销风格的英文 README
  - 结构与中文版一致
  - 语言切换导航指向其他版本
  - 英文核心口号: "Token (LLM) = Token (ERC20)"

  **Must NOT do**:
  - 不承诺特定结果
  - 不编造数据

  **Recommended Agent Profile**:
  - **Category**: `writing`
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 2 (with Tasks 2, 4, 5)
  - **Blocks**: Task 6
  - **Blocked By**: Task 1

  **Acceptance Criteria**:
  - [ ] 文件存在: profile/README_EN.md
  - [ ] 包含语言切换链接
  - [ ] 包含所有必要段落

  **QA Scenarios**:
  ```
  Scenario: English file exists and valid
    Tool: Bash
    Steps:
      1. test -f profile/README_EN.md
      2. grep -qi "0G" profile/README_EN.md
      3. grep -qi "SHARE" profile/README_EN.md
    Expected Result: All commands exit 0
    Evidence: .sisyphus/evidence/task-3-en-readme.txt
  ```

  **Commit**: NO

 [x] 4. **创建日语 README (profile/README_JA.md)**

  **What to do**:
  - 创建品牌营销风格的日语 README
  - 结构与其他版本一致
  - 专业日语翻译，技术名词保留英文（如 0G Chain, libp2p）

  **Must NOT do**:
  - 不承诺特定结果
  - 不编造数据

  **Recommended Agent Profile**:
  - **Category**: `writing`
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 2 (with Tasks 2, 3, 5)
  - **Blocks**: Task 6
  - **Blocked By**: Task 1

  **Acceptance Criteria**:
  - [ ] 文件存在: profile/README_JA.md
  - [ ] 包含语言切换链接
  - [ ] 包含所有必要段落

  **QA Scenarios**:
  ```
  Scenario: Japanese file exists and valid
    Tool: Bash
    Steps:
      1. test -f profile/README_JA.md
      2. grep -q "README.md" profile/README_JA.md
    Expected Result: All commands exit 0
    Evidence: .sisyphus/evidence/task-4-ja-readme.txt
  ```

  **Commit**: NO

 [x] 5. **创建韩语 README (profile/README_KO.md)**

  **What to do**:
  - 创建品牌营销风格的韩语 README
  - 结构与其他版本一致
  - 专业韩语翻译，技术名词保留英文

  **Must NOT do**:
  - 不承诺特定结果
  - 不编造数据

  **Recommended Agent Profile**:
  - **Category**: `writing`
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: YES
  - **Parallel Group**: Wave 2 (with Tasks 2, 3, 4)
  - **Blocks**: Task 6
  - **Blocked By**: Task 1

  **Acceptance Criteria**:
  - [ ] 文件存在: profile/README_KO.md
  - [ ] 包含语言切换链接
  - [ ] 包含所有必要段落

  **QA Scenarios**:
  ```
  Scenario: Korean file exists and valid
    Tool: Bash
    Steps:
      1. test -f profile/README_KO.md
      2. grep -q "README.md" profile/README_KO.md
    Expected Result: All commands exit 0
    Evidence: .sisyphus/evidence/task-5-ko-readme.txt
  ```

  **Commit**: NO

 [x] 6. **文件验证与一致性检查**

  **What to do**:
  - 验证所有4个README文件存在
  - 验证语言切换链接完整
  - 验证核心口号出现
  - 验证段落结构一致性

  **Must NOT do**:
  - 不修改任何文件内容

  **Recommended Agent Profile**:
  - **Category**: `quick`
  - **Skills**: []

  **Parallelization**:
  - **Can Run In Parallel**: NO
  - **Parallel Group**: Wave 3
  - **Blocks**: Final Verification
  - **Blocked By**: Tasks 2-5

  **Acceptance Criteria**:
  - [ ] 4个文件全部存在
  - [ ] 所有语言切换链接有效
  - [ ] 核心口号出现在中文版

  **QA Scenarios**:
  ```
  Scenario: All files verified
    Tool: Bash
    Steps:
      1. test -f profile/README.md && test -f profile/README_EN.md && test -f profile/README_JA.md && test -f profile/README_KO.md
      2. grep -q "README_EN.md" profile/README.md && grep -q "README_JA.md" profile/README.md && grep -q "README_KO.md" profile/README.md
      3. grep -q "Token（LLM）即 Token（ERC20）" profile/README.md
    Expected Result: All commands exit 0
    Evidence: .sisyphus/evidence/task-6-verification.txt
  ```

  **Commit**: YES
  - Message: `docs(profile): add multi-language organization profile README`
  - Files: `profile/*.md`

---

## Final Verification Wave

 [x] F1. **Plan Compliance Audit** — `quick`
  验证所有文件存在，语言切换链接有效，核心口号出现，段落结构完整。
  Output: `Files [4/4] | Links [PASS] | Slogan [PASS] | Structure [PASS] | VERDICT: APPROVE`
  Output: `Files [4/4] | Links [PASS] | Slogan [PASS] | Structure [PASS] | VERDICT: APPROVE/REJECT`

---

## Commit Strategy

- **1**: `docs(profile): add multi-language organization profile README` — profile/*.md

---

## Success Criteria

### Verification Commands
```bash
# 文件存在性检查
test -f profile/README.md && echo "CN OK"
test -f profile/README_EN.md && echo "EN OK"
test -f profile/README_JA.md && echo "JA OK"
test -f profile/README_KO.md && echo "KO OK"

# 语言切换链接检查
grep -q "README_EN.md" profile/README.md && echo "EN link OK"
grep -q "README_JA.md" profile/README.md && echo "JA link OK"
grep -q "README_KO.md" profile/README.md && echo "KO link OK"

# 核心口号检查
grep -q "Token（LLM）即 Token（ERC20）" profile/README.md && echo "Slogan OK"
```

### Final Checklist
 [x] 4个语言版本文件存在
 [x] 语言切换链接完整
 [x] 核心口号出现
 [x] 段落结构一致
 [x] 合规措辞使用正确
