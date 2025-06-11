<div id="menu" style="position:fixed;top:0;left:0;width:100%;background:#f8f8f8;border-bottom:1px solid #ddd;padding:5px 0;z-index:1000;text-align:center;">
  <a href="index.html" style="margin:0 15px;color:#800080;font-weight:bold;">Home</a>
  <a href="topic-description.html" style="margin:0 15px;color:#800080;font-weight:bold;">Topic Description</a>
  <a href="methodology.html" style="margin:0 15px;color:#800080;font-weight:bold;">Gap, Methodology and Tools</a>
  <a href="steps.html" style="margin:0 15px;color:#800080;font-weight:bold;">Methodological Steps</a>
  <a href="challenges.html" style="margin:0 15px;color:#800080;font-weight:bold;">Challenges & LLMs Differences</a>
</div>
<p align="center">
  <img src="https://ichef.bbci.co.uk/ace/ws/640/cpsprodpb/1781D/production/_116158269_bridgerton_108_unit_02448r.jpg.webp" alt="Bridgerton" style="display: block; margin: auto; max-width: 100%; height: auto;">
</p>

<br>

# Methodological Steps

<details>
  <summary style="color:purple"><strong>First steps: update and integration</strong> (click to expand)</summary>
 <details>
    <summary><strong>Update: Episodes and Seasons </strong>(click to expand)</summary>

These initial queries have the aim to correct information related to the <em>dbo:numberOfSeasons</em> and <em>dbo:numberOfEpisodes</em>. In  both cases the values are wrong: the number of seasons should be 3, but it is represented as <em>xsd:2</em>, and the number of episodes should be 24, but it is represented as <em>xsd:16</em>. 
<br>
Furthermore both <em>dbo:numberOfSeasons</em> and <em>dbo:numberOfEpisodes</em> are associated with related DBpedia properties, <em>dbps: dbp:numSeasons and dbp:numEpisodes</em>, which are also incorrect. The procedure adopted to solve this issue is the same for both situations. 
<br>
First, the correction of the number of episodes will be presented, showing the results provided by both <a href="https://chat.openai.com/" target="_blank" rel="noopener noreferrer">ChatGPT</a> and <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini</a>. Then the situation about the number of seasons will be addressed.<br>  
<strong>EPISODES</strong>
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
    4)	Finally also the <em>dbp:numEpisodes</em> was corrected. <br>
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
  <br>
  <strong>SEASONS</strong> <br>
  The same procedure has been applied to the data concerning the number of seasons, following the same approach used for the number of episodes. The steps will be showed in the same order: <br>
1) 
<img src="https://i.imgur.com/wu4LZOI.png" alt="SPARQL Query Seasons" width="600"/> <br>
ChatGPT:
<img src="https://i.imgur.com/o0Y8Cgz.png" alt="SPARQL Query Seasons" width="600"/> 
<img src="https://i.imgur.com/DXZxcYd.png" alt="SPARQL Query Seasons" width="600"/> 
Gemini:
<img src="https://i.imgur.com/jYzEcyV.png" alt="SPARQL Query Seasons" width="600"/> 
<img src="https://i.imgur.com/vgSZTXG.png" alt="SPARQL Query Seasons" width="600"/> 
2) 
<img src="https://i.imgur.com/z58GDZg.png" alt="SPARQL Query Seasons" width="600"/> 
ChatGPT
<img src="https://i.imgur.com/JIdw9xw.png" alt="SPARQL Query Seasons" width="600"/> 
Gemini
<img src="https://i.imgur.com/3yIxS80.png" alt="SPARQL Query Seasons" width="600"/> 
3) 
<img src="https://i.imgur.com/msi9blH.png" alt="SPARQL Query Seasons" width="600"/> 
ChatGPT
<img src="https://i.imgur.com/aAiA8ED.png" alt="SPARQL Query Seasons" width="600"/> 
<img src="https://i.imgur.com/4hzFgGG.png" alt="SPARQL Query Seasons" width="600"/> 
Gemini
<img src="https://i.imgur.com/AJ94aIi.png" alt="SPARQL Query Seasons" width="600"/> 
<img src="https://i.imgur.com/Qqkvubc.png" alt="SPARQL Query Seasons" width="600"/> 
4)
<img src="https://i.imgur.com/edUaQAB.png" alt="SPARQL Query Seasons" width="600"/>
ChatGPT
<img src="https://i.imgur.com/vyGzfpr.png" alt="SPARQL Query Seasons" width="600"/>
Gemini
<img src="https://i.imgur.com/NaPLpnw.png" alt="SPARQL Query Seasons" width="600"/>

  </details>
  <details>
    <summary><strong>Integration: Starring, Caption and Start</strong> (click to expand)</summary>
Subsequently, we identified other categories that required integration, specifically <em>dbo:starring</em>, <em>dbp:caption</em> and <em>dbp:start</em>.
In these cases, the LLMs were prompted to generate CONSTRUCT queries aimed at adding resources to the corresponding categories, which were then executed using <a href="https://yasgui.org/" target="_blank" rel="noopener noreferrer">Yasgui</a>. Both models emphasized that, in order to effectively modify the knowledge graph, INSERT DATA statements would have been required. Therefore, the RDF triples presented here are intended as suggestions that can be exported or uploaded to the graph accordingly. <br>
<strong><em>dbo:starring</em></strong> <br>
 In this case, both LLMs were asked to generate a CONSTRUCT query to add new resources to the class. <br> NOTE: ChatGPT autonomously recommended verifying which resources were already included in the class. Although its proposed query made use of the OPTIONAL keyword—thereby inherently avoiding the addition of duplicate resources, we nonetheless executed the supplementary verification query to fully adhere to the model's suggestion.
Following this, we proceeded to run the CONSTRUCT queries provided by both LLMs. <br>
    ChatGPT:
  <img src="https://i.imgur.com/y968vDM.png" alt="SPARQL Query Starring" width="600"/>
  <img src="https://i.imgur.com/sVUlNyj.png" alt="SPARQL Query Starring" width="600"/>
  <img src="https://i.imgur.com/lXacW7z.png" alt="SPARQL Query Starring" width="600"/>
  <img src="https://i.imgur.com/Pbk7Agz.png" alt="SPARQL Query Starring" width="600"/>
  <img src="https://i.imgur.com/4x14YeE.png" alt="SPARQL Query Starring" width="600"/>
  <img src="https://i.imgur.com/xiQ6tYS.png" alt="SPARQL Query Starring" width="600"/>
  <img src="https://i.imgur.com/KZaqVrz.png" alt="SPARQL Query Starring" width="600"/> 
  Gemini:
  <img src="https://i.imgur.com/iukaHfz.png" alt="SPARQL Query Starring" width="600"/>
  <img src="https://i.imgur.com/5oJ51y1.png" alt="SPARQL Query Starring" width="600"/>
  <img src="https://i.imgur.com/7zlA3QL.png" alt="SPARQL Query Starring" width="600"/>
  <img src="https://i.imgur.com/Ko5a1Mb.png" alt="SPARQL Query Starring" width="600"/>
  <br>
While ChatGPT created a final response including both new and original resources, Gemini only produced triples for the new resources. <br>
<strong><em>dbp:caption</em></strong> <br>
We followed the same procedure for <em>dbp:caption</em>. <br>
    ChatGPT:
<img src="https://i.imgur.com/iukaHfz.png" alt="SPARQL Query Caption" width="600"/>
<img src="https://i.imgur.com/abkzRNL.png" alt="SPARQL Query Caption" width="600"/>
<img src="https://i.imgur.com/III8HHS.png" alt="SPARQL Query Caption" width="600"/>
<img src="https://i.imgur.com/nmMGgp4.png" alt="SPARQL Query Caption" width="600"/>
<img src="https://i.imgur.com/6cROUj8.png" alt="SPARQL Query Caption" width="600"/>
<img src="https://i.imgur.com/ouAviel.png" alt="SPARQL Query Caption" width="600"/>
Gemini
<img src="https://i.imgur.com/4w4gJ8N.png" alt="SPARQL Query Caption" width="600"/>
<img src="https://i.imgur.com/A8umuXJ.png" alt="SPARQL Query Caption" width="600"/>
<img src="https://i.imgur.com/vGxsolt.png" alt="SPARQL Query Caption" width="600"/>
<img src="https://i.imgur.com/0yA665u.png" alt="SPARQL Query Caption" width="600"/>
<img src="https://i.imgur.com/Xcuzwmy.png" alt="SPARQL Query Caption" width="600"/>
<img src="https://i.imgur.com/WopT5uU.png" alt="SPARQL Query Caption" width="600"/>
<br>
The two LLMs gave the same outputs as before: ChatGPT included all resources, whereas Gemini enlisted only the new ones. <br>
<strong><em>dbp:start</em></strong> <br>
In this instance, a preliminary search was requested to verify and retrieve the needed information. In fact, the category dbp:start already contained the launch date of the first and second season, but was missing the date for the third one. So the first step consisted in  checking on both LLMs the missing data: <br>
ChatGPT:
<img src="https://i.imgur.com/ycjgekx.png" alt="SPARQL Query Start" width="600"/> 
Gemini:
<img src="https://i.imgur.com/qPQRZAR.png" alt="Sparql Query Start" width="600"/> <br>
After this verification, we asked to the LLMs for the usual CONSTRUCT query that we then executed on YASGUI. <br>
    ChatGPT:
<img src="https://i.imgur.com/t9opllM.png" alt="SPARQL Query Caption" width="600"/>
<img src="https://i.imgur.com/oW3lcqo.png" alt="SPARQL Query Caption" width="600"/>
<img src="https://i.imgur.com/tk2xuxJ.png" alt="SPARQL Query Caption" width="600"/>
Gemini:
<img src="https://i.imgur.com/pvnW9Zi.png" alt="SPARQL Query Caption" width="600"/>
<img src="https://i.imgur.com/GjeLOxE.png" alt="SPARQL Query Caption" width="600"/>
<img src="https://i.imgur.com/nLj3VKm.png" alt="SPARQL Query Caption" width="600"/>
<img src="https://i.imgur.com/l13q79w.png" alt="SPARQL Query Caption" width="600"/>
<img src="https://i.imgur.com/XQjul3r.png" alt="SPARQL Query Caption" width="600"/>
<br>
In this case GEMINI needed more directions than ChatGPT to realize an adequate query. 
  </details>

</details>

<details>
  <summary style="color:purple"><strong>New Category: Theme</strong> (click to expand)</summary>

  We used <a href="https://chat.openai.com/" target="_blank" rel="noopener noreferrer">ChatGPT</a> and <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini</a> to ask about the main themes in the series.
  <img src="https://i.imgur.com/C16WlTH.png" alt="SPARQL Query Caption" width="600"/> 

  <details>
    <summary>Subsection 2.1 (click to expand)</summary>
    Contenuto della sottosezione 2.1.
  </details>

  <details>
    <summary>Subsection 2.2 (click to expand)</summary>
    Contenuto della sottosezione 2.2.
  </details>

</details>

<details>
  <summary style="color:purple"><strong>Main Section 3</strong> (click to expand)</summary>

  Contenuto principale 3 qui.

  <details>
    <summary>Subsection 3.1 (click to expand)</summary>
    Contenuto della sottosezione 3.1.
  </details>

  <details>
    <summary>Subsection 3.2 (click to expand)</summary>
    Contenuto della sottosezione 3.2.
  </details>

</details>




 

 

   


  
   
  


 

 
  
 
