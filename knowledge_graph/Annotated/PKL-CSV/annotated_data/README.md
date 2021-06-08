48annotated -> NER labeling of tokens in sub-regulations (for layer 3 in Knowledge Graph) of the form {NER label : [token start position, token end position]}

cleanedregtopics48 -> list of topics from SEBI regulatory documents (document-wise)

cleanedregulations -> list of SEBI sub-regulations

conceptpaper_graph -> list of graph connection information between concept paper documents and SEBI amended regulatory document in the form [filename, year, regulatory document, concept/topic discussed for edge labeling]

docs_chaps -> chapter names extracted from 48 SEBI regulatory documents

ig -> list of graph connection information between informal guidance documents and SEBI sub-regulations in the form [filename, subregulation id, regulatory document, description for edge labeling]

lc -> list of graph connection information between case documents and SEBI sub-regulations in the form [filename, subregulation id, regulatory document, allegations made for edge labeling]

regtopics -> list of topics from SEBI sub-regulations (subregulation-wise)
