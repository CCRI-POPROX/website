---
subTitle: "" 
title: "Proposed Infrastructure"
img: "/assets/images/projects/project-thumb-two.jpg"
linkText: "Read More"
featureImg1: "/assets/images/projects/project-details-infra.jpg"
featureImg2: ""
---
<p>
The proposed research infrastructure is an integrated system comprising several components
illustrated in Figure 1, many of which are described in more detail below.
● A cloud-based research recommender engine and research management framework. The infrastructure includes a database of indexed news content (provided by the Associated Press), a database of usage logs, a two-stage recommender engine that retrieves and then ranks articles, a meta-ranker to select and/or mix different recommenders, presentation interfaces (initially for newsletter delivery, but later for interactive news browsing), an experiment manager/dispatcher that invokes the appropriate recommender components for each end-user based on experiments in which the user is enrolled), an embedded survey tool to support interactive surveys and feedback, and a logging/analysis/reporting system with support for standardized and validated metrics.
● An end-user population, recruited for this infrastructure, together with a central IRB-reviewed consent process and compensation/incentive mechanisms to elicit overall participation and/or participation in specific experiments.
● A suite of research services and outreach activities, including documentation and sample experiments, workshops and tutorials, datasets to support researchers, an IRB kit to permit streamlined human subjects review (all experiments must comply with central IRB guidelines and are then reviewed by the researchers’ local IRB for the specifics of the experiment) , and a researcher support team to work with researchers.
● Community-based governance with a community advisory board including researchers as well as representatives of the content providers and end users.
We recognize that research infrastructure that includes end users is challenging, but it is exactly what the research community is missing. There is no shortage of software toolkits and datasets, but fewer and fewer researchers are carrying out experiments with actual human users. We are mindful of the lessons from TREC Open Search in which low usage made it difficult to obtain useful results. We have extensive experience building long-lived research infrastructure including users, most notably our MovieLens system which has since 1997 registered more than 320,000 users who have collectively contributed more than 31 million movie ratings plus 2.2 million tags and 3.3 million other actions. Most important, we maintain sufficient ongoing usage levels to carry out research (more than 4000 active users in any month with 80% of them longer-term users). Our partnership with AP, and integration with their newsletter, will provide a significant further boost to user acquisition. Any project of this nature has risks, but our team is well-positioned to succeed, and the resulting scientific progress will be substantial.

<b>Fundamental Infrastructure.</b>
Figure 1 depicts the proposed technical architecture, which we describe in more detail below. We will use or extend existing open-source software and cloud infrastructure (AWS) to support the technical infrastructure of the application wherever possible, and will be collaborating with other research groups where appropriate (notably Prof. Bernstein’s group at the University of Zurich which developed news aggregation and display technology for their German-language news system studies). Specific software infrastructure to be re-used includes: ElasticSearch (text indexing and candidate retrieval), PostgreSQL (data storage, including user and experiment management), LensKit and TorchRec (ranking models), LensKit REST server (ranking API), Docker (platform infrastructure), and components of our pre-existing MovieLens experimental framework (user-experiment mapping and management). Development will follow agile software engineering processes (specifically, Scrum), with specific proposed experiments driving the evolution of specifications for the various components (we have an initial set of six model experiments for phase I). We recognize the significant integration challenge here (which is why we are staffing this with a full-time and a part-time professional software engineer), but from our experience believe the project is feasible in the planned timeframe.

<b>Data Storage</b> The ecosystem will have two primary data stores. The article index will store news articles from AP (and other sources) and expose them to the rest of the platform for both retrieval and analysis. We expect to use ElasticSearch or Apache Solr to implement this part of the platform.
The platform database will store all other data produced or collected by the platform in a relational database (e.g., PostgreSQL), including: user account and profile data; current and past user assignments to experimental conditions; recommendation and usage logs, including recommendations delivered, algorithms configurations/experimental conditions, and resulting user actions; survey responses; user activity logs; and system activity logs. This database will facilitate both recommendation (by storing the user interaction signals needed to produce personalized recommendations) and experimental results (both by logging user responses to recommendations and questionnaires and enabling bulk re-analysis of user activity and system responses).
</p>