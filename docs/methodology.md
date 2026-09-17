# Methodology

**Status: planned workflow.** The procedures below define how the study will be carried out. They do not report completed site work, verified geometry, simulation outputs or validated results.

## 1. Document the site

Select and record the study boundaries on Sydhavnsgade, Copenhagen. Use Google Earth for aerial context and on-site photographs for visible road details, lighting infrastructure and surrounding conditions. Supplement missing viewpoints with street-level imagery where useful.

Record the source, capture or access date, location or viewpoint and intended use of each reference. Note uncertain features and differences between images taken at different dates. Keep source attribution with any published reference material and check its permitted reuse before including it in the repository or portfolio.

Daytime photographs can document visible infrastructure; they do not measure night-time lighting performance. Do not infer exact dimensions, luminaire photometry or verified material properties from appearance alone.

## 2. Establish the input register

Create a register before modelling. For each input, record its name, value, unit, source, evidence status, uncertainty or limitation, review status and the model version using it. Unresolved values remain marked as unknown; no placeholder should be mistaken for a measured input.

| Evidence status | Meaning in this study |
| --- | --- |
| Observed | A visible qualitative feature supported by a site reference |
| Estimated | An approximate value inferred from incomplete evidence, with the method recorded |
| Assumed | A deliberate study input selected without site verification |
| Measured | A value obtained using a recorded measurement method and date |
| Verified | A value checked against identifiable supporting evidence, with the check documented |

Keep design variables distinct from existing-site evidence. Checking a model against an assumed width verifies implementation of the assumption, not the actual road width. A measured value should retain its method and uncertainty when subsequently verified.

## 3. Develop the AI-assisted Rhino model

Provide GPT Astra with the visual references and the input register to assist Rhino modelling and scripting. The register controls dimensions; imagery informs context. If an input is unresolved, record the gap or use an explicitly labelled provisional assumption rather than silently inventing a dimension.

Separate road surfaces, pedestrian or cycle areas where present, poles, buildings and vegetation into identifiable layers. Keep contextual detail proportionate to the study. Record the AI-assisted tasks, substantive modelling choices and corrections made by the author.

Review units, orientation, cross-section, object locations and agreement with the input register. The resulting context model remains an interpreted representation of the site.

## 4. Define the engineering abstraction

Prepare a simplified geometry specification for lighting calculation. Define the calculation areas, cross-section, lighting arrangement and relevant mounting parameters. Record which contextual features are retained or omitted and why.

Maintain two explicit records: the evidence supporting the input values, and the check that the calculation model implements those values correctly. Assumptions may be accepted for a bounded study without being relabelled as verified site geometry.

Rhino geometry is not assumed to transfer directly into the road-lighting calculation workflow. Confirm the supported exchange route or rebuild the calculation geometry from the reviewed specification in DIALux evo. Check dimensions, units and orientation after either route.

## 5. Establish lighting requirements

Use *Håndbog Vejbelysning* as the planned Danish guidance reference. The 2024 edition discussed during project planning is a starting reference; confirm the edition and applicability before extracting requirements. Review the relevant referenced calculation basis and any site-specific conditions needed for class selection.

Create a requirements register recording the source title, edition, section or page, assessment area, selected class, metric, unit, limit, comparison direction and selection rationale. Document unresolved classification inputs instead of selecting a class from the road name or a photograph alone.

No numerical thresholds or compliance assertions are established by this methodology. Confirm that the chosen DIALux workflow can represent the selected requirements and explicitly record any gaps.

## 6. Configure and run DIALux evo

Build Design A using the reviewed geometry specification and requirements register. Record the software version, project revision, luminaire identity, manufacturer photometry file and the settings needed to reproduce the calculation.

The input record will include applicable mounting and orientation parameters, maintenance assumptions, road-surface assumptions, calculation areas or grids and any other settings relevant to the chosen assessment. Record photometry sources and distinguish luminaire power from luminous output.

Review the model before calculation. Preserve the project and exported report for each completed run. A contextual rendering is not a calculation result and will not be presented as one.

## 7. Iterate through Designs A, B and C

Use A as the initial study baseline. Review its actual results before selecting changes for B; use evidence from A and B to define C. Record the hypothesis, variables changed, expected effect and observed effect for each iteration.

Keep requirements, assessment areas and other comparison settings consistent where possible. If the comparison basis changes, explain the change and rerun affected scenarios. Prefer changes whose effects can be interpreted; when several variables change together, acknowledge that their individual effects cannot be isolated from that comparison alone.

Do not label a configuration as the measured existing installation without supporting evidence. Further iteration remains possible if A, B and C do not provide an acceptable outcome. Version 1 does not use NSGA-II or an automated optimisation loop.

## 8. Structure actual simulation data

Add datasets only after results exist. Preserve original reports separately from analysis tables and link every extracted value to its source. The planned data structure is:

| Record | Minimum information |
| --- | --- |
| Run | Run ID, design ID, project revision, software version, date, source report |
| Input | Run ID, parameter, value, unit, evidence status, source |
| Result | Run ID, assessment area, metric, value, unit, report location |
| Requirement | Requirement ID, area, metric, unit, limit, operator, source and rationale |
| Check | Run ID, requirement ID, result reference, outcome and review note |

Missing data will remain missing, not zero. Keep rounding for presentation separate from stored precision. Check extracted or transcribed values against the source reports before analysis.

## 9. Analyse with Python

Use Pandas to organise the datasets, NumPy for numerical operations and Matplotlib for comparison figures. Document dependencies and execution instructions when analysis code is added.

Check required fields, units, duplicates, missing values and run identifiers before comparing designs. Apply the correct comparison direction for each documented requirement. Use explicit outcomes such as pass, fail, not assessed or not applicable; missing data or unresolved requirements must not become a pass.

Compare lighting performance and installed power on the same stated basis. Calculate annual energy only when operating schedules and control assumptions are recorded. Keep any derived quantities traceable to their inputs and equations.

Python checks data processing and requirement comparisons. It does not replace DIALux photometric calculation or independently establish real-world lighting performance.

## 10. Review and validate

Review the chain from evidence to geometry, calculation setup, exported outputs and analysis. Check that the model matches the input register, selected requirements are implemented correctly, and analysis values agree with the source reports.

Investigate consequential uncertainties through targeted sensitivity runs where practical. Record which conclusions change when uncertain inputs vary. Distinguish numerical consistency checks, requirements assessment, independent calculation checks if performed, and field measurement validation; do not claim one as another.

Keep unresolved limitations visible. Simulation-based assessment is conditional on the model and its assumptions; authority approval and field photometric validation are not part of the current scope.

## 11. Make the engineering decision

Review Designs A, B and C against the documented requirements first, then assess energy implications, practical constraints and sensitivity to assumptions. Explain the selected configuration and its trade-offs using traceable evidence. If none is acceptable, document the need for further work instead of declaring a successful design.

The decision record will state the evidence used, rejected alternatives, uncertainty, remaining verification needs and the limits of the recommendation.

## 12. Communicate the study

Prepare a portfolio narrative linking the real site, context model, engineering abstraction, design iterations, analysis and decision. Label photographs, AI-assisted visualisations, calculation outputs and analysis figures by their actual role.

Describe the author's engineering decisions and the AI assistance accurately. Publish completed work as evidence becomes available, with source references, assumptions and limitations alongside results. Update the README status to reflect actual progress rather than the intended final outcome.
