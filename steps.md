<div id="menu" style="position:fixed;top:0;left:0;width:100%;background:#f8f8f8;border-bottom:1px solid #ddd;padding:5px 0;z-index:1000;text-align:center;">
  <a href="index.html" style="margin:0 15px;color:#0366d6;font-weight:bold;">Home</a>
  <a href="topic-description.html" style="margin:0 15px;color:#0366d6;font-weight:bold;">Topic Description</a>
  <a href="methodology.html" style="margin:0 15px;color:#0366d6;font-weight:bold;">Gap, Methodology and Tools</a>
  <a href="steps.html" style="margin:0 15px;color:#0366d6;font-weight:bold;">Methodological Steps</a>
  <a href="challenges.html" style="margin:0 15px;color:#0366d6;font-weight:bold;">Challenges & LLMs Differences</a>
</div>

<br>
# Methodological Steps
<strong>First steps: update and integration</strong>
<br><br>
These initial queries have the aim to correct information related to the dbo:numberOfSeasons and dbo:numberOfEpisodes. In  both cases the values are wrong: the number of seasons should be 3, but it is represented as xsd:2, and the number of episodes should be 24, but it is represented as xsd:16. 
<br>
Furthermore both dbo:numberOfSeasons and dbo:numberOfEpisodes are associated with related DBpedia properties, dbps: dbp:numSeasons and dbp:numEpisodes, which are also incorrect. The procedure adopted to solve this issue is the same for both situations. 
<br>
First, the correction of the number of episodes will be presented, showing the results provided by both <a href="https://chat.openai.com/" target="_blank" rel="noopener noreferrer">ChatGPT</a> and <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini</a>. Then the situation about the number of seasons will be addressed.
