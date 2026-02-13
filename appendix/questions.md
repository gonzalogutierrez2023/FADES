# Full List of Questions

This appendix provides the full list of deterministic questions used by the FNOL conversational agent, grouped by vehicle side (A/B) and by semantic subsection of the CAI form.

For each slot, we specify:
- **Question**: the canonical question asked by the LLM
- **Asked?**
  - **Always** = the FNOL conversational agent always asks this question
  - **Only if missing** = the value is pre-filled from the insurance database when available
- **Suppressed if driver = insured**: skipped when the insured and driver coincide

The structure mirrors the CAI template (see main text and official CAI document).

---

## Vehicle A — Identification and Insurance Data

| Slot | Field | Condition | Notes |
|---|---|---|---|
| `targa_A` | Vehicle A license plate | Always | Entry point, attempted prefill. |
| `insured_name_A` | Insured full name (A) | If missing | Prefilled when available. |
| `tax_id_A` | Tax ID or VAT number (A) | If missing | Prefilled. |
| `policy_number_A` | Insurance policy number (A) | If missing | Prefilled. |
| `insurance_company_A` | Insurance company (A) | If missing | Prefilled. |
| `vehicle_brand_A` | Vehicle brand (A) | If missing | Prefilled. |
| `vehicle_type_A` | Vehicle type (A) | If missing | Prefilled. |
| `coverage_type_A` | Insurance coverage type (A) | If missing | Prefilled. |
| `extra_coverage_A` | Additional coverages (A) | If missing | Prefilled. |
| `phone_A` | Insured phone number (A) | If missing | Prefilled. |
| `address_A` | Insured address (A) | If missing | Prefilled. |
| `postal_code_A` | Postal code (A) | If missing | Prefilled. |

---

## Vehicle A — Driver Information

| Slot | Field | Condition | Notes |
|---|---|---|---|
| `driver_same_as_insured_A` | Driver equals insured (A) | Always | If yes, fields are copied. |
| `driver_name_A` | Driver full name (A) | If missing | Suppressed if same as insured. |
| `driver_tax_id_A` | Driver tax ID / VAT (A) | If missing | Suppressed if same as insured. |
| `driver_address_A` | Driver address (A) | If missing | Suppressed if same as insured. |
| `driver_postal_code_A` | Driver postal code (A) | If missing | Suppressed if same as insured. |

---

## Accident Metadata (Shared for Vehicles A and B)

| Slot | Field | Condition |
|---|---|---|
| `accident_date` | Accident date | Always |
| `accident_time` | Accident time | Always |
| `accident_location` | Accident location | Always |

---

## Damages, Injuries, and Witnesses

| Slot | Field | Condition | Notes |
|---|---|---|---|
| `injuries` | Injuries reported | Always | — |
| `object_damage` | Damage to objects | Always | Accepts “none”. |
| `external_vehicle_damage` | Damage to other vehicles | Always | Accepts “none”. |
| `witnesses_present` | Witnesses present | Always | — |
| `witness_details` | Witness identification | If yes | Conditional. |
| `law_enforcement` | Law enforcement involved | Always | — |
| `law_enforcement_type` | Type of authority | If yes | Police, Carabinieri, or others. |

---

## Vehicle B — Identification and Insurance Data

| Slot | Field | Condition | Notes |
|---|---|---|---|
| `targa_B` | Vehicle B license plate | Always | Entry point. |
| `insured_name_B` | Insured full name (B) | If missing | — |
| `tax_id_B` | Tax ID or VAT number (B) | If missing | — |
| `policy_number_B` | Insurance policy number (B) | If missing | — |
| `insurance_company_B` | Insurance company (B) | If missing | — |
| `vehicle_brand_B` | Vehicle brand (B) | If missing | — |
| `vehicle_type_B` | Vehicle type (B) | If missing | — |
| `coverage_type_B` | Insurance coverage type (B) | If missing | — |
| `extra_coverage_B` | Additional coverages (B) | If missing | — |
| `phone_B` | Insured phone number (B) | If missing | — |
| `address_B` | Insured address (B) | If missing | — |
| `postal_code_B` | Postal code (B) | If missing | — |

---

## Vehicle B — Driver Information

| Slot | Field | Condition | Notes |
|---|---|---|---|
| `driver_same_as_insured_B` | Driver equals insured (B) | Always | — |
| `driver_data_known_B` | Driver data known (B) | If different | — |
| `driver_name_B` | Driver full name (B) | If missing | Conditional. |
| `driver_tax_id_B` | Driver tax ID / VAT (B) | If missing | Conditional. |
| `driver_address_B` | Driver address (B) | If missing | Conditional. |
| `driver_postal_code_B` | Driver postal code (B) | If missing | Conditional. |

---

## Impact Points and BAREME Classification

| Slot | Field | Condition | Notes |
|---|---|---|---|
| `impact_points_A` | Impact points (A) | Always | Can be inferred from text. |
| `impact_points_B` | Impact points (B) | Always | Same inference. |
| `bareme_A` | BAREME code (A) | Always | Inference allowed. |
| `bareme_B` | BAREME code (B) | Always | — |

---

## Free-Text Accident Description (Group S3)

| Slot | Field | Condition |
|---|---|---|
| `accident_description` | Detailed narrative of the accident dynamics | Always |

In Group S3, the user provides a free-text narrative describing the accident dynamics.  
The language model extracts the structured field `accident_description` and may optionally infer:
- `bareme_A`, `bareme_B`
- `impact_points_A`, `impact_points_B`

The system never updates fields outside the current group unless they are explicitly flagged as pending suggestions.
