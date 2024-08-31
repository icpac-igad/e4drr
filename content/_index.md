---
title: "Home"
date: 2023-10-24
type: landing

design:
  # Default section spacing
  spacing: "6rem"

sections:
  - block: hero
    content:
      title: E4DRR 
      text: |
        - 🧱 "Risk knowledge is an essential component of effective disaster
          risk management. The available impact data from previous disasters
          serve as invaluable tools for disaster preparedness and
          decisionmaking support. The project, titled "Hazard Modeling, Impact
          Estimation, Climate Storylines for Drought and Flood Disasters in
          Eastern Africa" (short form “E4DRR”), is a two-year project
          funded by the Complex Risk Analytics Fund (CRAF’d) and
          implemented by ICPAC in collaboration with NORCAP." 🧱 
          
      #primary_action: # text: Get Started
      #url: https://hugoblox.com/templates/
      #icon: rocket-launch
      #secondary_action:
      # text: Read the docs
      #url: https://docs.hugoblox.com
    design:
      spacing:
        padding: [0, 0, 0, 0]
        margin: [0, 0, 0, 0]
      # For full-screen, add `min-h-screen` below
      css_class: "dark"
      background:
        color: "navy"
        image:
          # Add your image background to `assets/media/`.
          filename: tech.jpg
          filters:
            brightness: 0.5
  - block: features
    id: features
    content:
      title: Aim and Objectives
      text: To enhance the East Africa Hazard Watch Portal as a decision-making and actionable information tool for Disaster Risk Management (DRM) through impact-based forecasting based on a chain of auditable evidence synthesised from event-based climate Storylines 🌍
      items:
        - name: Enhanced Risk knowledge
          icon: magnifying-glass
          description:  Enhanced Risk Knowledge and Awareness Through the Creation of Event-Based Climate Storylines
        - name: Operationalizing Impact Based Forecasting
          icon: code-bracket
          description: Exploration of Storylines creation processes and applications in Ensemble Prediction System (EPS) Impact Based Forecasting (IBF)
        - name: Capacity Development
          icon: star
          description: In the Use of Methods and Tools for Storyline Creation 
  - block: cta-image-paragraph
    id: solutions
    content:
      items:
        - title: Enhanced Risk knowledge
          text: Composite Impact dataset for risk knowledge and awareness
          feature_icon: check
          features:
            - "Work package 1 Establish Hazard and Impact Modelling for the Region: Setting up of hazard and impact modelling for the region" 
            - "Work package 2 Implement Co-development Method for Event-Based Climate Storylines: Implement a co-development method for event-based climate storylines"
            - "Work package 3 Consolidate Composite Dataset and Storylines into Story Maps Linked with EAHW: Consolidate the composite dataset and storylines as story maps and link with East Africa Hazard Watch (EAHW) web application"            
          # Upload image to `assets/media/` and reference the filename here
          image: impact_data.png

        - title:  Operationalizing Impact Based Forecasting 
          text: Ensemble Prediction System (EPS) Impact Based Forecasting (IBF)
          feature_icon: bolt
          features:
            - "Work package 4 Establish an Analysis and Forecast Validation Facility Utilizing Storylines Datasets and Processes for Anticipatory Action"
            - "Work package 5 Demonstrate the Application of Storylines as Bayesian Networks in IBF Risk and Decision Analysis"
            - "Work package 6 Operationalize EPS IBF with Hazard and Impact Modelling for the Region Operationalise EPS IBF with hazards and impact modelling for the region"
          # Upload image to `assets/media/` and reference the filename here
          image: bulletin.png

        - title:   Capacity Development 
          text: In the Use of Methods and Tools for Storyline Creation
          feature_icon: bolt
          features:
            - "Work package 7 Develop Documentation and Training Materials on Methods and Tools Used in Storyline Creation Activities"
            - "Work package 8 Conduct Capacity Development Activities in Co-development, Workshops and Tutorials"
          # Upload image to `assets/media/` and reference the filename here
          image: bn-dm.png

    design:
      spacing:
        # Reduce bottom spacing so the testimonial appears vertically centered between sections
        padding: ["6rem", 0, 0, 0]
  - block: cta-card
    content:
      title: Coimposite Impact Dataset DevOps IBF
      text: Quick updates on the Development.  <br>   <small> Disclaimer-The content of this website does not reflect the official opinion of the Funding agency or partner organizations. Responsibility for the information and views expressed in the web lies entirely with the authors  </small>.
      button:
        text: Learn more
        url: /blog
    design:
      card:
        # Card background color (CSS class)
        css_class: "bg-primary-700"
        css_style: ""
---
