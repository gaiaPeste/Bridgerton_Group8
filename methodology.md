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

After having identified the entity we wanted to take into account, we decided to execute a first general query to find anything that was labelled as “Bridgerton” in [DBpedia](https://www.dbpedia.org/resources/ontology/). So we asked two LLMs ([ChatGPT ](https://chatgpt.com/)and [Gemini](https://gemini.google.com/?hl=it)),to produce a query following the example included in the guidelines presentation, involving few-shot prompting.
These were the results:
  
<p><strong> ChatGPT:</strong></p>

  <img src="https://i.imgur.com/5HuAiJ2.png" alt="SPARQL Query from ChatGPT" width="600"/>
  <img src="https://i.imgur.com/bJbrr2S.png" alt="SPARQL Query from ChatGPT" width="600"/> 

<p><strong> Gemini:</strong></p>

  <img src="https://i.imgur.com/COdnf85.png" alt="SPARQL Query from Gemini" width="600"/>
  <img src="https://i.imgur.com/gbjfinA.png" alt="SPARQL Query from Gemini" width="600"/> 

Both LLMs gave us the same outcome, to which we added LIMIT 100 to have a reasonable outcome.Then
we executed the query and we obtained a series of results, between which we individuated the knowledge graph we wanted to amplify (n. 30), traceable with the IRI: [https://dbpedia.org/page/Bridgerton](https://dbpedia.org/page/Bridgerton).

<img src="https://i.imgur.com/DvKTVa6.png" alt="Yasgui" width="600"/> 
<img src="https://i.imgur.com/uZhTrn5.png" alt="Yasgui" width="600"/> 

This knowledge graph classifies “Bridgerton” as an entity of type: Television show. From there we decided to execute other two very general queries to individuate the classes and properties already related to the dbr:Bridgerton, so to have a general idea of what we were working 

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

After having explored the vocabulary related to our knowledge graph, we decided to have a look at it and we noticed instantly that some information was **wrong** and needed to be **modified**
that some classes and properties needed to be **integrated** and that some information could be **added integrally**. So we developed a general methodology to address all this instances. 

</details>


<details>
  <summary>🧪 2. General Methodology</summary>

</details>

<details>
  <summary>🛠️ 3. Tools</summary>

</details>


![Bridgerton](data:image/jpeg;base64,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)
