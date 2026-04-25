# Persistent Wrong Answers (Across Exams 1-4)

Use this format for each repeated miss:

## Entry Template

- Topic:
- Appeared in exams:
- What I answered:
- Correct answer:
- Why I was wrong:
- Doc reference:
- Hands-on fix I ran:
- Retest result:

## Common Gaps Checklist

- [ ] `terraform state rm` removes from state only.
- [ ] `terraform import` does not generate configuration.
- [ ] State locking behavior (apply vs plan understanding).
- [ ] CLI workspaces vs Terraform Cloud workspaces.
- [ ] Version constraints (`~> 1.0` vs `~> 1.0.0`).
- [ ] Correct workflow order (`init -> validate -> plan -> apply -> destroy`).
- [ ] Lifecycle rules (`create_before_destroy`, `prevent_destroy`, `ignore_changes`).
