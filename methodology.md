<div id="menu" style="position:fixed;top:0;left:0;width:100%;background:#f8f8f8;border-bottom:1px solid #ddd;padding:5px 0;z-index:1000;text-align:center;">
  <a href="index.html" style="margin:0 15px;color:#0366d6;font-weight:bold;">Home</a>
  <a href="topic-description.html" style="margin:0 15px;color:#0366d6;font-weight:bold;">Topic Description</a>
  <a href="methodology.html" style="margin:0 15px;color:#0366d6;font-weight:bold;">Gap, Methodology and Tools</a>
  <a href="steps.html" style="margin:0 15px;color:#0366d6;font-weight:bold;">Methodological Steps</a>
  <a href="challenges.html" style="margin:0 15px;color:#0366d6;font-weight:bold;">Challenges & LLMs Differences</a>
</div>

<br>
# Gap, Methodology & Tools
<details>
  <summary>🔍 1. How the Gap Was Identified</summary>

After having identified the entity we wanted to take into account, we decided to execute a first general query to find anything that was labelled as "Bridgerton" in <a href="https://wiki.dbpedia.org/services-resources/ontology">DBpedia Ontology</a>. So we asked two LLMs,  <a href="https://chat.openai.com/" target="_blank" rel="noopener noreferrer">ChatGPT</a> and <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini</a>,to produce a query following the example included in the guidelines presentation, involving few-shot prompting.
These were the results:
  
<p><strong> ChatGPT:</strong></p>

  <img src="https://i.imgur.com/5HuAiJ2.png" alt="SPARQL Query from ChatGPT" width="600"/>
  <img src="https://i.imgur.com/bJbrr2S.png" alt="SPARQL Query from ChatGPT" width="600"/> 

<p><strong> Gemini:</strong></p>

  <img src="https://i.imgur.com/COdnf85.png" alt="SPARQL Query from Gemini" width="600"/>
  <img src="https://i.imgur.com/gbjfinA.png" alt="SPARQL Query from Gemini" width="600"/> 

Both LLMs gave us the same outcome, to which we added LIMIT 100 to have a reasonable outcome.Then
we executed the query and we obtained a series of results, between which we individuated the knowledge graph we wanted to amplify (n. 30), traceable with the IRI <a href="https://dbpedia.org/page/Bridgerton" target="_blank" rel="noopener noreferrer">https://dbpedia.org/page/Bridgerton</a>.

<img src="https://i.imgur.com/DvKTVa6.png" alt="Yasgui" width="600"/> 
<img src="https://i.imgur.com/uZhTrn5.png" alt="Yasgui" width="600"/> 

This knowledge graph classifies “Bridgerton” as an entity of type: Television show. From there we decided to execute other two very general queries to individuate the classes and properties already related to the <a href="https://dbpedia.org/page/Bridgerton" target="_blank" rel="noopener noreferrer">dbr:Bridgerton</a>
, so to have a general idea of what we were working 

<p><strong>CLASSES:</strong></p> 
<p><strong> ChatGPT:</strong></p>
<img src="https://i.imgur.com/w4K1yda.png" alt="SPARQL Query from ChatGPT" width="600"/>
<img src="https://i.imgur.com/LfOL1kx.png" alt="SPARQL Query from ChatGPT" width="600"/>
<img src="https://i.imgur.com/p7AeWJL.png" alt="Yasgui from ChatGPT" width="600"/>
<img src="https://i.imgur.com/UnvBert.png" alt=" Yasgui from ChatGPT" width="600"/>

<p><strong>Gemini:</strong></p>
<img src="https://i.imgur.com/vtzqTXf.png" alt="SPARQL Query from Gemini" width="600"/>
<img src="https://i.imgur.com/G1YYySy.png" alt="SPARQL Query from Gemini" width="600"/>
<img src="https://i.imgur.com/xeTaNzB.png" alt="Yasgui from Gemini" width="600"/>
<img src="https://i.imgur.com/i3aFYYb.png" alt="Yasgui from Gemini" width="600"/>

<p><strong>PROPERTIES:</strong></p>
<p><strong>ChatGPT:</strong></p>
<img src="https://i.imgur.com/Hb7AOxG.png" alt="SPARQL Query from ChatGPT" width="600"/>
<img src="https://i.imgur.com/4hqSvps.png" alt="SPARQL Query from ChatGPT" width="600"/>
<img src="https://i.imgur.com/mVfqVtJ.png" alt="Yasgui from ChatGPT" width="600"/>
<img src="https://i.imgur.com/MUtNcKs.png" alt="Yasgui from ChatGPT" width="600"/>

<p><strong>Gemini:</strong></p>
<img src="https://i.imgur.com/IkmaZAt.png" alt="SPARQL Query from Gemini" width="600"/>
<img src="https://i.imgur.com/IeNxMBK.png" alt="SPARQL Query from Gemini" width="600"/>
<img src="https://i.imgur.com/3Mt0g2I.png" alt="Yasgui from Gemini" width="600"/>
<img src="https://i.imgur.com/JWiPxa0.png" alt="Yasgui from Gemini" width="600"/>

The two LLMs gave the same result, but Gemini added and ORDER BY to range the results in alphabetical order.

After having explored the vocabulary related to our knowledge graph, we decided to have a look at it and we noticed instantly that some information was <strong>wrong</strong> and needed to be <strong>modified</strong> that some classes and properties needed to be <strong>integrated</strong> and that some information could be <strong>added integrally</strong>. So we developed a general methodology to address all this instances. 
<br><br>


</details>



<details>
  <summary>🧪 2. General Methodology</summary>
  In this project, we explored and enriched a knowledge graph (KG) about the TV series Bridgerton by combining SPARQL querying techniques with the assistance of large language models (LLMs), specifically <a href="https://chat.openai.com/" target="_blank" rel="noopener noreferrer">ChatGPT (Open AI)</a> and <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini (Google)</a>
Our goal was to model and assess whether certain concepts (e.g., general information and knowledge about themes and the soundtrack) are represented in the graph, and where necessary, propose new triples.
<br> 
After having identified the gap, we studied the DBpedia ontology to identify how concepts like themes, subjects, and categories are currently modeled. We explored the ontologies and identified the concepts (classes and properties) to build queries.
Then we used the LLMs (<a href="https://chat.openai.com/" target="_blank" rel="noopener noreferrer">ChatGPT (Open AI)</a> and <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini (Google)</a>) as information retrieval/question answering tools to find relevant knowledge to enrich the KG. 
After having identified the areas that we wanted to explore more in depth, we wrote several SPARQL queries targeting the DBpedia resource for Bridgerton. 
In doing so, we applied multiple SPARQL keywords to extract or validate thematic information:
<ul>
•	FILTER + REGEX to detect the presence of specific keywords in abstracts</ul>
  <ul>
•	OPTIONAL to be able to have queries that allow information to be added to the solution where the information is available, but do not reject the solution because some part of the query pattern does not match </ul>
  <ul>
•	DISTINCT and LIMIT to refine and control results</ul>
  <ul>
•	ORDER BY to sort output (used in debugging and display queries)</ul>
  <ul>
•	UNION to combine multiple theme patterns in a single query (e.g., "desire" OR "struggle").</ul>
</ul>
<br>
When existing links were missing or were incorrect, we proposed new conceptual connections using RDF triples. We designed custom RDF triples using SPARQL CONSTRUCT queries to represent new knowledge. So we used <a href="https://chat.openai.com/" target="_blank" rel="noopener noreferrer">ChatGPT (Open AI)</a> and <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini (Google)</a> to generate these triples, model their structure, and validate whether the vocabulary aligned with <a href="https://www.dbpedia.org/" target="_blank" rel="noopener noreferrer">DBpedia</a>. We also explored how LLMs can help when formal vocabulary is lacking.
We used three prompting strategies:
<ul>
-	Zero-shot: Direct requests (“Can you give me a complete and detailed list of the themes in the Bridgerton TV series?”)
-	Few-shot: Providing examples like the personal desire and the emotional struggles triples before asking for a new one on taboos.
-	Chain-of-thought: Asking the LLM to think step-by-step before generating a triple (e.g., “Think step-by-step how to model a triple connecting Bridgerton to the concept of emotional struggle”).
</ul>
<br>

  We critically evaluated LLM outputs by checking query correctness using a SPARQL endpoint (e.g. <a href="https://dbpedia.org/sparql" target="_blank" rel="noopener noreferrer">DBpedia SPARQL interface</a>, <a href="https://yasgui.org/" target="_blank" rel="noopener noreferrer">Yasgui</a>
). We noticed that both LLMs had strong understanding of RDF, RDFS, OWL, SPARQL, and semantic modeling practices. They are familiar with Linked Data vocabularies (e.g., DBpedia, FOAF, etc.) and understand how to model new triples or propose schema extensions using correct RDF syntax. 
<br>

This project demonstrated how SPARQL and LLMs can work in synergy to enrich and interrogate a cultural knowledge graph. From querying existing data to proposing new semantic connections, we applied best practices in prompt engineering, ontology alignment, and RDF modeling, all while evaluating the reliability and expressiveness of different language models.
<br><br>
</details>

<details>
  <summary>🛠️ 3. Tools</summary>
  1.	LLMs: 	<strong><a href="https://chat.openai.com/" target="_blank" rel="noopener noreferrer">ChatGPT (Open AI)</a></strong>  and  <strong><a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini (Google)</a></strong>: 
-	Purpose: Used as a language model assistant for generating SPARQL queries, proposing RDF triples, modeling ontological relationships, and supporting prompt engineering.
-	Strengths: Strong performance in structured reasoning, syntax generation, and adherence to ontological standards when prompted effectively.
-	Use Cases:
o	Creating SPARQL queries (SELECT, CONSTRUCT).
o	Rewriting prompts using few-shot or chain-of-thought methods.
o	Evaluating and refining RDF vocabulary usage.

</details>


<p align="center">
  <img src="https://www.indiewire.com/wp-content/uploads/2024/05/BRIDGERTON_304_Unit_02860R.jpg?w=600&h=337&crop=1" alt="SPARQL Query" width="600"/>
</p>
