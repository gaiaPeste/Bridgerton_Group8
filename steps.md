<div id="menu" style="position:fixed;top:0;left:0;width:100%;background:#f8f8f8;border-bottom:1px solid #ddd;padding:5px 0;z-index:1000;text-align:center;">
  <a href="index.html" style="margin:0 15px;color:#0366d6;font-weight:bold;">Home</a>
  <a href="topic-description.html" style="margin:0 15px;color:#0366d6;font-weight:bold;">Topic Description</a>
  <a href="methodology.html" style="margin:0 15px;color:#0366d6;font-weight:bold;">Gap, Methodology and Tools</a>
  <a href="steps.html" style="margin:0 15px;color:#0366d6;font-weight:bold;">Methodological Steps</a>
  <a href="challenges.html" style="margin:0 15px;color:#0366d6;font-weight:bold;">Challenges & LLMs Differences</a>
</div>
<p align="center">
  <img src="https://ichef.bbci.co.uk/ace/ws/640/cpsprodpb/1781D/production/_116158269_bridgerton_108_unit_02448r.jpg.webp" alt="Bridgerton" style="display: block; margin: auto; max-width: 100%; height: auto;">
</p>

<br>

# Methodological Steps
<details>
  <summary><strong>First steps: update and integration</strong> (click to expand)</summary>
 <details>
    <summary><strong>Update: Episodes and Seasons </strong>(click to expand)</summary>

These initial queries have the aim to correct information related to the <em>dbo:numberOfSeasons</em> and <em>dbo:numberOfEpisodes</em>. In  both cases the values are wrong: the number of seasons should be 3, but it is represented as <em>xsd:2</em>, and the number of episodes should be 24, but it is represented as <em>xsd:16</em>. 
<br>
Furthermore both <em>dbo:numberOfSeasons</em> and <em>dbo:numberOfEpisodes</em> are associated with related DBpedia properties, <em>dbps: dbp:numSeasons and dbp:numEpisodes</em>, which are also incorrect. The procedure adopted to solve this issue is the same for both situations. 
<br>
First, the correction of the number of episodes will be presented, showing the results provided by both <a href="https://chat.openai.com/" target="_blank" rel="noopener noreferrer">ChatGPT</a> and <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini</a>. Then the situation about the number of seasons will be addressed.
<ol>
  1) First of all the actual <em>dbo:numberOfEpisodes</em> value was checked through an initial query. A zero-shot prompt was proposed to both LLMs as follows. Here are the results:
  <img src="https://i.imgur.com/XcxtieO.png" alt="SPARQL Query Episodes" width="600"/>
  ChatGPT:
  <img src="https://i.imgur.com/sbnODQ6.png" alt="SPARQL Query Episodes" width="600"/> 
  <img src="https://i.imgur.com/V4PQq1a.png" alt="Yasgui Episodes" width="600"/> 
 Gemini:
  <img src="https://i.imgur.com/tXEYWrI.png" alt="SPARQL Query Episodes" width="600"/> 
  <img src="https://i.imgur.com/jiBuE5t.png" alt="Yasgui Episodes" width="600"/> 
</ol>
<ol>
  2) The wrong value was immediately corrected through the construction of new RDFs triples, obtained through chain-of-thought prompting:
   <img src="https://i.imgur.com/6GDhFcT.png" alt="SPARQL Query Episodes" width="600"/> 
  ChatGPT:
   <img src="https://i.imgur.com/EXmMcby.png" alt="SPARQL Query Episodes" width="600"/> 
   <img src="https://i.imgur.com/RuZhaMt.png" alt="SPARQL Query Episodes" width="600"/> 
   <img src="https://i.imgur.com/5ff3MuV.png" alt="SPARQL Query Episodes" width="600"/> 
  Gemini:
   <img src="https://i.imgur.com/lXm4sZT.png" alt="SPARQL Query Episodes" width="600"/> 
   <img src="https://i.imgur.com/CiKbkFL.png" alt="SPARQL Query Episodes" width="600"/> 
   </ol>
<ol>
  3) Then, the <em>dbo:numberOfEpisodes</em> and <em>dbp:numEpisodes</em> were compared through another query:
  <img src="https://i.imgur.com/tvugGKz.png" alt="SPARQL Query Episodes" width="600"/> 
  ChatGPT:
  <img src="https://i.imgur.com/LDrh5si.png" alt="SPARQL Query Episodes" width="600"/> 
  <img src="https://i.imgur.com/U0ZoxnZ.png" alt="SPARQL Query Episodes" width="600"/>
   Gemini
   <img src="https://i.imgur.com/8uqzUln.png" alt="SPARQL Query Episodes" width="600"/>
   <img src="https://i.imgur.com/G7tDGwZ.png" alt="SPARQL Query Episodes" width="600"/>
  </ol>
  <ol>
    4)	Finally also the dbp:numEpisodes was corrected: <br>
    ChatGPT (with a zero-shot prompt): 
    <img src="https://i.imgur.com/dpOnemL.png" alt="SPARQL Query Episodes" width="600"/>
    <img src="https://i.imgur.com/CNnc1QR.png" alt="SPARQL Query Episodes" width="600"/>
    Gemini (with a chain-of-thought prompt):
    <img src="https://i.imgur.com/Oaht2Ir.png" alt="SPARQL Query Episodes" width="600"/>
    <img src="https://i.imgur.com/YmpnuqS.png" alt="SPARQL Query Episodes" width="600"/>
    <img src="https://i.imgur.com/6kHNrWE.png" alt="SPARQL Query Episodes" width="600"/>
    <img src="https://i.imgur.com/KeJ8yyJ.png" alt="SPARQL Query Episodes" width="600"/>
 </ol>
 BONUS: in the knowledge graph there was also another dbp related to episodes, which was wrong too. So also the <em>dbp:episodes</em> was corrected as follows, with few-shot prompting.
  <img src="https://i.imgur.com/pgxOfS0.png" alt="SPARQL Query Episodes" width="600"/>
  ChatGPT:
  <img src="https://i.imgur.com/Nyx4aks.png" alt="SPARQL Query Episodes" width="600"/>
  <img src="https://i.imgur.com/8BRHy2r.png" alt="SPARQL Query Episodes" width="600"/>
  <img src="https://i.imgur.com/Ck3IfEM.png" alt="SPARQL Query Episodes" width="600"/>
  Gemini:
  <img src="https://i.imgur.com/IRLtuSF.png" alt="SPARQL Query Episodes" width="600"/>
  <img src="https://i.imgur.com/poYaZ8k.png" alt="SPARQL Query Episodes" width="600"/>
  <img src="https://i.imgur.com/OTgOXat.png" alt="SPARQL Query Episodes" width="600"/>
  <img src="https://i.imgur.com/sXZq5Id.png" alt="SPARQL Query Episodes" width="600"/>
  </details>
  
   <details>
    <summary><strong>Integration: Starring, Caption and Start</strong> (click to expand)</summary>

    Contenuto della sottosezione 2.

  </details>

</details>


<br><br>

 
  
 
