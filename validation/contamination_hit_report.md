# 1013R_R200E_FRONTEND_VISIBLE_CONTAMINATION_GUARD

Status: `PASS`

## Checks

- `uses_r103_response_snapshot`: `true`
- `frontend_visible_snapshot_written`: `true`
- `content_source_ledger_written`: `true`
- `active_lesson_denylist_written`: `true`
- `all_cases_focus_match_expected`: `true`
- `teacher_main_has_no_denylist_hits`: `true`
- `default_visible_has_no_denylist_hits`: `true`
- `r200b_candidate_not_teacher_main_text`: `true`
- `deterministic_fallback_not_teacher_main_conclusion`: `true`
- `legacy_shell_not_default_visible`: `true`
- `main_text_entries_have_content_source_type`: `true`
- `preview_only_no_formal_apply`: `true`

## Cases

### shoe_observation_user_repro (shoe_observation_drawing_expression)

- expected_focus: `shoe_observation_drawing_expression`
- focus_ok: `true`
- visible_text_count: `162`
- teacher_main_text_count: `114`
- contamination_hit_count: `2`
- teacher_main_contamination_hit_count: `0`
- teacher_main_source_type_counts: `{"R114_field_projection": 5, "R200A_kernel": 88, "uploaded_source": 21}`

Contamination hits:
- `渐变` | right_rail_patch.must_not_show | right_rail_patch | 色彩的渐变
- `渐变` | right_rail_patch.must_not_show | right_rail_patch | P6 色彩渐变联动

### color_gradation (color_gradation_expression)

- expected_focus: `color_gradation_expression`
- focus_ok: `true`
- visible_text_count: `228`
- teacher_main_text_count: `170`
- contamination_hit_count: `0`
- teacher_main_contamination_hit_count: `0`
- teacher_main_source_type_counts: `{"R114_field_projection": 5, "R200A_kernel": 129, "uploaded_source": 36}`

### qinglv_landscape (ink_or_traditional_color_exploration)

- expected_focus: `ink_or_traditional_color_exploration`
- focus_ok: `true`
- visible_text_count: `227`
- teacher_main_text_count: `169`
- contamination_hit_count: `0`
- teacher_main_contamination_hit_count: `0`
- teacher_main_source_type_counts: `{"R114_field_projection": 5, "R200A_kernel": 128, "uploaded_source": 36}`

### material_transformation (material_transformation_expression)

- expected_focus: `material_transformation_expression`
- focus_ok: `true`
- visible_text_count: `236`
- teacher_main_text_count: `178`
- contamination_hit_count: `0`
- teacher_main_contamination_hit_count: `0`
- teacher_main_source_type_counts: `{"R114_field_projection": 5, "R200A_kernel": 137, "uploaded_source": 36}`

### ocean_theme (theme_observation_expression)

- expected_focus: `theme_observation_expression`
- focus_ok: `true`
- visible_text_count: `234`
- teacher_main_text_count: `176`
- contamination_hit_count: `0`
- teacher_main_contamination_hit_count: `0`
- teacher_main_source_type_counts: `{"R114_field_projection": 5, "R200A_kernel": 135, "uploaded_source": 36}`

### weaving (paper_weaving_structure_expression)

- expected_focus: `paper_weaving_structure_expression`
- focus_ok: `true`
- visible_text_count: `226`
- teacher_main_text_count: `174`
- contamination_hit_count: `2`
- teacher_main_contamination_hit_count: `0`
- teacher_main_source_type_counts: `{"R114_field_projection": 5, "R200A_kernel": 127, "uploaded_source": 42}`

Contamination hits:
- `渐变` | right_rail_patch.must_not_show | right_rail_patch | 色彩的渐变
- `渐变` | right_rail_patch.must_not_show | right_rail_patch | P6 色彩渐变联动

