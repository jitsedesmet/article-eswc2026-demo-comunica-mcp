## Implementation
{:#implementation}

Comunica MCP SPARQL is a TypeScript/JavaScript project that exposes all functionalities of the [Comunica SPARQL querying framework](cite:cites comunica) through MCP.
It is open-source, available on [GitHub](https://github.com/comunica/comunica-feature-mcp/){:.mandatory}, npm, and is available under the MIT license.
Comunica is a modular SPARQL framwork that enables SPARQL querying over decentralized Knowledge Graphs.
This includes Knowledge Graphs exposed as [SPARQL endpoints](cite:cites spec:sparqlprot),
[Linked Data documents](cite:cites linkeddata) in any RDF representation, [TPF interfaces](cite:cites tpf), [HDT files](cite:cites hdt), [Solid pods](cite:cites solid), and more.
In contrast to GRASP, Comunica MCP SPARQL is exposed through the more flexible MCP instead of using direct function calling.
MCP is very simple to setup, as it only requires a minimal configuration change within LLM agents, as can be seen in [](#mcp-config).
Furthermore, besides allowing the LLM agent to execute any possible SPARQL 1.2 query,
Comunica MCP SPARQL allows agents to provide one or more Knowledge Graph URLs to query over.
And if the AI agent does not know what URLs to start from,
[link traversal](cite:cites linktraversalfoundations,solidquery) can be used to discover relevant sources by following links.

<figure id="mcp-config" class="listing">
````/code/mcp-config.txt````
<figcaption markdown="block">
An example of the only configuration change needed to configure Comunica MCP SPARQL within tools such as Claude or Copilot.
</figcaption>
</figure>

Comunica MCP SPARQL is not the first MCP approach for SPARQL, but it has some notable differences to existing work.
Some SPARQL engine vendors have their own dedicated MCP servers, such as
[Jena](https://github.com/ramuzes/mcp-jena){:.mandatory},
[GraphDB](https://github.com/keonchennl/mcp-graphdb){:.mandatory},
and [Stardog](https://github.com/noahgorstein/mcp-server-stardog){:.mandatory}.
These MCP servers are tied to these systems, while Comunica MCP SPARQL works with any Knowledge Graph.
[RDF Explorer](https://github.com/emekaokoye/mcp-rdf-explorer){:.mandatory} and [SPARQL-MCP](cite:cites sparqlmcp) are not tied to specific Knowledge Graphs,
but in contrast to Comunica MCP SPARQL,
they only handle Knowledge Graphs exposed through SPARQL endpoints.
Among these two, SPARQL-MCP is the only one that also supports federation,
but in contrast to Comunica MCP SPARQL,
it requires the LLM agent to explicitly include `SERVICE` keywords within the query,
while Comunica enables automatic source selection.
Furthermore, all advanced features from Comunica are exposed through MCP,
such as HTTP proxy support, timeout settings, and authentication (e.g for updates).

Below, we list the tools that Comunica MCP SPARQL exposes to LLMs,
together with their LLM-directed descriptions and (a subset of) the available parameters:

- `query-sparql`: Execute SPARQL queries over one or more remote sources, which also includes update queries.
    - `query` (required): SPARQL query string.
    - `sources` (required): List of SPARQL endpoint URLs, TPF interface URLs, or Lin
    - `httpProxy` (optional): HTTP proxy URL (e.g., http://proxy.example.com:8080).
    - `httpAuth` (optional): HTTP basic authentication in the format username:password.
- `query-sparql-rdf`: Execute SPARQL queries over a serialized RDF dataset provided as a string.
    - `query` (required): SPARQL query string.
    - `value` (required): Serialized RDF dataset as a string.
    - `mediaType` (required): Media type of the serialized RDF dataset.
