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


</details>



<details>
  <summary>🧪 2. General Methodology</summary>

</details>

<details>
  <summary>🛠️ 3. Tools</summary>

</details>


<p align="center">
  <img src="https://www.indiewire.com/wp-content/uploads/2024/05/BRIDGERTON_304_Unit_02860R.jpg?w=600&h=337&crop=1" alt="SPARQL Query" width="600"/>
</p>
