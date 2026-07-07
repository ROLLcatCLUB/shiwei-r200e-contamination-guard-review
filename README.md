# 1013R R200E Frontend Visible Contamination Guard Review

This is a GPT/human review package for the R200E guard added after the R200D audit.

The user-reported problem is serious:

```text
When testing a 足下生辉 upload, teacher-visible sections appeared to contain unrelated material such as 海洋生物, 拼贴/拼板, 材料收集, 废旧材料.
```

The current conclusion is not "the system is fine." The more precise conclusion is:

```text
R200E can now capture frontend-visible text and source ownership.
The latest local R103 replay samples do not show deny-list terms in teacher main text.
However, historical P2D evidence confirms a real contamination path:
garbled or thin upload input -> focus misclassification -> R200A kernel writes teacher-visible main text.
```

## What Is Included

- `source/validate_1013r_r200e_frontend_visible_contamination_guard.py`
  - New validator.
  - Captures frontend-visible text from R103 response, not only backend template structure.

- `validation/validate_1013R_R200E_frontend_visible_contamination_guard_result.json`
  - Latest R200E result.

- `validation/contamination_hit_report.md`
  - Human-readable summary.

- `evidence/frontend_visible_text_snapshot.json`
  - Per-case visible text snapshot.

- `evidence/content_source_ledger.json`
  - Source ledger for visible text.

- `evidence/active_lesson_denylist.json`
  - Active deny-lists for lesson focus types.

- `historical_records/p2d_20260707T130733Z_167118fe885a_contamination_excerpt.json`
  - Concrete historical evidence of the reported issue.

- `backend_chain/`
  - R103/R200A/R200B/R200C/R114/R97B_P3 files needed to audit ownership and contamination sources.

## Latest R200E Result

```text
status: PASS
case_count: 6
teacher_main_hit_count: 0
default_visible_hit_count: 0
source_policy_violation_count: 0
```

But the ownership statistics are the important part:

```text
teacher_main_text_count: 981
R200A_kernel: 744
uploaded_source: 207
R114_field_projection: 30
```

This means most teacher-visible main text is currently written by `R200A_kernel`, not by uploaded source or R114 graph projection.

## Historical Contamination Evidence

See:

```text
historical_records/p2d_20260707T130733Z_167118fe885a_contamination_excerpt.json
```

Key facts:

```text
record_id: p2d_20260707T130733Z_167118fe885a
model_called: false
template_episode_count: 0
lesson_focus_id: material_transformation_expression
lesson_focus_matched_keywords: ["材料"]
```

The record's `student_analysis` contains:

```text
剪贴、拼摆或材料收集
海洋生物特征
废旧材料
```

This happened without model calls. That strongly points to deterministic/kernel generation, especially R200A, rather than provider prompt output.

## Audit Questions

1. Should R200A be allowed to overwrite `basis`, `student_analysis`, `objectives`, and `key_difficult_points`?
2. When title/text parsing is garbled or the upload has no episodes, should R200A be blocked from writing teacher main text?
3. Should R200A output move to diagnostics/candidate-only instead of main teacher-visible sections?
4. Should R114 graph projection become the only allowed source for formal preview main text?
5. Should R103 enforce a source ownership policy before returning frontend-visible response?
6. Does the R200E source ledger still classify too broadly, or is it enough for R200F/G planning?

## Recommended Next Stage

```text
1013R_R200F_SOURCE_AND_OWNERSHIP_POLICY
```

Expected rule:

```text
uploaded_source / R114_graph / R114_field_projection may enter main text.
R200A_kernel may only enter diagnostic/candidate/teacher-review sections until source confidence is high.
R200B_candidate remains candidate-only.
deterministic_fallback remains folded or marked as source_gap.
legacy_shell remains blocked.
```

## Boundary

```text
preview only
no formal apply
no database write
no Feishu/memory write
no model call
no export
no R21/R36 modification
```

