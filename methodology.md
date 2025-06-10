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

After having identified the entity we wanted to take into account, we decided to execute a first general query to find anything that was labelled as “Bridgerton” in DBpedia. So we asked two LLMs (ChatGPT and Gemini),to produce a query following the example included in the guidelines presentation, involving few-shot prompting.
These were the results:
  
<p><strong> ChatGPT:</strong></p>

  <img src="https://i.imgur.com/5HuAiJ2.png" alt="SPARQL Query from ChatGPT" width="600"/>
  <img src="https://i.imgur.com/bJbrr2S.png" alt="SPARQL Query from ChatGPT" width="600"/> 

<p><strong> Gemini:</strong></p>

  <img src="https://i.imgur.com/COdnf85.png" alt="SPARQL Query from Gemini" width="600"/>
  <img src="https://i.imgur.com/gbjfinA.png" alt="SPARQL Query from Gemini" width="600"/> 

Both LLMs gave us the same outcome, to which we added LIMIT 100 to have a reasonable outcome.Then
we executed the query and we obtained a series of results, between which we individuated the knowledge graph we wanted to amplify (n. 30), traceable with the IRI: [https://dbpedia.org/page/Bridgerton](https://dbpedia.org/page/Bridgerton) . 










</details>


<details>
  <summary>🧪 2. General Methodology</summary>

</details>

<details>
  <summary>🛠️ 3. Tools</summary>

</details>


