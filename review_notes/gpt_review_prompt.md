# GPT Review Prompt

Please review this R200E package as an architecture and quality-control audit.

The immediate user complaint was that a `足下生辉` lesson appeared to include unrelated material such as:

```text
海洋生物
拼贴 / 拼板
材料收集
废旧材料
```

R200E now captures frontend-visible text from the R103 assembled response and labels content-source ownership.

Important evidence:

```text
validation/validate_1013R_R200E_frontend_visible_contamination_guard_result.json
validation/contamination_hit_report.md
historical_records/p2d_20260707T130733Z_167118fe885a_contamination_excerpt.json
```

The latest R200E run passes deny-list checks for the local replay samples, but it also shows teacher-main ownership:

```text
R200A_kernel: 744
uploaded_source: 207
R114_field_projection: 30
```

Please focus on:

1. Whether R200A should be demoted from writing teacher-visible main text.
2. Whether R103 needs a hard ownership gate before returning the response.
3. Whether the historical contamination record proves a deterministic fallback/kernel failure path.
4. What PASS conditions R200F should enforce.
5. Whether source ledger granularity is sufficient.

Please do not recommend adding more prompt rules, curriculum content, export, or UI polish before ownership is fixed.

