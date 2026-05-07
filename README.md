# Environmental Programs Management System

**Integrated impact tracking platform** for environmental education, ecological restoration, and community engagement programs. Captures program participation, outcomes, and organizational impact through low-cost Microsoft 365 tools.

## 🎯 Problem Statement

Environmental organizations track conservation programs across multiple initiatives (education, restoration, stewardship) using disconnected spreadsheets and manual data consolidation, resulting in:

- **Impact visibility gaps**: No unified view of organizational outcomes
- **Delayed reporting**: Manual aggregation of program metrics
- **Data inconsistency**: Same information in multiple files
- **Stakeholder alignment**: Difficulty demonstrating program impact

## ✅ Solution Overview

A **centralized program management system** that captures participation data once, automates validation and consolidation, and delivers real-time impact dashboards—demonstrating organizational effectiveness to donors, partners, and stakeholders.

### Key Capabilities

| Module | Capability | Outcome |
|--------|-----------|---------|
| **Program Registry** | Master catalog of initiatives | Single source of truth for programs & activities |
| **Participation Tracking** | Attendance & volunteer hours | Real-time participation metrics by program |
| **Impact Metrics** | Outcomes by program type | Quantifiable results: education reach, restoration area, community engagement |
| **Volunteer Management** | Hours, skills, retention | Human capital tracking and volunteer development |
| **Multi-module Analytics** | Unified data warehouse | Comparative impact across all programs |

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────────┐
│                     Power Apps Frontend                      │
│  (Program entry, volunteer registration, participation logs) │
└────────────────────┬────────────────────────────────────────┘
                     │ Captures structured participation data
                     ▼
┌─────────────────────────────────────────────────────────────┐
│                Power Automate Orchestration                  │
│  (6 automated workflows: programs, participation, volunteers)│
└────────────────────┬────────────────────────────────────────┘
                     │ Transforms & validates
                     ▼
┌─────────────────────────────────────────────────────────────┐
│              Excel Data Lake (OneDrive)                      │
│  (Programs, participants, outcomes, volunteers)              │
└────────────────────┬────────────────────────────────────────┘
                     │ Live connection
                     ▼
┌─────────────────────────────────────────────────────────────┐
│                Power BI Dashboards                           │
│  (Impact reporting: reach, outcomes, volunteer contribution) │
└─────────────────────────────────────────────────────────────┘
```

**Technology Stack:**
- **Frontend**: Power Apps (mobile-optimized forms)
- **Integration**: Power Automate (6 workflows)
- **Data layer**: Excel workbook in OneDrive (6 core tables)
- **Analytics**: Power BI (3 impact dashboards)
- **Infrastructure**: Microsoft 365 (no additional costs)

## 📋 Project Structure

```
environmental-management-system/
├── README.md (this file)
├── ARCHITECTURE.md (technical system design)
├── DATABASE_DESIGN.md (data schema & relationships)
├── DEPLOYMENT.md (setup guide, 30-45 min)
├── CHANGELOG.md (version history)
│
├── powerapps/
│   ├── Prototipo_PPL_Ambiental.msapp (exported app)
│   └── SETUP.md (configuration guide)
│
├── power-automate/
│   ├── flows/ (6 workflow exports with docs)
│   │   ├── 01-RegistroPrograma.md
│   │   ├── 02-RegistroParticipacion.md
│   │   ├── 03-RegistroVoluntarios.md
│   │   ├── 04-CálculoImpacto.md
│   │   ├── 05-ResumenMensual.md
│   │   └── 06-ReporteStakeholders.md
│   └── CONNECTIONS_GUIDE.md
│
├── powerbi/
│   ├── dashboards/ (3 PBIX files)
│   │   ├── 01-Dashboard_Alcance.pbix
│   │   ├── 02-Dashboard_Impacto.pbix
│   │   ├── 03-Dashboard_Voluntarios.pbix
│   │   └── README.md
│   └── DATA_MODEL.md
│
├── data/
│   ├── sample_data/ (anonymized examples)
│   │   ├── sample_programas.xlsx
│   │   ├── sample_participacion.xlsx
│   │   └── sample_voluntarios.xlsx
│   └── DATA_DICTIONARY.md
│
├── .github/workflows/
├── LICENSE (MIT)
└── .gitignore
```

## 🚀 Quick Start

### Prerequisites
- Microsoft 365 account
- Power Apps + Power Automate + Power BI access
- 30-45 minutes

### Setup in 4 Steps

1. **Create Excel data structure** (from `data/sample_data/`)
   - See: [`DATABASE_DESIGN.md`](./DATABASE_DESIGN.md)

2. **Import Power Apps**
   - See: [`powerapps/SETUP.md`](./powerapps/SETUP.md)

3. **Deploy Power Automate workflows**
   - See: [`power-automate/CONNECTIONS_GUIDE.md`](./power-automate/CONNECTIONS_GUIDE.md)

4. **Create Power BI dashboards**
   - See: [`powerbi/README.md`](./powerbi/README.md)

**Full guide**: [`DEPLOYMENT.md`](./DEPLOYMENT.md)

## 📊 Key Metrics & Impact

**Operational outcomes observed**:
- **Program documentation**: 100% of activities captured (vs. manual tracking)
- **Volunteer hours**: Automatic logging, no manual spreadsheets
- **Impact quantification**: Real-time reach metrics (participants, hectares restored, etc.)
- **Reporting time**: 80% reduction (from 4 hours to 30 minutes monthly)
- **Cost**: $0 infrastructure (uses existing M365)

## 🔐 Security & Privacy

- **No PII**: Example data fully anonymized
- **Secure storage**: Excel in OneDrive with access control
- **Audit trail**: All program changes logged
- **Compliance-ready**: GDPR-compatible (participant privacy protection)

## 🛠️ Technical Highlights

### Database Design
- **Normalized schema**: 6 core tables (Programs, Participants, Volunteers, Outcomes, Dates, Organizations)
- **Dimensional model**: Star schema optimized for BI
- **Data integrity**: Validation in Power Apps + Power Automate

### Power Automate
- **Trigger-based**: Immediate data validation on entry
- **Scheduled**: Automatic monthly impact summary generation
- **Error handling**: Email alerts on data issues

### Power BI
- **Live refresh**: DirectQuery to Excel for real-time updates
- **Impact measures**: DAX calculations for reach, outcomes, volunteer equivalent
- **Stakeholder views**: Customizable dashboards per audience

## 📚 Documentation Map

| Document | Purpose |
|----------|---------|
| [`ARCHITECTURE.md`](./ARCHITECTURE.md) | System design and data flows |
| [`DATABASE_DESIGN.md`](./DATABASE_DESIGN.md) | Complete schema documentation |
| [`DEPLOYMENT.md`](./DEPLOYMENT.md) | Step-by-step setup (copy-paste instructions) |
| [`powerapps/SETUP.md`](./powerapps/SETUP.md) | App configuration & customization |
| [`power-automate/CONNECTIONS_GUIDE.md`](./power-automate/CONNECTIONS_GUIDE.md) | Workflow setup & testing |
| [`powerbi/README.md`](./powerbi/README.md) | Dashboard specifications & DAX |
| [`data/DATA_DICTIONARY.md`](./data/DATA_DICTIONARY.md) | Field-level definitions |

## 🔄 Extensibility

- **New program types**: Add to DIM_Programs, create custom outcome measures
- **Additional metrics**: Add calculated fields in Power BI (no code needed)
- **External integrations**: Connect to volunteer management systems, donor databases via Power Automate
- **Scale to database**: Migrate to SQL when data exceeds 100K records/year

## 👨‍💼 Author Notes

This system demonstrates:
- **End-to-end impact tracking** pipeline
- **Low-code/no-code** architecture for rapid deployment
- **Operational BI** for organizational decision-making
- **Scalable design** (Excel → SQL migration path)

Built during professional practice focusing on operations management and data-driven sustainability.

## 📄 License

MIT License - See [`LICENSE`](./LICENSE) file

---

**Questions?** See [`DEPLOYMENT.md`](./DEPLOYMENT.md) for troubleshooting.
