# Palantir Foundry CRM Project

This project was built as part of a work sample for Axis Data. The challenge was simple but open-ended:  
**"Build a Sales CRM"** using Palantir Foundry with only two incomplete datasets.

In ~48 hours, I designed and delivered a full-stack CRM application inside Foundry — from raw CSVs to a usable dashboard.

---

## 🚀 Project Highlights

### Data Engineering (Pipeline Builder)
- Cleaned and normalized raw datasets: `raw_people` and `raw_companies`.
- Imputed missing fields (e.g. revenue, addresses) with reasonable defaults.
- Added UUIDs as primary keys for both tables.
- Linked people to companies via left join on `company_name`.
- Introduced `is_independent` flag for unlinked people (freelancers/contractors).
- Output tables:
  - **clean_companies**: `company_id, company_name, website, address, revenue_in_millions, industry`
  - **clean_people**: `person_id, job_title, name, phone_number, email, company_id, company_name, is_independent`

### Backend Modeling (Ontology Manager)
Created four ontology objects with properties, relationships, and actions:

1. **Company** → id, name, address, industry, revenue, website  
2. **Person** → id, name, job title, email, phone, company link, is_independent, is_archived  
3. **Opportunity** → linked to company + person, expected close date, stage, value  
4. **Lead** → linked to company + person, interaction type, notes, date  

All entities support CRUD actions (`Create`, `Edit`, `Delete`).

### Frontend (Workshop Builder)
- Built a CRM dashboard tied directly to ontology actions.  
- Features:
  - Quick-create buttons: **New Company, New Person, New Opportunity**  
  - Views: **Timeline**, **All Opportunities**, **All Interactions**  
  - Metrics at a glance: total companies, total people, active opportunities value, interactions this month  
  - Company view: details, linked people, opportunities, interactions, comments section  
  - Person view: details, linked opportunities, interactions, notes section  
- Fully interactive: filter, search, edit, add new entities, all synced with backend.

---

## 🎯 Reflection
This was the most full-stack project I’ve done inside a single platform:
- Thought like a **data engineer** cleaning and structuring raw inputs.  
- Thought like a **backend engineer** modeling business entities and relationships.  
- Thought like a **frontend/product engineer** designing a workflow salespeople would actually use.  

From incomplete CSVs to a working CRM dashboard — all in 48 hours.




