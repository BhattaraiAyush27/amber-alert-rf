# V1 Case Information Contract

This is the first-pass domain contract. It is intentionally not a database migration yet.

## Case

Internal metadata:

- id: ULID
- organization_id: ULID
- case_number: organization-scoped human reference
- status: draft | active | resolved | archived
- verification_status: unverified | pending | verified | rejected
- opened_at
- missing_since
- resolved_at: nullable
- resolution_reason: nullable structured code
- created_by_membership_id
- created_at / updated_at

## Case Subject

Internal/restricted source-of-truth information:

- id: ULID
- case_id
- legal_first_name
- legal_middle_name: nullable
- legal_last_name
- preferred/display name: nullable
- date_of_birth: nullable when unknown
- age_at_missing: integer/derived snapshot
- sex: nullable/controlled vocabulary
- height_cm: nullable
- weight_kg: nullable
- hair_description: nullable
- eye_description: nullable
- identifying_features: restricted free text
- vulnerability flags: structured booleans/controlled vocabulary

Sensitive demographics are not automatically ML features.

## Case Circumstance

Structured facts intended both for investigation and future decision support:

- case_id
- last_seen_at
- last_seen_location_text
- suspected_abduction: yes | no | unknown
- abduction_witnessed: yes | no | unknown
- force_or_coercion_reported: yes | no | unknown
- suspect_known: yes | no | unknown
- suspect_relationship: controlled vocabulary, nullable
- threat_information_present: yes | no | unknown
- vehicle_involved: yes | no | unknown
- witness_information_available: yes | no | unknown
- voluntary_departure_indicators: yes | no | unknown
- medical_vulnerability: yes | no | unknown
- developmental_vulnerability: yes | no | unknown
- narrative: restricted text

Unknown is a real value and must not silently become false.

## Restricted information kept outside public Alert content

Examples:

- private family/contact details
- investigation notes
- non-public suspect information
- non-public exact locations
- evidence
- unapproved photographs
- reporter/source identity
- raw tipster identity
- internal risk/ML assessments

## Public information contract

No field above is public merely because it exists. Public information is copied/transformed into an Alert Revision only after deliberate operator selection and later approval.
