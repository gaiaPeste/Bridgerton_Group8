<div id="menu" style="position:fixed;top:0;left:0;width:100%;background:#f8f8f8;border-bottom:1px solid #ddd;padding:5px 0;z-index:1000;text-align:center;">
  <a href="index.html" style="margin:0 15px;color:#800080;font-weight:bold;">Home</a>
  <a href="topic-description.html" style="margin:0 15px;color:#800080;font-weight:bold;">Topic Description</a>
  <a href="methodology.html" style="margin:0 15px;color:#800080;font-weight:bold;">Gap, Methodology and Tools</a>
  <a href="steps.html" style="margin:0 15px;color:#800080;font-weight:bold;">Methodological Steps</a>
  <a href="challenges.html" style="margin:0 15px;color:#800080;font-weight:bold;">Challenges & LLMs Differences</a>
</div>

<p align="center">
  <img src="https://www.indiewire.com/wp-content/uploads/2024/05/BRIDGERTON_304_Unit_02860R.jpg?w=600&h=337&crop=1" alt="SPARQL Query" width="600"/>
</p>

<br>
# Gap, Methodology & Tools
<details>
  <summary>🔍 <strong>1. How the Gap Was Identified</strong></summary>
  <br><br>
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
, so to have a general idea of what we were working with.

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

After having explored the vocabulary related to our knowledge graph, <a href="https://dbpedia.org/resource/Bridgerton" target="_blank" rel="noopener noreferrer"><em>dbr:Bridgerton</em></a>, we decided to examine it more closely and we noticed instantly that some information was <strong>wrong</strong> and needed to be <strong>modified</strong> that some classes and properties needed to be <strong>integrated</strong> and that some information could be <strong>added integrally</strong>. So we developed a general methodology to address all this instances. 
<br><br>


</details>



<details>
  <summary>🧪 <strong>2. General Methodology</strong></summary>
  <br><br>
  After having identified the gaps, we used the LLMs (<a href="https://chat.openai.com/" target="_blank" rel="noopener noreferrer">ChatGP</a> and <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini</a>) as information retrieval/question answering tools to find relevant knowledge to enrich the KG. <br>
Subsequently, after having identified the areas that we wanted to explore more in depth, we wrote several <strong>SPARQL queries</strong> targeting <a href="https://dbpedia.org/resource/Bridgerton" target="_blank" rel="noopener noreferrer"><em>dbr:Bridgerton</em></a> assisted by LLMs. 
In doing so, we applied multiple SPARQL keywords to extract or validate thematic information:
<ul>
•	<strong>FILTER + REGEX</strong> to detect the presence of specific keywords in abstracts</ul>
  <ul>
•	<strong>OPTIONAL</strong> to be able to have queries that allow information to be added to the solution where the information is available, but do not reject the solution because some part of the query pattern does not match </ul>
  <ul>
•	<strong>DISTINCT</strong> and <strong>LIMIT</strong> to refine and control results</ul>
  <ul>
• <strong>ORDER BY</strong> to sort output (used in debugging and display queries)</ul>
  <ul>
•	<strong>UNION</strong>to combine multiple theme patterns in a single query (e.g., "desire" OR "struggle").</ul>

<br>
When existing links were missing, incorrect or needed to be amplified, we proposed new conceptual connections using RDF triples. We designed custom RDF triples using SPARQL <strong>CONSTRUCT</strong> queries to represent new knowledge. So we used <a href="https://chat.openai.com/" target="_blank" rel="noopener noreferrer">ChatGPT (Open AI)</a> and <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini (Google)</a> to generate these triples, model their structure, and validate whether the vocabulary aligned with <a href="https://www.dbpedia.org/" target="_blank" rel="noopener noreferrer">DBpedia</a>. We also explored how LLMs can help when formal vocabulary is lacking.
We used three prompting strategies:
<ul>
-	<strong>Zero-shot</strong>: Direct requests (“Can you give me a complete and detailed list of the themes in the Bridgerton TV series?”)</ul>
<ul>
-	<strong>Few-shot</strong>: Providing examples like the personal desire and the emotional struggles triples before asking for a new one on taboos.</ul>
<ul>
-	<strong>Chain-of-thought</strong>: Asking the LLM to think step-by-step before generating a triple (e.g., “Think step-by-step how to model a triple connecting Bridgerton to the concept of emotional struggle”).</ul>

<br>

  We critically evaluated LLM outputs by checking <strong>query correctness</strong>  using a SPARQL endpoint (e.g.<a href="https://yasgui.org/" target="_blank" rel="noopener noreferrer">Yasgui</a>). <br>
  We noticed that both LLMs had strong understanding of <strong> RDF, RDFS, OWL, SPARQL</strong>, and semantic modeling practices. They are familiar with <strong>Linked Data vocabularies</strong> (e.g., DBpedia, FOAF, etc.) and understand how to <strong>model new triples</strong> or propose schema extensions using correct RDF syntax. <br>
When given examples they corrected and trained themselves to give the following tasks in the already corrected form. The same thing happened when they were asked to think step by step. While at first, they gave more concise and direct answers, after asking them to do chain-of-thought they repeated this process also in the following tasks. <br>
They both remembered and chained context, which helped when we asked questions like: "Now create a triple for 'taboos' like you did for 'emotional struggles'". They can track previous ontology examples and maintain vocabulary consistency. <br>
This project demonstrated how SPARQL and LLMs can work in synergy to enrich and interrogate a cultural knowledge graph. From querying existing data to proposing new semantic connections, we applied best practices in <strong>prompt engineering, ontology alignment</strong>, and <strong>RDF modeling</strong>, all while evaluating the reliability and expressiveness of different language models.
<br><br>
</details>

<details>
  <summary>🛠️ <strong>3. Tools</strong></summary>
  <br><br>
  <ol>
  1.	LLMs: 	<strong><a href="https://chat.openai.com/" target="_blank" rel="noopener noreferrer">ChatGPT (Open AI)</a></strong>  and  <strong><a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini (Google)</a></strong>: 
    <ul>
-	Purpose: Used as a language model assistant for generating SPARQL queries, proposing RDF triples, modeling ontological relationships, and supporting prompt engineering.</ul>
     <ul>
-	Strengths: Strong performance in structured reasoning, syntax generation, and adherence to ontological standards when prompted effectively.</ul>
     <ul>
-	Use Cases:</ul>
    <ul>
o	Creating SPARQL queries (SELECT, CONSTRUCT).</ul>
     <ul>
o	Rewriting prompts using few-shot or chain-of-thought methods.</ul>
     <ul>
o	Evaluating and refining RDF vocabulary usage. </ul>
  </ol>
  <ol>
  2.	<strong><a href="https://yasgui.org/" target="_blank" rel="noopener noreferrer">YASGUI</a></strong>
    <ul>
•	Purpose: A web-based SPARQL query interface used to write, test, and run SPARQL queries on DBpedia and other endpoints.</ul>
     <ul>
•	Benefits:</ul>
     <ul>
o	Syntax highlighting and prefix auto-completion.</ul>
     <ul>
o	Easy visualization of results.</ul>
     <ul>
o	Support for custom SPARQL endpoints.</ul>
  </ol>
  <ol>
  3.	<strong><a href="https://prefix.cc/" target="_blank" rel="noopener noreferrer">Prefix.cc</a></strong>
    <ul>
•	Purpose: A lookup service for common RDF and SPARQL prefixes.</ul>
    <ul>
•	Use in Project:</ul>
    <ul>
o	Quickly finding standard prefixes (e.g., dbo, rdfs, foaf) to ensure correct namespace usage in queries.</ul>
    <ul>
o	Ensuring vocabulary alignment and avoiding errors in prefix declaration.</ul>
</ol> 
<ol>
4.	<strong><a href="https://github.com" target="_blank" rel="noopener noreferrer">GitHub</a></strong> <br>
GitHub is a web-based platform for version control and collaboration. It lets developers store and manage code using Git, track changes, and work together on software projects.
</ol>
<br><br>







