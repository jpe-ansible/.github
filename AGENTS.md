# jpe-ansible

jpe-ansible holds public Ansible collections for agent-host automation and Nautobot
operations, including synchronization, readiness, and drift tasks.

## Shared CI and releases

- Reuse workflows from `JacobPEvans/.github` and `JacobPEvans/.github-ai`.
  Reference both at `@v1`; never pin them to a commit SHA.
- Keep organization-managed CI and release steps in the reusable workflows.
  Local workflow files should call the shared implementation with repository
  specific inputs.
- Give each repository exactly one `release.yml` caller for its release
  workflow.
- Configure Renovate to extend only `github>JacobPEvans/.github`.
- Enterprise rulesets inject required checks. Do not add repository copies of
  shared checks.

## Domain conventions

- Keep reusable automation in Ansible collections, roles, and playbooks.
  Express operational behavior with Ansible tasks.
- Make collection tasks idempotent so repeated runs converge on the declared
  state.
- Do not add Python, shell, or Ruby helper files to collection repositories.
- Keep collection behavior focused on its published purpose. Retain role
  contracts and integration-specific details with the owning collection.

### Repeatable operations

- Model automation as state convergence so repeated playbook runs produce the
  intended configuration.
- Keep collection behavior accessible through Ansible roles and playbooks;
  avoid standalone operational commands that bypass Ansible.

## Repository map

| Repository | Purpose |
| --- | --- |
| `ansible-ai-agents` | Ansible collection for AI agent hosts |
| `ansible-nautobot` | Nautobot server, sync, pre-flight, and drift roles |
| `.github` | Organization profile |
