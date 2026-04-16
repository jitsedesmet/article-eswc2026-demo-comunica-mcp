## Abstract
<!-- Context      -->
Despite the growing popularity of AI agents based on Large Language Models (LLMs),
they often hallucinate parts of their answers,
which limits their trustworthiness.
Techniques such as GraphRAG have already been introduced
to improve the overall accuracy of LLMs by combining them with Knowledge Graphs.
In contrast to GraphRAG, the recently introduced Model Context Protocol (MCP)
allows LLMs to be connected to external systems without prior training.
Since we do not have a good understanding yet of how MCP can help connecting LLMs to Knowledge Graphs,
<!-- Need         -->
there is a need for flexible software that offers Knowledge Graphs through an MCP interface.
<!-- Task         -->
The goal of this demonstration is to introduce the Comunica MCP SPARQL servers,
<!-- Object       -->
which exposes all public or private Knowledge Graphs through a SPARQL-based MCP interface.
<!-- Findings     -->
Our preliminary findings show that modern LLMs can effectively query over well known Knowledge Graphs such as DBpedia and Wikidata,
but can struggle when querying other Knowledge Graphs,
or try to write federated queries.
<!-- Conclusion   -->
In conclusion, Comunica MCP SPARQL is a tool that offers a path towards trustworthy and explainable agentic AI,
<!-- Perspectives -->
and enables future research towards neuro-symbolic AI by integrating LLMs and Knowledge Graphs.

