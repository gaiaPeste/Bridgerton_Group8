<div id="menu" style="position:fixed;top:0;left:0;width:100%;background:#f8f8f8;border-bottom:1px solid #ddd;padding:5px 0;z-index:1000;text-align:center;">
  <a href="index.html" style="margin:0 15px;color:#800080;font-weight:bold;">Home</a>
  <a href="topic-description.html" style="margin:0 15px;color:#800080;font-weight:bold;">Topic Description</a>
  <a href="methodology.html" style="margin:0 15px;color:#800080;font-weight:bold;">Gap, Methodology and Tools</a>
  <a href="steps.html" style="margin:0 15px;color:#800080;font-weight:bold;">Methodological Steps</a>
  <a href="challenges.html" style="margin:0 15px;color:#800080;font-weight:bold;">Challenges & LLMs Differences</a>
</div>
<p align="center">
  <img src="https://www.farodiroma.it/wp-content/uploads/2022/04/AAAAQf3Io4rXuO2h_zb3O1V4Q8Q4h2ol54FxldOPKIM-v719mG5cbJ8a7UVzbVT3dpNoPyMSBuEwdC7jEHt6u3WJE2831zJ4udb3uXyYpJ5EubMkacQ4y2LUPl7sZMn_nHBVKX5XUPEiW3rZC9_c7uaD1LdMyo.jpeg" alt="Bridgerton" style="display: block; margin: auto; max-width: 100%; height: auto;">
</p>


<br>

# Challenges and LLMs Differences

## Challenges

<strong>WIKIDATA VS DBPEDIA</strong> 
<br>
One of the main challenges we faced during the project was deciding between two major knowledge bases: <a href="https://www.wikidata.org/" target="_blank" rel="noopener noreferrer">Wikidata</a> and <a href="https://www.dbpedia.org/" target="_blank" rel="noopener noreferrer">DBpedia</a>.<br>
Both offer structured semantic data, but they differ significantly in terms of ontology, update frequency (how often the data is refreshed or revised), and level of detail. <br>
Wikidata provides a more dynamic and community-curated dataset with flexible properties, while <a href="https://www.dbpedia.org/" target="_blank" rel="noopener noreferrer">DBpedia</a> relies on a more rigid and formally defined ontology extracted from <a href="https://www.wikipedia.org/" target="_blank" rel="noopener noreferrer">Wikipedia</a>. <br> 
Since our task was to identify gaps and build RDF triples, we ultimately chose <a href="https://www.dbpedia.org/" target="_blank" rel="noopener noreferrer">DBpedia</a>. This decision was driven by the fact that <a href="https://wiki.dbpedia.org/services-resources/ontology">DBpedia's fixed Ontology</a>
and structured format made it easier to detect inconsistencies and missing information. <br>

<strong>REALIZATION OF THE WEBSITE ON GITHUB</strong>

During the development of our website ([link]), we encountered a challenge related to Markdown (MD) rendering on GitHub Pages. While GitHub is expected to support Markdown, we found that only the homepage (index.md) was properly interpreted as Markdown. All other sections required HTML, sometimes combined with Markdown, to render correctly.

To address this issue, we converted most elements from Markdown to HTML. This process required more steps than using Markdown alone, which is generally simpler and more efficient. Links and images posed particular challenges:
<ul>
  - Links in HTML, such as <br>
  <a href="https://example.com" target="_blank" rel="noopener noreferrer">Exmaple</a>, <br> required more effort compared to Markdown links which are sinmpler to write even manually: <br>[Example.com](https://example.com);
  - The same applies to images: the HTML version <br>
  <img src="https://www.example.com/image.png" alt="Image description" width="600"/>, <br> 
  is more verbose than the MD equivalent: <br>
  ![Image description](https://www.example.com/image.png).
</ul>
Moreover, we also had to adapt the entire syntactic structure—such as <strong>bold</strong>, <em>italics</em>, and line breaks—to fit HTML formatting instead of Markdown. In fact, the files used to build the different sections did not recognize asterisks for bold or italics and line breaks had to be explicitly added using the "<br>" tag. <br>

<strong>CHATGPT VS GEMINI</strong> 
<br>
The queries that <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini</a> generates use a syntax or format that the query editor does not recognize or support. This means when you try to run these queries in the editor, they produce errors or don’t work as expected. This incompatibility could be due to differences in query language versions, supported features, or syntax rules between <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini</a> and the query editor.
To support this thesis we took as an example the query concerning the music genre of Bridgerton's soundtrack (classical).
<ol>
1. Incorrect or Nonexistent URIs <br>
AI models sometimes "hallucinate" URIs — they might guess something like > dbr:Classical <br>
But in <a href="https://www.dbpedia.org/" target="_blank" rel="noopener noreferrer">DBpedia</a>, the correct resource might actually be: <br>
<em>dbc:Classical_music</em> <br>
The difference between dbr: (for entities) and dbc: (for categories) matters. If <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini</a> uses a nonexistent or invalid URI, your query will return nothing or throw an error. </ol>
<ol>
2. Wrong predicate usage <br>
We use predicates like dbo:genre or dbo:subject, which are valid <a href="https://wiki.dbpedia.org/services-resources/ontology">DBpedia Ontology</a> properties. <br>
Sometimes, <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini</a> might suggest something like: <a href="https://dbpedia.org/resource/Bridgerton" target="_blank" rel="noopener noreferrer"><em>dbr:Bridgerton</em></a><em>\  dct:subject \  dbr:Classical_music </em>. <br>
But dct:subject isn't commonly used in DBpedia (it mostly uses dbo:subject). So even though the triple is syntactically valid, it doesn't align with how <a href="https://www.dbpedia.org/" target="_blank" rel="noopener noreferrer">DBpedia</a> is structured, and the data won’t match. </ol>
<ol>
3. Missing filters for language <br>
When retrieving labels (e.g., rdfs:label), your queries smartly include: FILTER (lang(?label) = "en") <br>
<a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini</a> might omit this, leading to results in many languages, which can break parsing and get a bunch of messy, multi-language labels. </ol> <br>
This issue was mainly addressed by asking the same <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini</a> model to reformulate the queries -by adding more specific instructions to the prompt- or by submitting <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini</a>'s query to <a href="https://chat.openai.com/" target="_blank" rel="noopener noreferrer">ChatGPT</a> and asking what was syntactically wrong with it. We observed that <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini</a>, despite the numerous additional indications, generally required more steps to produce the desired query. In contrast, <a href="https://chat.openai.com/" target="_blank" rel="noopener noreferrer">ChatGPT</a> was able to quickly identify the problem and suggest a valid alternative. Other differences between the LLMs will be addressed in the next paragraph.


## LLMs Differences 
While working on our project, we compared  <a href="https://chat.openai.com/" target="_blank" rel="noopener noreferrer">ChatGPT</a> and <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini</a> and observed some differences between the two LLMs, both in terms of reasoning processes and outputs. <br><br>
<a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini</a> shows weaker understanding of RDFS and makes more semantic errors compared to <a href="https://chat.openai.com/" target="_blank" rel="noopener noreferrer">ChatGPT</a>, especially in zero-shot settings. However, when provided with corrections or few-shot examples, <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini</a> is able to adjust and produce more accurate responses.<br><br>
Another notable trait is <a href="https://gemini.google.com/" target="_blank" rel="noopener noreferrer">Gemini</a>'s tendency to explain reasoning processes in detail, even when chain-of-thought explanations are not required by the prompt. It tends to provide not only the SPARQL queries but also detailed explanations of how they work inside the queries. While this can be helpful in some cases, it often results in overly verbose and non-necessary responses, though it also reflects the model’s design for transparency in reasoning. This additional material can become confusing, especially when we simply need to copy and paste the query into <a href="https://yasgui.org/" target="_blank" rel="noopener noreferrer">Yasgui</a> to test it. The extra explanations sometimes make it harder to identify the actual query, slowing down the workflow. <br><br>
<a href="https://chat.openai.com/" target="_blank" rel="noopener noreferrer">ChatGPT</a>, by contrast, is more concise and to the point. It usually provides a clear and direct answer, focusing on delivering the correct query without unnecessary elaboration—unless specifically requested. This makes it easier and quicker to extract and use the query. Furthermore, the syntax of the queries generated by <a href="https://chat.openai.com/" target="_blank" rel="noopener noreferrer">ChatGPT</a> tends to be more accurate and compatible with SPARQL tools like <a href="https://yasgui.org/" target="_blank" rel="noopener noreferrer">Yasgui</a>.
