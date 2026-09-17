# ML Data Source Policy

## Preferred sources

### NamUs
Primary research candidate. Prefer official registered-user CSV exports over HTML scraping. Preserve raw exports immutably and record acquisition metadata.

### Charley Project
Secondary research/validation source only. Preserve attribution and document the site's non-random inclusion/classification criteria. Do not treat its labels as a universal ontology.

### NCMEC
Do not scrape. Use only approved API/data-sharing paths and only for ML training if the applicable terms/permission allow that use.

### Official AMBER program reports
Use for policy/history/outcome research. Do not manufacture negative examples by assuming every non-AMBER missing-person case was an ineligible alert candidate.

### Nepal institutional sources
Long-term preferred local path is an authorized data/research partnership with responsible institutions rather than brittle public-site scraping.

## Dataset provenance manifest

Every raw acquisition must record:

- source name;
- source URL/system;
- acquisition method;
- acquired_at timestamp;
- applicable terms/permission note;
- SHA-256 digest;
- record count;
- source schema/version if known;
- sensitivity/PII classification.

Raw person-level data must not be committed to the public Git repository.
