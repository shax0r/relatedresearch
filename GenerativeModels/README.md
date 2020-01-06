Generative Models
=====

This folder contains research related to the use of generative models in AI.

## 2019
---

### Collier, et al.

- [MAMS: Multi-Agent MicroServices](Collier, et al-2019 Multi-Agent MicroServices.pdf)

   [Collier](https://people.ucd.ie/rem.collier/), [O'Neill](https://people.ucd.ie/eoin.oneill/), [O’Hare](https://people.ucd.ie/gregory.ohare/), and [Lillis](https://people.ucd.ie/david.lillis/) demonstrate, in their article,the integration of agent technology into microservices-based systems by leveraging on the similarities between agents and microservices approaches.  Following close similarities underlying the design principles of both multi-agent systems and microservices, the authors propose a class of system comprising Plain-Old MircroServices (POMS) and Agent-Oriented MicroServices (AOMS): MAMS. The authors use the Organization as a Service (OaaS) model to conceptualize the design and operation of the proposed MAMS framework. Through the model, the authors introduce the idea of reusable components of a larger microservices architecture where AOMS would provide standardized implementations of common organizational structures and auctions. The adopted OaaS model dictates the internal mechanism of implementations to use agents, whereas the external interface is realized as a set of Representational State Transfers (REST) resources, allowing both AOMS and POMS to use them. The MAMS concept, developed through the illustration of the Vickery auction as a service, in the article, demonstrates seamless exposure of agents’ internal states and inboxes as resources to traditional microservices, through a REST API interaction. The REST API interactions are supported by the ASTRA Message Service tool and the [FIPA-ACL](http://www.fipa.org/repository/aclspecs.html)  messaging to expose agents’ virtual resources as well as inboxes. The proposed MAMS model adapted the ASTRA programming language to support the creation of virtual resources and FIPA-ACL based communication via RESTful inboxes. That means the MAMS model builds an internal network of resources (States of agents and agent inboxes) supported by Agent communication language as well as ASTRA Message Service, and links the internal resources marked ‘public’ and identified through a globally unique Uniform Resource Identifier to the external entities (microservices) via RESTful inboxes. To make the developed MAMS framework consistent with the [Continuous Integration/Continuous Delivery model](https://en.wikipedia.org/wiki/CI/CD) characterizing microservices-based approaches, the authors restructured ASTRA into a set of Maven artifacts by re-engineering the ASTRA compiler to work as part of a Maven Plugin that can be easily integrated into its build lifecycle.  

   - **Key Takeaways:** 
   •	The illustrated MAMS can be used seamlessly by other microservices. This can be easily extended to include external agents through the use of FIPA-ACL and public inboxes.
•	The illustrated MAMS structure adapts the OaaS model, which dictates the internal mechanism of implementations to use agents, whereas the external interface is realized as a set of Representational State Transfers (REST) resources, allowing both AOMS and POMS to use them.
•	The proposed MAMS model adapted the ASTRA programming language to support the creation of virtual resources and FIPA-ACL based communication via RESTful inboxes.
•	The proposed MAMS model compels re-engineering of the ASTRA compiler, used to create virtual resources, to conform to the Continuous Integration/Continuous Delivery model characterizing microservices-based approaches
•	Even though the demonstrated MAMS model majors on the similarities of the principles characterizing both agents and microservices, certain inconsistent aspects like the bounded context of agents interfere with their mobile interaction with microservices, because agents are bound to a specific Uniform Resource Identifier.

   - **What can go wrong:**
  The association of every agent resource with a globally unique URL limits the mobility of agents, thus hindering the extent of interaction with microservice requests. The redirection process increases run-time, which may lead to delays in the case of multiple concurrent requests. Delays can also emanate from transaction limits set on a particular MAMS platform.
   - **What to look out for:** 
   •	Embracing Web models to provide a simple decentralized global unique naming system for agents can act as a basis for driving new decentralized approaches to build MAS.
•	The demonstrated MAMS framework is an essential step in achieving a longer-term goal of realizing Hypermedia MAS: agent-based systems that can discover, consume and integrate hypermedia services that act as an enabler for Semantic Web and Linked Data systems.

  - **Why the structure is superior:** 
 •	The MAMS approach presents a framework that can be used seamlessly by other microservices and can be easily extended to include external agents through the use of FIPA-ACL and public inboxes.
•	The MAMS approach provides a library of reusable solutions that other auctions and organizational mechanisms can adapt. 
•	The MAMS structure offers secure solutions by only exposing agents that need to interact with external systems. 
•	The alignment of MAMS deployment with industry best practice allows developers to leverage on a wide range of industry-standard tools and components available to microservices-based systems.
•	The implementation strategy and concrete agent technologies are well defined in the demonstrated MAMS structure. 
•	The demonstrated MAMS framework is made consistent, through re-engineering of the ASTRA compiler, with the Continuous Integration/Continuous Delivery model, which characterizes microservices-based approaches


    
  


### Born, et al.

   This research contributes towards enhancing the efficacy of candidate anticancer drug compounds by ensuring their desired chemical properties are specifically tailored to the specific cellular environment or gene expression profile of a tumor cell that the compounds intend to act. The research presents a deep RL-based model for anticancer molecule generation that, for the first time, enables the generation of novel anticancer compounds while taking into account the disease context, which is encoded in the specific gene expression profile (GEP) of a tumor cell. The research demonstrates the possibility of optimizing, using RL optimizing framework, the proposed anti-cancer compound generative model to produce candidate compounds with high predicted efficacy (IC50-the micromolar concentration necessary to inhibit 50% of the cells in a sample) against a given target GEP. 

   The proposed model is reported to have a capacity of proposing novel molecular structures from a chemical space of about 1030 to 1060 molecules. The research successfully validated an estimated 96.2 percent of the generated molecules. 
   - **Inputs:** RNA-Sequence gene expression profiles from cancerous and healthy human tissues ([transcriptomic data](https://www.ncbi.nlm.nih.gov/pubmed/20972753)), test and train molecular datasets from credible databases, IC50 drug sensitivity data, as well as bioactive drug-like molecular data. 
   - **Outputs:** Generated molecular structures, Morgan fingerprints (ECFP) of the generated molecules, and a candidate compound. 
   - **Significant Structure:** The most crucial elements of the presented research model is a conditional generator framework, which entails a bio molecular profile VAE (PVAE) and a sequential compound generator VAE (SVAE), an RL optimization framework, Tanimoto similarity model, and a multimodal IC50 prediction model (PaccMann). 

   This research significantly relates to the overall mission of Emergent Dynamics, Inc., as it develops efficacy curative solutions through deep generative models for Biomedicine. An optimized generative model can design effective drugs closely following cell tissue adaptive sequences and bioactive small molecular structural patterns. The research demonstrates the development of an effective anticancer drug design model through reinforcement learning.
