<div id="menu" style="position:fixed;top:0;left:0;width:100%;background:#f8f8f8;border-bottom:1px solid #ddd;padding:5px 0;z-index:1000;text-align:center;">
  <a href="topic-description.html" target="_blank" rel="noopener noreferrer" style="margin:0 15px;color:#0366d6;font-weight:bold;">Topic Description</a>
  <a href="methodology.html" target="_blank" rel="noopener noreferrer" style="margin:0 15px;color:#0366d6;font-weight:bold;">Methodology</a>
  <a href="steps.html" target="_blank" rel="noopener noreferrer" style="margin:0 15px;color:#0366d6;font-weight:bold;">Steps</a>
  <a href="challenges.html" target="_blank" rel="noopener noreferrer" style="margin:0 15px;color:#0366d6;font-weight:bold;">Challenges</a>
</div>


<br><br><br><br><br>

# Abstract

In this project, we explored and enriched a knowledge graph (KG) about the TV series Bridgerton by combining SPARQL querying techniques with the assistance of large language models (LLMs), specifically ChatGPT (OpenAI) and Gemini (Google). Our goal was to model and assess whether certain concepts (e.g., general information and knowledge, themes, soundtrack) are represented in the graph, and where necessary, propose new triples.

---

# Menu

- [Topic Description](#topic-description)
- [Gap, General Methodology & Tools](#gap-general-methodology-tools)
- [Methodological Steps](#methodological-steps)
- [Challenges and LLMs differences](#challenges-and-llms-differences)

---

# Project by

> Alessia Gavelli,  
> Elisa Mainardi &  
> Gaia Pestelli

![Branching](https://media-assets.vanityfair.it/photos/660c178833508f82229a46bf/16:9/w_1280,c_limit/1_OWWnuMfWov0Tc4IjIU0RHQ%20copia.jpg)

---

## Topic Description

For our project, we have chosen to focus on the television series Bridgerton, a production that has gained widespread popularity and cultural relevance in recent years.This decision was made collectively, as the series is well-known, widely discussed, and familiar to all members of the group. Bridgerton includes multiple **interconnected storylines** and social dynamics, making it ideal for building a semantic graph (e.g. DBpedia) where entities and links reflect both explicit and inferred connections. This allows us to apply advanced querying techniques (e.g. Yasgui) to explore patterns, relationships, and hierarchies within the fictional world.

Bridgerton is a historical romance television series created by Chris Van Dusen and produced by Shondaland, based on the bestselling novels by Julia Quinn. The show is set in **Regency-era London** (early 19th century), a period characterized by rigid social structures, elaborate courtship rituals, and intense pressure to marry advantageously. As of 2025, Bridgerton has released three seasons; additionally, the series has been renewed for Seasons 5 and 6, ensuring the continuation of the Bridgerton family's stories.

The narrative primarily follows an affluent family whose members are each introduced to the social season, where finding a suitable marriage partner is both a personal and familial priority. Each season centers on the romantic and emotional development of a different family member, exploring how **individual desires often clash with societal expectations**. The stories are marked by themes of **longing, personal growth**, and the delicate balance between **public image and private truth**. A key narrative device is the presence of an anonymous gossip columnist whose scandalous reports influence public perception and add intrigue to the unfolding events. A companion series to Bridgerton expands the universe by focusing on the early life of a prominent royal figure featured in the main show. "Queen Charlotte: A Bridgerton story" is set in the same alternate version of Regency society, this prequel explores themes such as **power, societal change, personal sacrifice, and the pressures of leadership**.
Thematically, Bridgerton explores the tension between **love and societal obligation, gender roles, and the importance of reputation** within the aristocracy. It also addresses female agency, particularly through its female characters who seek autonomy in a patriarchal world. While not historically accurate, the show embraces a diverse and **inclusive casting**, presenting a reimagined Regency society in which race does not impede social mobility—thus blending historical drama with modern values.
Visually, Bridgerton is known for its opulent production design, featuring grand estates, extravagant costumes, and stylized reinterpretations of period customs. Despite its historical setting, the series often incorporates **contemporary music (in classical arrangements) and **modern storytelling techniques**, creating a fresh, hybrid aesthetic.
.

---

## Gap, General Methodology & Tools

**HOW THE GAP WAS IDENTIFIED**
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

---

## Methodological Steps

Contenuto della sezione 3.

---

## Challenges and LLMs differences

Contenuto della sezione 4.
