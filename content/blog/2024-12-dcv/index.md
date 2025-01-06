---
title: Decision-centric approach to Impact Based Forecast verification
summary: The goal of IBF is better decision-making, forecast verification must align with this purpose.
date: 2024-12-28

authors:
  # - Nishadh

tags:
# - Decision-Centric-Verification
# - Active Inference
# - Bayesian Networks 
---


## Introduction  

Impact-based forecasting (IBF) is becoming an essential tool for disaster
preparedness and risk reduction. As this approach grows, we need to evaluate
how well these forecasts support real-world decisions by stakeholders, such as
emergency managers, policymakers, and private organizations. Traditional
methods of verifying forecasts mainly focus on statistical accuracy, but these
may not fully capture the practical value of forecasts. This post explores why
it's important to go beyond conventional verification methods and adopt a
decision-centric verification (DCV) framework.  

Traditional weather forecast verification tends to focus too much on technical
accuracy, like RMSE (Root Mean Square Error) or bias scores. While these
metrics are important, they don’t address the real goal: improving decisions.
For example, a forecast that is slightly less accurate but better aligned with
decision thresholds could still be more valuable. Instead of only asking, "Was
the forecast accurate?" we should also ask, "Did this forecast help make better
decisions?" or "Which prediction errors affected the quality of decisions
most?" Decision-centric verification shifts the focus to outcomes, asking, “Did
the forecast lead to actions (e.g., evacuation, resource allocation) that
reduced negative impacts or increased positive outcomes?”

---

## Background  

Traditional weather and hazard forecast verification faces several challenges
when applied to IBF:  

1. It’s hard to collect detailed impact data for validation.  
2. There’s no easy way to measure how forecast accuracy affects real-world
   outcomes.  
3. It’s difficult to assess whether the resulting decisions and actions were
   effective.  
4. The focus is often more on model performance than on practical usefulness.  

---

## Literature Review  

### 1. **Anticipatory Action Literature**  
Research on anticipatory action highlights a shift toward DCV in weather and
climate forecasting. Early studies on using probabilistic forecasts for water
management [1] and more recent work on impact-based verification [2] show how
these methods have evolved. Studies like [3] and [4] focus on bridging the gap
between traditional weather metrics and real-world applications. Humanitarian
organizations [5] and drought forecasting systems [6, 7] have adapted
verification methods to align with decision timelines, action triggers, and
institutional learning. This research emphasizes the importance of making
verification relevant to decision-makers, balancing scientific accuracy with
practical needs in disaster response.  

### 2. **Bayesian Philosophy**  
Bayesian methods are crucial for managing uncertainty and improving decisions.
Bayesian networks, as demonstrated in [8], structure complex relationships
between forecasts, impacts, and outcomes. These networks help address DCV
challenges by modeling dependencies between predictors and handling incomplete
data. Similarly, Russell’s open-universe probability models [9] offer a way to
analyze dynamic scenarios, treating them as "possible worlds" and mapping their
causal relationships. Friston’s Active Inference framework [10] uses Bayesian
updates to continuously improve decision-making under uncertainty, providing a
solid foundation for integrating forecasts, impact assessments, and
verification metrics.  

### 3. **Event-Based Storylines**  
Event-based storylines provide a framework for connecting climate science to
decision-making under uncertainty. Proposed by [11], this method links climate
projections to preparedness decisions. Researchers have expanded it to include
measurable socio-economic impacts [12] and practical flood management
applications [13]. Further work on storylines [14] has focused on reducing
uncertainty and aligning forecasts with stakeholder needs. These storylines map
impact chains across different scales, offering a clear, structured way to
support scenario-based decisions. They also provide a credible narrative for
handling both direct and indirect impacts while maintaining scientific rigor.  

The connection between open-universe probability models, “possible worlds,” and
event-based storylines is highly complementary for DCV in IBF. Both frameworks
handle uncertainty and allow for dynamic scenarios: open-universe models create
flexible structures for new entities, while storylines build coherent event
chains. Together, they help align forecast reasoning with real-world
decision-making, making verification more relevant and useful for stakeholders.  

---

## Conclusion  

To fully realize the potential of impact-based forecasting, we need to shift
from traditional accuracy-focused verification to decision-centric approaches.
By leveraging methods like Bayesian frameworks and event-based storylines, we
can create more actionable and effective forecasts. These tools help
decision-makers focus on what truly matters: reducing risks, saving lives, and
improving outcomes.

---

### References  

1. Lopez, Ana, and Sophie Haines. "Exploring the usability of probabilistic weather forecasts for water resources decision-making in the United Kingdom." *Weather, Climate, and Society* 9.4 (2017): 701-715.  
2. Busker, Tim, et al. "Impact-based seasonal rainfall forecasting to trigger early action for droughts." *Science of the Total Environment* 898 (2023): 165506.  
3. MacLeod, David, Dominic R. Kniveton, and Martin C. Todd. "Playing the long game: Anticipatory action based on seasonal forecasts." *Climate Risk Management* 34 (2021): 100375.  
4. Coughlan de Perez, Erin, et al. "Action-based flood forecasting for triggering humanitarian action." *Hydrology and Earth System Sciences* 20.9 (2016): 3549-3560.  
5. de la Poterie, Arielle Tozier, et al. "Anticipatory action to manage climate risks: Lessons from the Red Cross Red Crescent in Southern Africa, Bangladesh, and beyond." *Climate Risk Management* 39 (2023): 100476.  
6. Guimarães Nobre, Gabriela, et al. "Ready, Set & Go! An anticipatory action system against droughts." *Natural Hazards and Earth System Sciences* 24.12 (2024): 4661-4682.  
7. Nobre, Gabriela Guimarães, et al. "Forecasting, thresholds, and triggers: Towards developing a Forecast-based Financing system for droughts in Mozambique." *Climate Services* 30 (2023): 100344.  
8. Vogel, Kristin, et al. "Bayesian network learning for natural hazard analyses." *Natural Hazards and Earth System Sciences* 14.9 (2014): 2605-2626.  
9. Russell, Stuart. "Unifying Logic and Probability: A New Dawn for AI?." *Information Processing and Management of Uncertainty in Knowledge-Based Systems: 15th International Conference, IPMU 2014, Montpellier, France, July 15-19, 2014, Proceedings, Part I*. Springer International Publishing, 2014.  
10. Parr, Thomas, Giovanni Pezzulo, and Karl J. Friston. *Active inference: the free energy principle in mind, brain, and behavior*. MIT Press, 2022.  
11. Sillmann, Jana, et al. "Event‐based storylines to address climate risk." *Earth's Future* 9.2 (2021): e2020EF001783.  
12. van den Hurk, Bart JJM, et al. "Climate impact storylines for assessing socio-economic responses to remote events." *Climate Risk Management* 40 (2023): 100500.  
13. De Bruijn, K. M., et al. "The storyline approach: a new way to analyse and improve flood event management." *Natural Hazards* 81 (2016): 99-121.  
14. Shepherd, Theodore G., et al. "Storylines: an alternative approach to representing uncertainty in physical aspects of climate change." *Climatic Change* 151 (2018): 555-571.  



