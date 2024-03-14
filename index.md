---
layout: home
title: "Cera"
---


<!-- [Link to another page](./another-page.html).

[Link to methods page](./models.html). -->
# Why Did We do This
Current utility report process consists of:
- **Members of the public having  to communicate their concerns with the call center which will direct them to the proper department** 
- **SDG&E’s immediate response team is sent out based on a description of the issue by callers that may carry ambiguity**
- **Room for difficulty in accurately assessing and describing the problem**
## Pain point:
SDG&E cannot fully evaluate the problem without sending out experts into the field which is resource intensive and time consuming

As readily available electricity grows in the essential role it plays in functioning society, mitigating potential power outages by way of faulty electric equipment is a top priority for utility companies. Raising alerts on deficient electric structures not only ensures the continued distribution of electricity, but prevents safety hazards, such as wildfires and road blockages as well. Current utility management relies in large part on the general public to report potentially dangerous equipment through phone calls, which are beneficial as a baseline alert and evaluation. However, response teams at companies like SDG&E are not able to fully assess the problem without first sending out teams to inspect the damage, which is resource intensive and time consuming. Our project attempts to optimize this system by envisioning a platform where members of the public can submit images and a description of problems they see with poles, with machine learning models that will evaluate this information to determine the degree of urgency of the equipment’s condition. Rather than create the platform itself, this paper represents a proof of concept, with the application of three models on sample and manually derived data. To account for the diversity of images that may come from a public platform or app, we optimized a pre-trained object detection model to identify poles from images with a variety of qualities. To then gain insights from given text descriptions of the problem, we applied two natural language processing (NLP) models on sample disaster tweet data to gauge the topic and sentiment from reports. Applying these models serve as evidence of the potential that manual platforms for reporting electrical structures promise for utility companies in the future.
