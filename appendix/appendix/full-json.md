# Full JSON

Below is the full JSON example.

```json
{
  "session": {
    "session_id": "+393801942228",
    "user_id": "+393801942228",
    "status": "draft",
    "created_at": "2025-11-18 09:37:52",
    "updated_at": "2025-11-18 11:03:24"
  },
  "accident": {
    "date": "18/11/2025",
    "time": "11:55",
    "location": "Via Garibaldi 140,Latina",
    "injuries": 0,
    "property_damage": "no",
    "external_vehicle_damage": "no",
    "witnesses_present": 0,
    "witness_names": "",
    "law_enforcement_involved": 1,
    "law_enforcement_type": "Carabinieri",
    "accident_description": ""
  },
  "vehicle_A": {
    "license_plate": "ZA000AC",
    "insurance": {
      "policy_number": "D3E4F",
      "company": "Novires",
      "coverage_type": "Third-Party Liability",
      "additional_coverage": "NO"
    },
    "insured_person": {
      "first_name": "Leonardo",
      "last_name": "Russo",
      "tax_id_vat": "BRTGRZ85A20C351B",
      "address": "Via Mazzini 62, Florence",
      "postal_code": "50089",
      "phone_number": "+392391379295"
    },
    "vehicle": {
      "brand": "Abarth",
      "model": "695 Rivale"
    },
    "driver": {
      "same_as_insured": 1,
      "full_name": "Leonardo Russo",
      "tax_id_vat": "BRTGRZ85A20C351B",
      "address": "Via Mazzini 62, Florence",
      "postal_code": "50089"
    },
    "damage": {
      "bareme": null,
      "impact_points": "",
      "impact_points_text": ""
    }
  },
  "vehicle_B": {
    "license_plate": "ZA001AP",
    "insurance": {
      "policy_number": "3DEF4",
      "company": "Novires",
      "coverage_type": "Third-Party Liability",
      "additional_coverage": "Hail"
    },
    "insured_person": {
      "first_name": "Cecilia",
      "last_name": "Pellegrini",
      "tax_id_vat": "ZNNGRG71L09P345R",
      "address": "Via Garibaldi 16, Turin",
      "postal_code": "10035",
      "phone_number": "+397700287052"
    },
    "vehicle": {
      "brand": "Jaguar",
      "model": "E-Pace"
    },
    "driver": {
      "same_as_insured": null,
      "skip_driver": 1,
      "full_name": "",
      "tax_id_vat": "",
      "address": "",
      "postal_code": ""
    },
    "damage": {
      "bareme": null,
      "impact_points": "",
      "impact_points_text": ""
    }
  }
}
