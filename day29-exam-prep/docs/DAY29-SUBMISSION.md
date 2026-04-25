# Day 29 of the Terraform Challenge

## Four-Exam Score Table

| Exam | Score | % | Time | Notes |
|------|-------|---|------|-------|
| Exam 1 | 47/57 | 82% | ~57m | Some CLI/state confusion |
| Exam 2 | 51/57 | 89% | ~54m | Better confidence |
| Exam 3 | 54/57 | 95% | ~46m | Small versioning gaps |
| Exam 4 | 55/57 | 96% | ~43m | Very strong accuracy |

## Trend Analysis
Scores stayed above 70% and improved across all four exams. The trend shows stronger understanding and steadier performance under timed conditions. The biggest improvement came from reviewing missed questions right away and reinforcing weak areas through terminal practice.

## Readiness Assessment
**Ready:** My scores are high and consistent, with the final two exams in the mid-90s. I can answer faster with fewer second guesses. Remaining weak points are specific and already listed for Day 30 review.

## Persistent Wrong-Answer Topics

**State vs infrastructure**  
I confused `terraform state rm` with `terraform destroy`. Now I understand `state rm` removes a resource from state only, while `destroy` removes real infrastructure.

**Terraform import**  
Import adds existing resources to state and does not generate complete configuration. If config differs from real infrastructure, `terraform plan` shows changes.

**Version constraints**  
I clarified the difference between `~> 1.0` and `~> 1.0.0` and how each controls allowed upgrade ranges.

**Workspace behavior**  
Each workspace has its own state. The default workspace cannot be deleted while active. Terraform Cloud workspaces are different from CLI workspaces.

**State locking**  
State locking protects state from conflicting writes. In exam context, it is mainly about preventing concurrent apply-style state changes.

## Hands-On Exercises

```bash
terraform state list
terraform state show random_id.test
terraform state rm random_id.test
terraform destroy -auto-approve
```

This reinforced the difference between Terraform state operations and real infrastructure deletion.

```bash
terraform workspace new dev
terraform workspace list
terraform workspace select dev
terraform workspace show
```

This clarified workspace isolation and environment separation.

## Provider Version Constraint Practice

`~> 1.0`  
= `>= 1.0.0` and `< 2.0.0`

`~> 1.0.0`  
= `>= 1.0.0` and `< 1.1.0`

`>= 1.0, < 2.0.0`  
Equivalent to `~> 1.0`

## Final Study Priority List

1. Terraform Cloud concepts and run workflow.
2. Version constraint precision (`~>` and explicit range boundaries).
3. State vs infrastructure commands (`terraform state rm` vs `terraform destroy`).
4. `terraform import` behavior and post-import drift handling.
5. CLI edge cases where similar commands have different scope/effects.
