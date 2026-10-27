# Report assets – ML Assignment 2 (Bagging, Boosting, Bias-Variance)

Everything here comes straight from the outputs of `assignment2_notebook_renamed__1___3_.ipynb`.
No new figures or tables were created. Figures are the PNGs embedded in the notebook;
tables are the notebook's DataFrames / printed outputs, saved as CSV (original column names)
and LaTeX (booktabs, ready for the CVPR template; needs `\usepackage{booktabs,graphicx}`).

## Figures (figures/)
| File | Question | Notebook cell |
|---|---|---|
| fig_q1c_oob_disagreement_margin_vs_B.png | Q1(c) OOB accuracy, pairwise disagreement, vote margin vs B | 16 |
| fig_q2b_samme_diagnostics.png | Q2(b) weighted error, alpha, max sample weight, top-10 weight vs round | 31 |
| fig_q2c_highest_weight_training_face.png | Q2(c) highest-weight training face | 34 |
| fig_q2c_highest_weight_prediction_history.png | Q2(c) prediction history of that face | 34 |
| fig_q2d_clean_vs_masked_face0.png | Q2(d) clean vs masked test face 0 | 38 |

## Tables (tables/csv/*.csv and tables/latex/*.tex, same base name)
| Base name | Question | Notebook cell |
|---|---|---|
| t_q1a_single_tree_grid | Q1(a) depth x min_samples_leaf grid | 6 |
| t_q1bc_bagging_vs_B | Q1(b,c) bagging metrics for every B | 14 |
| t_q1d_tree_vs_bagging_clean_masked | Q1(d) accuracy + confidence, clean/masked | 20 |
| t_q1d_case_studies | Q1(d) two corrected + two both-wrong faces | 21 (printed) |
| t_q2a_samme_round_log | Q2(a) one SAMME round (eps = 0.3333, alpha = 1.3863) | 23 (printed) |
| t_q2b_boosting_grid | Q2(b) depth x rounds validation grid | 29 |
| t_q2c_bagging_vs_boosting | Q2(c) 25/50/100 learners incl. training time | 33 |
| t_q2c_hard_face | Q2(c) highest-weight training face stats | 34 (printed) |
| t_q2d_three_models_clean_masked | Q2(d) tree / bagging / SAMME, clean + masked | 37 |
| t_q2d_different_response_face | Q2(d) face 0, bagging vs boosting response | 38 (printed) |
| t_q2d_bagging_votes_face0 | Q2(d) bagging vote counts for face 0 | 38 (printed) |
| t_q3a_bias_variance_selected | Q3(a) bias^2, variance, mean/std accuracy | 42 (printed, 4 dp) |
| t_q3b_depth_bias_variance | Q3(b) shallow / selected / deep, single vs bagging | 44 (printed, 4 dp) |
| t_q3b_variance_reduction_by_depth | Q3(b) and Q3(c) variance removed + accuracy gain | 44, 46 |
| t_q3d_final_summary | Q3(d) final table | 48 |

Q3(c) has no table of its own: the notebook re-displays the Q3(b) variance-reduction table, so use
t_q3b_variance_reduction_by_depth and t_q3b_depth_bias_variance (leaf occupancy, disagreement).

## Layout notes
- Tables with many columns use `table*` (full width); smaller ones use single-column `table`.
  All are wrapped in `\resizebox`; switch `table*` <-> `table` as your 8-page budget needs.
- fig_q1c... has an intentionally blank 4th panel (the notebook turns that axis off); crop it in LaTeX with `trim`/`clip` if you want.
