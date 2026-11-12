---
name: knowledge-base-skill
description: 评审并发布跨组通用的公共知识，运行时按需检索公共层、候选不进检索。当用户要「提交公共候选」「发布跨组知识」「查一下通用机制」时使用。覆盖判别、候选、校验、发布，以及公共索引的读取和评审更新；不覆盖私有草稿与任何工作组目录。触发词：提交公共候选、发布知识包、查公共知识、publish knowledge。
agent_created: true
version: 1.0.0
---

# 公共知识包

只写 `knowledge-base/knowledge/`，不读私有草稿，不写任何工作组目录；跨组评审担保。

## 流程一 · 判断怎么进这一层

1. **判别**：跨组稳定、脱离来源项目仍可理解的机制、术语、对象关系、通用模式才进包；某工程的目录和表、临时脚本、单次复盘、原始日志留在组里。不确定标 `needs_revision`。
2. **候选**：按 `scope: base`、`status: pending` 写入 `pending/`，附 `review_notes`。
3. **校验**：确认六个正式分类、`pending/`、`index/` 齐全，且候选没提前进 `index/`；缺一项不发布。
4. **发布**：评审通过后物理移入正式分类，改 `status: published`，加入 `index/documents.json`。

## 流程二 · 运行时这一层怎么被用

1. 团队层没命中、或需要跨组通用背景时，才查 `knowledge-base/knowledge/index/documents.json`，再读正文。
2. `pending/` 是待审区，不进索引、不参与默认检索；读到也不当定论引用。
3. 与当前代码对不上，说明公共条目过期：提更新意见、走评审再改，不就地改，也不退回草稿。
4. 作废必须指向替代条目，不允许无声下架。

不写凭据、完整日志、本机路径、真实项目标识。
