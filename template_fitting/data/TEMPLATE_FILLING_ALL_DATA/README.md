# Template filling data

Input data : 

Regulation Documents, converted to text and split by regulations

**Annotations data** : 

**Entities Tagged** : 
    Each regulation was run through the **rule based template fitting** for each regulation,
    and for each regulation `Entities`, `Condition`, `Action` were extracted

    `Entities` : This is the person/group/organisation, the regulation is about 

    `Condition` : The conditions the regulation is valid for

    `Action` : The content of the regulation


**Non Annotatated data** : 

**Entites HTML View** : 
    The above tagged information is rendered as HTML, using Spacy entity visualizer (https://spacy.io/usage/visualizers#ent), and the outputs collected. So each regulation is displayed in html, with the tag information 

**Entities_Text**:
    Regulations are grouped by entity, this is to ensure better readability of regulations.

