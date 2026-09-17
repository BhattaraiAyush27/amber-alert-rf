# Initial Authorization Matrix

Roles are convenience bundles. Backend authorization checks abilities and scope, not role names alone.

| Ability | Investigator | Alert Operator | Reviewer | Publisher | Org Admin | Platform Admin |
|---|---:|---:|---:|---:|---:|---:|
| cases.create | yes | optional | no | no | configurable | no by default |
| cases.read | yes | yes | yes | yes | configurable | no by default |
| cases.read_restricted | yes | configurable | yes | configurable | no by default | no by default |
| cases.update | yes | configurable | no | no | no by default | no |
| cases.verify | configurable | no | yes | no | no by default | no |
| alerts.create | configurable | yes | no | no | no by default | no |
| alerts.submit | configurable | yes | no | no | no | no |
| alerts.review | no | no | yes | configurable | no | no |
| alerts.approve | no | no | yes | configurable | no | no |
| alerts.publish | no | no | no | yes | no by default | no |
| alerts.end | configurable | yes | yes | yes | no by default | no |
| members.manage | no | no | no | no | yes | no |
| organizations.manage | no | no | no | no | yes (own org) | yes (platform metadata) |
| platform.manage | no | no | no | no | no | yes |

## Non-negotiable checks

Protected resource authorization is the conjunction of:

1. authenticated User;
2. active Organization Membership;
3. resource belongs to that Organization;
4. Membership has the required ability;
5. current domain state permits the action;
6. additional action constraints pass (e.g. author != approver).

Platform administrators do not automatically gain access to restricted case content.
