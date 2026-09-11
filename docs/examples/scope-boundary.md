# Example: Scope Boundaries Across Tasks

[English](scope-boundary.md) | [简体中文](scope-boundary.zh-CN.md)

## Task 1

The user asks for a compact layout on one dashboard card. The agent applies the layout to that card and verifies the dashboard.

## Task 2

Later, the user asks for several long-form recommendations. The earlier card layout is irrelevant unless the user explicitly requests it as a general presentation preference.

## Correct interpretation

The first decision was component- or task-scoped. It does not establish a user-wide preference, a repository-wide typography rule, or a filter on unrelated content.

## Durable version

If the user says, "Use compact layouts across this project," the instruction becomes a project rule. If the user says, "Remember that I prefer compact layouts in future work," it becomes an explicit user preference. The persistence signal changes the scope.
