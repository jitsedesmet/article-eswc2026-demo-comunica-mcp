## Demonstration
{:#demonstration}

This demonstration shows the functionalities and current limitations of Comunica MCP SPARQL,
to trigger discussions for future work.
Concretely, we will run Comunica MCP SPARQL locally, and connect different LLM-based AI chatbots with it.
Through various prompts, participants can see answer accuracy improve.

<figure id="claude-example">
<img src="img/claude.png" alt="[An example of using Comunica MCP SPARQL in Claude]">
<figcaption markdown="block">
Get all movies Brad Pitt and Leonardo DiCaprio both play in with Claude.
</figcaption>
</figure>

For example, when using Claude to ask *"What movies do both Brad Pitt and Leonardo DiCaprio both play in?"*,
only a single answer is produced; namely _"Once Upon a Time in Hollywood"_.
However, when asking *"Use Comunica SPARQL to determine what movies both Brad Pitt and Leonardo DiCaprio both play in."* (see [](#claude-example)),
we receive a more accurate answer; *"Once Upon a Time in Hollywood and The Audition"*.
This is because internally, this second question leads to a SPARQL query over DBpedia,
which causes a more complete answer to be produced.
When connected to a Solid pod,
prompts such as *"Using Comunica SPARQL Solid, can you show me information about myself based on my profile?"* can be answered.

Comunica MCP still requires a dedicated MCP server, which contradicts Comunica's goal to enable pure client-side execution.
To address this limitation, we will also demonstrate a prototype of Comunica MCP that uses [WebMCP](cite:cites webmcp)
to expose MCP capabilities through the Web browser via [https://query.comunica.dev/](https://query.comunica.dev/).
