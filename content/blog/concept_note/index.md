---
title: Concept Note- E4DRR
summary: Hazard modeling, impact estimation, climate storylines for event catalogue on drought and flood disasters in the Eastern Africa.
date: 2024-08-31

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.

authors:
  # - Nishadh

tags:
  # - Academic
#- Hugo Blox
# - Markdown
---

## Activites of project:

## Outcome 1. Enhanced Risk Knowledge and Awareness Through the Creation of Event-Based Climate Storylines {#outcome-1} 

**Work package 1** Establish Hazard and Impact Modelling for the Region: Setting up of hazard and impact modelling for the region

* **Activity 1.1.1** EPS Data API for storylines
    * Organize and implement cost-effective programming routines for Ensemble Prediction System (ERA5 and GEFS) to be used for storylines creation as an Application Programming Interface (API).

* **Activity 1.1.2** Hazard Models Input Data API
    * Collect static data related to parsimonious hazard models along with dynamic input data as an Application Programming Interface (API).

* **Activity 1.1.3** Hazard Models Drought DevOps WPS
    * Set up the hazard model for Drought (CWALID) for validation and training schemes for operational purposes on cloud computing as a Development Operations (DevOps) Web Processing Services (WPS).

* **Activity 1.1.4** Hazard Models Flood DevOps WPS
    * Set up the hazard model for flood (RIM2D) for validation and training schemes on GPU hardware and for operational purposes on cloud computing with Web Processing Services (WPS).

* **Activity 1.1.5** Impact Modeling Input Data API
    * Collect static data required for impact calculations in CLIMADA, including exposure data, vulnerability defined in terms of impact functions, and hazard model outputs as an Application Programming Interface (API).

* **Activity 1.1.6** Impact Modeling DevOps WPS
    * Set up the CLIMADA impact calculation tool using the hazard model outputs as input as a Development Operations (DevOps) Web Processing Services (WPS).

**Work package 2** Implement Co-development Method for Event-Based Climate Storylines: Implement a co-development method for event-based climate storylines

* **Activity 1.2.1** Collect Documented Hazard Data and select events
    * Collect available documented hazard datasets related to flood and drought disasters in the 11 East African countries for the period 2000-2024. Select 11 flood and 11 drought events for each country in EAHW.

* **Activity 1.2.2** Simulation of Hazard-Impact models
    * Perform the hazard and impact modeling for the selected events using observed weather conditions as references for factual storylines based on documented hazards. 

* **Activity 1.2.3** Story Map Development
    * Design and develop story maps based on the reference storylines datasets.

* **Activity 1.2.4** Co-production Initiatives
    * Conduct preliminary coproduction activities to scope and select representative events for drought and flood in the respective countries.

**Work package 3** Consolidate Composite Dataset and Storylines into Story Maps Linked with EAHW: Consolidate the composite dataset and storylines as story maps and link with East Africa Hazard Watch (EAHW) web application

* **Activity 1.3.1** Multiple Simulations of Hazard-Impact Models 
    * Run the hazard and impact models in storylines mode for each selected event and obtain counterfactual initiation data from the rainfall forecast members of the EPS.

* **Activity 1.3.2** Storylines Organization in Story maps
    * Organize the outputs of the hazard and impact models into storylines by extending the story maps from WP2 and link them with EAHW.

* **Activity 1.3.3** Bayesian Network Development 
    * Develop causal and Bayesian networks to represent the storylines, along with a web interface for coproduction. 

* **Activity 1.3.4** Co-production Validation
    * Conduct a second-stage coproduction process to validate and optimize the storylines, utilizing the Bayesian network web interface.

* **Activity 1.3.5** Experiment Gen AI for event-based climate storylines
    * Explore the role of Generative AI Large Language Models (LLMs/chatGPT) in Bayesian and causal network creation and provide chat support with storylines narrative.

## Outcome 2: Exploration of Storylines creation processes and applications in Ensemble Prediction System (EPS) Impact-Based Forecasting (IBF) {#outcome-2}

**Work package 4** Establish an Analysis and Forecast Validation Facility Utilizing Storylines Datasets and Processes for Anticipatory Action: Develop analysis and forecast validation facility utilizing storyline dataset and processes for anticipatory action

* **Activity 2.1.1** Ensemble Prediction System (EPS) forecast verification and Extreme Value Analysis (Thresholds and Triggers) WPS
    * Utilize the EPS used for storylines, GEFS for flood and SEAS5 for drought, their last 20 years hindcast for extreme value analysis on cloud computing as a Development Operations (DevOps) Web Processing Services (WPS).

* **Activity 2.1.2** Web interface for Anticipatory Action 
    * Following anticipatory action analysis routines on extreme value analysis for thresholds, forecast verification to set triggers utilizing impact data from storylines. Provide an analytical platform in a web interface through a Jupyter notebook-based setup.

**Work package 5** Demonstrate the Application of Storylines as Bayesian Networks in IBF Risk and Decision Analysis

* **Activity 2.2.1** Storylines Synthesis 
    * Synthesize the storylines into a single Bayesian network for use in IBF.

* **Activity 2.2.2** Bayesian Network Backend Development
    * Develop backend code for real-time EPS data download for flood and drought, operationalize semi-automated hazards and impact modeling, and perform risk and decision analysis.

**Work package 6** Operationalize EPS IBF with Hazard and Impact Modelling for the Region
Operationalize EPS IBF with hazards and impact modeling for the region

* **Activity 2.3.1** Cloud-native EPS IBF DevOps WPS
    * Set up programming routines for interoperable data consumption and dissemination of project datasets, following the EPS IBF routines in cloud-native operations (CNO) and Analysis Ready, Cloud Optimized data formats (ARCO) as a Development Operations (DevOps) Web Processing Services (WPS).

* **Activity 2.3.2** IBF dissemination in EAHW layer/API
    * Create a web application that shows backend processes with integration on Bayesian networks for operational Early Warning Early Action (EWEA) IBF, including workflow visualization for auditability of evidence for non-public operation center consumption. End product from IBF workflow in ICPAC climate services and EAHW dissemination in Application Programming Interface (API).

* **Activity 2.3.3** Experiment generative AI for EPS
    * Explore the application of Generative AI (cGAN) in bias correction and downscaling of EPS data in an operational setup.

## Outcome 3: Capacity Development in the Use of Methods and Tools for Storyline Creation {#outcome-3}

**Work package 7** Develop Documentation and Training Materials on Methods and Tools Used in Storyline Creation Activities
Prepare documentation and training materials on methods and tools used in storyline creation

* **Activity 3.1.1** Open Sourcing the software programs used for storylines tools and methods
    * Open source the scripts and methodology for hazard modeling, impact estimation, Bayesian networks, operational downloading of EPS, story maps, interactive Bayesian networks.

* **Activity 3.1.2** Documentation on the software programs used for storylines tools and methods
    * Create documentation for hazard modeling, impact estimation, Bayesian networks, operational downloading of EPS, story maps, interactive Bayesian Networks.

* **Activity 3.3.3** Tutorials on storylines tools and methods
    * Tutorial development on hazard modeling, impact estimation, Bayesian networks, EPS in Jupyter notebooks.

**Work package 8** Conduct Capacity Development Activities in Co-development, Workshops, and Tutorials
Capacity development activities in co-development, workshops, and tutorials

* **Activity 3.2.1** Conduct Capacity Development
    * Conduct workshops and tutorials for capacity development by utilizing the ongoing activities at ICPAC and along with co-development events.

