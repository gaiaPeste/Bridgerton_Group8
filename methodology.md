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
After having identified the entity we wanted to take into account, we decided to execute a first general query to find anything that was labelled as “Bridgerton” in DBpedia,  https://www.dbpedia.org/resources/ontology/. So we asked two LLMs (ChatGPT and Gemini),to produce a query following the example included in the guidelines presentation, involving few-shot prompting.
These were the results:
  
  ChatGPT

![QUERY 1](https://i.imgur.com/5HuAiJ2.png)
![QUERY 1](https://i.imgur.com/bJbrr2S.png)

GEMINI

![QUERY 1](https://i.imgur.com/COdnf85.png)
![QUERY 1](https://i.imgur.com/gbjfinA.png)

Both LLMs gave us the same outcome, to which we added LIMIT 100 to have a reasonable outcome.Then
we executed the query and we obtained a series of results, between which we individuated the knowledge graph we wanted to amplify (n. 30), traceable with the IRI: https://dbpedia.org/page/Bridgerton . 

![QUERY 1](https://i.imgur.com/DvKTVa6.png)
![QUERY 1](https://i.imgur.com/uZhTrn5.png) 

This knowledge graph classifies “Bridgerton” as an entity of type: Television show. From there we decided to execute other two very general queries to individuate the classes and properties already related to the dbr:Bridgerton, so to have a general idea of what we were working with.

CLASSES:

ChatGPT

![QUERY CLASSES](https://i.imgur.com/w4K1yda.png)
![QUERY CLASSES](https://i.imgur.com/LfOL1kx.png)
![QUERY CLASSES](https://i.imgur.com/p7AeWJL.png)
![QUERY CLASSES](https://i.imgur.com/UnvBert.png)

GEMINI

![QUERY CLASSES](https://i.imgur.com/vtzqTXf.png)
![QUERY CLASSES](https://i.imgur.com/G1YYySy.png)
![QUERY CLASSES](https://i.imgur.com/xeTaNzB.png)
![QUERY CLASSES](https://i.imgur.com/i3aFYYb.png)

PROPERTIES:

ChatGPT

![QUERY PROPERTIES](https://i.imgur.com/Hb7AOxG.png)
![QUERY PROPERTIES](https://i.imgur.com/4hqSvps.png)
![QUERY PROPERTIES](https://i.imgur.com/mVfqVtJ.png)
![QUERY PROPERTIES](https://i.imgur.com/MUtNcKs.png)

GEMINI

![QUERY PROPERTIES](https://i.imgur.com/IkmaZAt.png)
![QUERY PROPERTIES](https://i.imgur.com/IeNxMBK.png)
![QUERY PROPERTIES](https://i.imgur.com/3Mt0g2I.png)
![QUERY PROPERTIES](https://i.imgur.com/JWiPxa0.png)

The two LLMs gave the same result, but Gemini added and ORDER BY to range the results in alphabetical order.

After having explored the vocabulary related to our knowledge graph, we decided to have a look at it and we noticed instantly that some information was **wrong** and needed to be **modified**
that some classes and properties needed to be **integrated** and that some information could be **added integrally**. So we developed a general methodology to address all this instances. 


</details>


<details>
  <summary>🧪 2. General Methodology</summary>

</details>

<details>
  <summary>🛠️ 3. Tools**</summary>

</details>


