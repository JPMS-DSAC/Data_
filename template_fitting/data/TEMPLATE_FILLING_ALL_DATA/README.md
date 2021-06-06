# Template filling data

*Input data for Tempalte filling* : 

Regulation documents split into its component regulations. Each regulation is also split into its component sub-regulations. Refer to `ALL_REGULATIONS_JSON_FLATTENED_SPLIT_SUBREG` for the input data

The data is in the form of 

|- Investment Advisors.json

-- Has all versions of Investment Advisor regulations in this json eg : Jan 11 2021

For each version of each type of regulatory document, one corresponding file is generated. 
Example :  Investment Advisors has Jan 11 2021 and Jan 21 2013 version, 
so it generates files of the form Investment_Advisors_Jan_11_2021 and Investment_Advisors_Jan_21_2013

*Output data*

**Entities Tagged** : 

Each regulatory document, which is a collection of regulations was run through the **rule based template fitting** code,
and for each regulation `Entities`, `Condition`, `Action` were extracted

`Entities` : This is the person/group/organisation, the regulation is about (Label : `ENT`)

`Condition` : The conditions the regulation is valid for (Label : `COND`)

`Action` : The action of the regulation (Label : `ACT`)

Example :  

```{
        "text": "The Board may require the sponsor to furnish such further information or clarification as may be required by it.",
        "ents": [
            {
                "start": 4,
                "end": 9,
                "label": "ENT"
            },
            {
                "start": 10,
                "end": 112,
                "label": "ACT"
            }
        ],
        "title": null
    }
```

Here `text` is the regulation text and  
`span(4:9)` which is Board and it is the `Entity`,
` span(10:112)` which is "may require ..." is the `Action`


**Entites HTML View** : 

The above tagged information is rendered as HTML, using Spacy entity visualizer (https://spacy.io/usage/visualizers#ent). So each regulation is displayed in html, with the tag information. This is just a visual representation of the generated labels in `Entites Tagged`



**Entities_Text**:

Regulations are grouped by entity.

In each file in this folder (named according to convention described above), the regulations have been modified to if-else conditions. Below is a sample example
``` ===============================================================================================
investment adviser :
{
--> shall maintain the following records,-(a)  Know Your Client records of the client;(b)  Risk profiling and risk assessment of the client;(c)  Suitability assessment of the advice being provided;(d)  Copies of agreements with clients, if any;(e)  Investment advice provided, whether written or oral;(f)  Rationale for arriving at investment advice, duly signed and dated;11(g)  A register or record containing list of the clients, the date of advice, nature ofthe  advice,  the  products/securities  in  which  advice  was  rendered  and  fee,  ifany charged for such advice.(2) All records shall be maintained either in physical or electronic form and preservedfor a minimum period of five years:Provided  that  where  records  are  required  to  be  duly  signed  and  are  maintained  inelectronic form, such records shall be digitally signed.(3) An investment adviser shall conduct yearly audit in respect of compliance with theseregulations from a member of Institute of Chartered Accountants of India or Institute of

--> shall appoint a compliance  officer  who  shall  be  responsible  for  monitoring  the  compliance  by  the investment adviser in respect of the requirements of the Act, regulations, notifications, guidelines, instructions issued by the Board.

--> <context> An investment adviser which is a body corporate or a partnership firm shall appoint a compliance  officer  who  shall  be  responsible  for  monitoring  the  compliance  by  the investment adviser in respect of the requirements of the Act, regulations, notifications, guidelines, instructions issued by the Board. - investment adviser<context> shall redress client grievances promptly.(2)  An  investment  adviser  shall  have  adequate  procedure  for  expeditious  grievanceredressal.(3)  Client grievances pertaining to financial products in which investments have beenmade based on investment advice, shall fall within the purview of the regulator of suchfinancial product.(4)  Any  dispute  between  the  investment  adviser  and  his  client  may  be  resolvedthrough arbitration or through Ombudsman authorized or appointed for the purpose by

--> if [An investment adviser who -(a)  contravenes  any  of  the  provisions  of  the  Act  or  any  regulations  or  circularsissued thereunder;(b)  fails to furnish any information relating to its activity as an investment adviseras required by the Board;14(c)  furnishes to the Board information which is false or misleading in any materialparticular;(d)  does not submit periodic returns or reports as required by the Board;(e)  does not co-operate in any enquiry, inspection or investigation conducted by theBoard;(f)  fails to resolve the complaints of investors or fails to give a satisfactory reply tothe Board in this behalf,] : 
 shall be dealt with in the manner provided under the Securities and Exchange Board

}
```

"===" is the seperator
Here `investment adviser` is the entity about which the 4 regulations are talking about.

`{,}` - start and end of all the regulations pertaining to `investment adviser`, with `-->` showing that a new regulation has started. In this example there are 4 regulations talking about investment adviser

The last regulation is an example if [`condition`] [`action`], the other regulations are simple `action` statements.

`<context>` tags give relavant context information wherever necessary, so that the regulation is better understood. This context tag is used when other regulations or subregulations or the word such is used (which implies that the entity of the regulation is being talked about in other regulations).

