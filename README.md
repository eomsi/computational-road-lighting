# Computational Road Lighting

An independent technical study of road-lighting design at Sydhavnsgade, Copenhagen.

This project will investigate how site documentation, AI-assisted Rhino modelling, DIALux evo simulation and Python analysis can support a traceable engineering design decision. The first version will compare three deliberately developed configurations-Design A, B and C-and explain the trade-offs behind the final selection.

Status: Phase 0 - Project setup. This repository currently contains the project brief and planned methodology. On-site photography, geometry verification, lighting-class selection, simulations and performance analysis remain to be completed. No measured dimensions, DIALux results or validated performance claims are published at this stage.

## Engineering question

How can alternative lighting configurations for a defined section of Sydhavnsgade be compared against documented lighting requirements, energy use and practical design constraints?

The study will focus on the reasoning behind each iteration: what changes, why it changes, how performance is checked and what uncertainty remains.

## Planned workflow

```text
Google Earth + on-site photography
  -> GPT Astra-assisted Rhino modelling
  -> Engineering abstraction and input review
  -> Håndbog Vejbelysning requirements
  -> DIALux evo simulation
  -> Design A / B / C iteration and re-simulation
  -> Structured simulation data
  -> Python / NumPy / Pandas / Matplotlib analysis
  -> Validation
  -> Engineering decision
  -> Portfolio communication
```

Street-level imagery may supplement gaps in the visual record. The exact study boundaries, dimensions and applicable lighting requirements will be established and documented before calculation.

## Evidence and engineering geometry

Site references and calculation inputs serve different purposes:

| Evidence or model | Intended use | Limitation |
| --- | --- | --- |
| Google Earth and on-site photographs | Understand the road layout, surroundings and visible infrastructure | Visual references do not establish verified dimensions or lighting performance |
| AI-assisted Rhino model | Reconstruct and communicate site context; support geometry preparation | AI-generated geometry requires review and is not survey evidence |
| Engineering input register | Record dimensions, sources, assumptions and design variables | Assumed values remain labelled as assumptions, even after internal review |
| DIALux calculation model | Evaluate defined lighting configurations | Results depend on the documented geometry, photometry and calculation settings |

Each geometry input will be identified as observed, estimated, assumed, measured or verified, with its source and review status recorded. A model check can confirm that geometry matches an input specification; it cannot turn an assumed dimension into a verified site measurement.

## Version 1 scope

- Document one selected road section and define a simplified calculation model.
- Establish applicable requirements from *Håndbog Vejbelysning* and the relevant referenced calculation basis, recording edition and source details.
- Develop and simulate Designs A, B and C using documented luminaire photometry.
- Structure actual simulation outputs for reproducible comparison in Python.
- Check performance against the selected requirements and explain the resulting engineering decision.

Version 1 uses engineering-led iteration. Automated optimisation, including NSGA-II, is outside the current scope and is not claimed as an implemented capability.

## Planned toolchain

| Purpose | Tools and references |
| --- | --- |
| Site documentation | Google Earth, on-site photography, supplementary street-level imagery |
| Modelling support | GPT Astra, AI-assisted scripting, Rhino |
| Lighting calculation | DIALux evo, manufacturer LDT / IES photometry, Håndbog Vejbelysning |
| Data analysis | Python, NumPy, Pandas, Matplotlib |
| Documentation | Git, GitHub, portfolio figures and narrative |

These are the intended tools for the study; their inclusion does not imply that the workflow has already been implemented. AI will support modelling, scripting and communication. Engineering inputs, requirements, calculation settings and design decisions will be reviewed by the study author.

## Repository guide


