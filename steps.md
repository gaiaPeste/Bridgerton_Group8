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
<strong>First steps: update and integration</strong>
<br><br>
These initial queries have the aim to correct information related to the <em>dbo:numberOfSeasons</em> and <em>dbo:numberOfEpisodes</em>. In  both cases the values are wrong: the number of seasons should be 3, but it is represented as <em>xsd:2</em>, and the number of episodes should be 24, but it is represented as <em>xsd:16</em>. 
<br>
Furthermore both <em>dbo:numberOfSeasons</em> and <em>dbo:numberOfEpisodes</em> are associated with related DBpedia properties, <em>dbps: dbp:numSeasons and dbp:numEpisodes</em>, which are also incorrect. The procedure adopted to solve this issue is the same for both situations. 
<br>
First, the correction of the number of episodes will be presented, showing the results provided by both <a href="https://chat.openai.com/" target="_blank" rel="noopener noreferrer">ChatGPT</a> and <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini</a>. Then the situation about the number of seasons will be addressed.
