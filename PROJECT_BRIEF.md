# Project Brief

## Project definition

| Item | Definition |
| --- | --- |
| Project | Computational Road Lighting |
| Type | Independent technical study |
| Site | Sydhavnsgade, Copenhagen, Denmark |
| Current phase | Phase 0 — Project setup |
| Version 1 approach | Engineering-led Design A / B / C comparison |
| Study boundaries | To be selected and documented |

## Objective

Develop a transparent workflow connecting real-world site references to lighting requirements, simulation results and an engineering design decision. The intended outcome is a documented comparison that explains both numerical performance and the assumptions behind it.

The repository and subsequent portfolio will make the author's engineering contribution visible through input selection, geometry abstraction, requirements interpretation, controlled design iteration and critical review.

## Scope

Version 1 will cover one selected section of Sydhavnsgade. Its calculation extent, road cross-section and treatment of any pedestrian or cycle spaces will be defined after site review. No road width, lane count, pole spacing, mounting height or study length is fixed by this brief.

The planned work comprises:

1. Collect aerial context and on-site photographs; record sources, dates and viewpoints.
2. Use GPT Astra to assist Rhino modelling and scripting from an explicit input specification.
3. Separate contextual geometry from simplified engineering geometry and document all unresolved inputs.
4. Determine the applicable lighting class and requirements using *Håndbog Vejbelysning* and relevant referenced material.
5. Configure a DIALux evo calculation model with documented LDT / IES photometry and calculation settings.
6. Develop Designs A, B and C, recording the rationale and changes for each iteration.
7. Extract actual calculation outputs into structured data with units and source references.
8. Use Python, NumPy, Pandas and Matplotlib to compare designs and check requirements.
9. Review input quality, calculation consistency and sensitivity to consequential assumptions.
10. Record the engineering decision and communicate the process through GitHub and a portfolio.

## Design strategy

| Design | Planned role | Evidence required |
| --- | --- | --- |
| A | Initial reference configuration for the study | Documented inputs and first calculation report |
| B | Targeted response to a limitation or trade-off identified in A | Change log, rationale and comparable calculation report |
| C | Further refinement informed by A and B | Change log, rationale and comparable calculation report |

Design A will be called an existing-condition model only if the installed geometry and equipment are sufficiently supported by evidence. Otherwise, it will remain a study baseline. No design is assumed to pass the requirements or outperform the others.

## Candidate variables and metrics

Potential design variables include pole spacing, mounting height, arrangement, setback or overhang, luminaire optics, luminous output and tilt. Feasible ranges and fixed inputs will be defined after site and requirements review.

Performance metrics will be selected only after the applicable requirements and assessment areas are established. Candidates include the relevant luminance or illuminance measures, uniformity and glare measures, alongside installed power. Annual energy will be considered only if operating hours, dimming and control assumptions are explicitly defined.

This list is a planning framework, not a selection of a lighting class, a set of numeric acceptance limits or a compliance claim.

## Evidence and validation boundaries

- Photographs and aerial imagery describe visual context; they do not by themselves verify dimensions.
- Measured inputs will include the method and date. Inputs described as verified will include supporting evidence and a documented check.
- Estimates and study assumptions will retain their labels throughout modelling and analysis.
- DIALux evo is the planned primary lighting calculation environment. Python will process outputs, compare scenarios and implement documented requirement checks.
- Agreement between a Python table and a DIALux report checks data handling; it is not an independent physical validation of the lighting simulation.
- No field photometric validation, authority approval or construction-ready design is included in the current deliverables.

## Planned deliverables and completion criteria

| Deliverable | Completion criterion |
| --- | --- |
| Site record | Study boundaries, source register and annotated observations documented |
| Geometry definition | Input register and reviewed calculation geometry, with assumptions visible |
| Requirements register | Applicable classes, metrics, limits, source sections and selection rationale recorded |
| Design comparison | A / B / C inputs and actual DIALux reports available on a consistent basis |
| Analysis | Traceable dataset, runnable analysis and figures tied to source outputs |
| Validation record | Input checks, requirement checks, unresolved issues and sensitivity findings documented |
| Engineering decision | Selection or need for further iteration justified against evidence and constraints |
| Portfolio summary | Concise explanation of the author's work, AI assistance, results and limitations |

All deliverables above are planned. The initial repository contains documentation only.

## Out of scope for Version 1

Automated search, NSGA-II and other optimisation algorithms are potential later extensions, not completed work or evidence of proficiency. A wider study area, detailed asset survey, construction documentation and field lighting measurements would require a separate scope decision.

## Immediate next steps

Select the study boundaries, collect daytime site photographs and establish an initial evidence and geometry register. Then resolve the calculation inputs and requirements needed to build Design A.
