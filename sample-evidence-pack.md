# MandateOS dispute evidence pack

> **Sandbox data.** This pack was generated from the MandateOS sandbox (simulated rail, test accounts). It demonstrates the format a production pack takes; it is not evidence of a real payment.

- Payment intent: `pin_b250daee0490484684effd80efb064f1`
- Generated at: 2026-10-23T11:33:00.000Z
- Pack version: 1.0
- Bundle hash (SHA-256): `3e6be4e42ca4f0570ebd034bd8bf52f29e7f5c7aae7b1fa71e053b11f1440d66`

## Summary verdict

The agent attempted a payment of **₹2,600** (260000 paise) to **Blinkit**. Final policy decision: **ALLOW**; payment status: **SUCCEEDED**.

Reason codes:
- `IN_SCOPE_AFTER_APPROVAL` — The user approved this payment, and on re-check it was inside the mandate's scope.

## What was authorized

Mandate `mnd_be02f9027664407aa22e8a2062acda30` — purpose: Weekly groceries and household staples. Status at pack time: ACTIVE.
- Per-payment cap: ₹5,000
- Daily cap: ₹15,000
- Monthly cap: ₹15,000
- Ask-first threshold: ₹5,000; approval mode: SILENT_WITHIN_SCOPE
- Categories: GROCERIES
- Merchant allowlist: mrc_bigbasket, mrc_blinkit
- Valid: 2026-10-01T00:00:00.000Z to 2027-03-31T00:00:00.000Z

Consent: the user consented on 2026-10-22T10:00:00.000Z via HOSTED_CONSENT_PAGE; consent text hash `46f4edc45da484deab3c4730d74d5144bdedeaada236ed2363945aa5ba07fcf8`; rail consent reference `consent_mnd_be02f9027664407aa22e8a2062acda30`.

Agent: Kirana Agent (`agt_2e541fe20e424743a1972c704e42bfb8`), developer account `dev_local`, attestation level **L0_SELF_ASSERTED**, signing-key fingerprint `2722f1c198adffb899fd7f0644900717f6579101164b92a96754cd39bfd380d7`.
User: Priya (`usr_priya`).

## What happened

Policy decisions, in order:
- **STEP_UP** at 2026-10-23T11:33:00.000Z — `FIRST_TXN_FOR_MERCHANT` (This is the first payment to this merchant under the mandate, so the user must approve it.) (policy version 1.0.0, inputs hash `60572a6b6e0a80f5d251f153c4eb6e8321c4e06b0854b1dab8aec912b49023b0`, ledger seq 22)
- **ALLOW** at 2026-10-23T11:33:00.000Z — `IN_SCOPE_AFTER_APPROVAL` (The user approved this payment, and on re-check it was inside the mandate's scope.) (policy version 1.0.0, inputs hash `374bfa5a448127026fc93f458b1bbcf07d4a4901d35255261ad20b6e8ca936da`, ledger seq 25)

Approval: request `apr_343442bacc3d4629809811a0095c0930` asked the user to confirm **₹2,600** to **Blinkit** via PUSH. Status: **APPROVED**, decided at 2026-10-23T11:33:00.000Z via IN_APP by user `usr_priya`.

Execution: rail **SANDBOX_UPI**, external reference `sbx_txn_7`, UPI reference `1000000000007`; final status SUCCEEDED.

## Timeline

- seq 1 · 2026-10-22T10:00:00.000Z · **MANDATE_CREATED** · actor DEVELOPER:dev_local · entry hash `b13f8f970baa3e14…`
- seq 2 · 2026-10-22T10:00:00.000Z · **MANDATE_CONSENTED** · actor USER:usr_priya · entry hash `c263d92b34da7db3…`
- seq 3 · 2026-10-22T10:00:00.000Z · **MANDATE_ACTIVATED** · actor USER:usr_priya · entry hash `b6d920fe4c575294…`
- seq 22 · 2026-10-23T11:33:00.000Z · **POLICY_DECISION** · actor SYSTEM:policy-engine · entry hash `ec95c1612aabcdf2…`
- seq 23 · 2026-10-23T11:33:00.000Z · **APPROVAL_REQUESTED** · actor AGENT:agt_2e541fe20e424743a1972c704e42bfb8 · entry hash `3e35a508d67c801f…`
- seq 24 · 2026-10-23T11:33:00.000Z · **APPROVAL_DECIDED** · actor USER:usr_priya · entry hash `2986b2bc0394fd88…`
- seq 25 · 2026-10-23T11:33:00.000Z · **POLICY_DECISION** · actor SYSTEM:policy-engine · entry hash `47046abeab2deccb…`
- seq 26 · 2026-10-23T11:33:00.000Z · **EXECUTION_SUBMITTED** · actor SYSTEM:api-mcp · entry hash `6486dfa54aca7482…`
- seq 27 · 2026-10-23T11:33:00.000Z · **EXECUTION_SUCCEEDED** · actor SYSTEM:api-mcp · entry hash `46e8d7347a644468…`

## Verification

- Ledger chain: **valid**. The user's full hash chain (28 entries) was re-verified at generation time; this pack includes the 9 entries that reference this intent, its approval, and its mandate (seq numbers are shown, so entries belonging to other payments appear as gaps).
- Bundle hash: `3e6be4e42ca4f0570ebd034bd8bf52f29e7f5c7aae7b1fa71e053b11f1440d66` — SHA-256 over the canonical JSON of the pack contents. Recomputing it over the JSON form of this pack detects any later edit.
- Attestation limit: this pack is **not server-signed** (v1). The hashes prove the pack is internally consistent and that the ledger chain was intact when the pack was generated; they do not by themselves prove MandateOS issued the pack.
