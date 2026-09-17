# Domain Glossary

## User
A human platform identity. A User does not gain organization authority merely by existing.

## Organization
An accountable operational entity such as a police agency, government body, emergency organization, or verified partner organization.

## Organization Membership
The scoped relationship between a User and an Organization. Membership has its own lifecycle and roles/abilities. A User may have different authority in different Organizations.

## Jurisdiction
An administrative or legal geographic area in which authority may apply. Jurisdiction is not the same thing as an Organization and is not the same thing as an Alert target area.

## Case
The internal investigative/work-management record concerning a missing person or suspected abduction. A Case can exist without any public Alert.

## Case Subject
The missing person associated with a Case. A Case Subject is not a platform User.

## Case Verification
A recorded human decision that the Case has met the organization's requirements to proceed as a verified case. Verification does not itself authorize publication.

## Alert
A public communication campaign derived from a Case. An Alert has a lifecycle independent from its Case.

## Alert Revision
An immutable, deliberately public snapshot of Alert content. Approval and distribution always refer to a specific revision.

## Alert Approval
A recorded human authorization of an exact Alert Revision for publication. Modifying public content requires a new revision and therefore new approval.

## Alert Target
The geographic audience definition for an Alert, e.g. administrative area, point/radius, polygon, or later corridor/route.

## Tip / Sighting
Untrusted or semi-trusted information submitted about a Case/Alert. Reporter identity is more restricted than ordinary tip content.

## Distribution
The intent to disseminate a specific Alert Revision through a specific channel/target.

## Distribution Attempt
One traceable provider/channel attempt to execute a Distribution. Attempts are retryable and idempotent.

## Audit Event
A security-conscious record of an important action. Audit data is allow-listed and must not indiscriminately duplicate sensitive model contents.

## ML Assessment
A versioned advisory output generated from structured case information. It is evidence for human review, not workflow authority.
