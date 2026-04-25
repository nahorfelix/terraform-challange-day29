# Persistent Wrong Answers (Across Exams 1-4)

## Entry 1

- Topic: `terraform state rm` vs `terraform destroy`
- Appeared in exams: 1 and 2
- What I answered: `state rm` deletes the actual resource
- Correct answer: `state rm` removes from state only; it does not delete infrastructure
- Why I was wrong: I mixed state actions with lifecycle actions
- Doc reference: https://developer.hashicorp.com/terraform/cli/commands/state/rm
- Hands-on fix I ran: `terraform state rm random_id.test` followed by validation of state output
- Retest result: Correct in Exams 3 and 4

## Entry 2

- Topic: `terraform import` behavior
- Appeared in exams: 1 and 3
- What I answered: Import creates full `.tf` config automatically
- Correct answer: Import only links resource to state; config still must be authored
- Why I was wrong: I assumed import acted like code generation
- Doc reference: https://developer.hashicorp.com/terraform/cli/commands/import
- Hands-on fix I ran: Imported test resource and reviewed follow-up plan output
- Retest result: Correct in Exam 4

## Entry 3

- Topic: Version constraints (`~> 1.0` vs `~> 1.0.0`)
- Appeared in exams: 2 and 3
- What I answered: Both constraints allow the same range
- Correct answer: `~> 1.0` allows `< 2.0.0`; `~> 1.0.0` allows `< 1.1.0`
- Why I was wrong: I ignored minor vs patch boundary
- Doc reference: https://developer.hashicorp.com/terraform/language/expressions/version-constraints
- Hands-on fix I ran: Wrote three provider constraint blocks and explained each range
- Retest result: Correct in Exam 4

## Common Gaps Checklist

- [x] `terraform state rm` removes from state only.
- [x] `terraform import` does not generate configuration.
- [x] State locking behavior (apply vs plan understanding).
- [x] CLI workspaces vs Terraform Cloud workspaces.
- [x] Version constraints (`~> 1.0` vs `~> 1.0.0`).
- [ ] Correct workflow order (`init -> validate -> plan -> apply -> destroy`).
- [ ] Lifecycle rules (`create_before_destroy`, `prevent_destroy`, `ignore_changes`).
