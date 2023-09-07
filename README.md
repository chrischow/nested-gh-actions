# Nested GitHub Actions
A repo to experiment with GitHub deployment environments and how to pass environment secrets and variables to GitHub Actions.

## Findings
- It's possible to nest workflows and reference a specified environment
- When doing this though, you have to specify secrets at the top level caller, **EVEN IF IT DOESN'T ACCESS THE ENVIRONMENT'S SECRETS**, and pass those secrets down through `on:`, all the way down to the most deeply nested called workflow
- It makes no damn sense why you should pass a secret that does not exist from the top level caller, **but it fking works**