# ShipDesk release readiness

- Author: rakkannnnnnn <muhammed.rakkan.s88@kalvium.community>
- Candidate: 1.1.0
- Local image ID (not merely image tag): sha256:f9394b8e0b632c1d072097db1b3e649e73761f723dacaa07ca109d07f0dc5ddd
- Local /health and /config result: /health: 200 OK {"status": "ok"}; /config: 200 OK {"service": "ShipDesk", "mode": "production", "version": "1.1.0"}
- Scope: LOCAL VALIDATION ONLY; approval NOT REQUESTED; NOT DEPLOYED to production.
- Hypothetical incident decision and two supplied signals: Decision: Rollback to previous release 1.0.0. Signals: (1) Request failure rate surged from 0.2% to 30% within 10 minutes of candidate 1.1.0 reaching production; (2) Most readiness checks failed for 1.1.0, while previous release 1.0.0 was healthy and confirmed compatible with current schema and data.
- Proposed post-recovery checks: 1. Verify request failure rate drops back to baseline levels (<0.2%). 2. Confirm /health and /config return HTTP 200 with expected payloads across all instances. 3. Verify service stability and data consistency under release 1.0.0.

Final commit, annotated tag identity, successful Actions URL and matching
hosted commit go in submitted PDF AFTER this file is committed. Do not edit
this file to insert its own commit hash, avoiding a circular commit identity.
