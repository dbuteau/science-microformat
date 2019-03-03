# Scientific HTML microformat
Make the net less full of bullshit

A Thinking about scientific specialization microformat 

## Goal:
Workout a better web semantic parsing allowing bot to recognize and sort scientific publication giving them a credibility score based on available informations. The bot will go crawl on the net check what is given in microdata, if the resource is available and correct.

## Credibility score:
Credibility score go from -1 to 3. 
Where: 
- -1: represent really poor credibility this can be considered as clearly a fake news
- 0: a study not pair checked or poorly documented or poorly documented meta-analysis
- 1: a study containing verifiable facts, or poorly documented meta-analysis
- 2: a well documented and pair checked study
- 3: a meta-analysis really well documented  

In the following the credibility score will be noted CS.  
It will be calculated depending of presence and quality of contents given in following microformat.  
Unless contrary is mentioned, every publication start at CS=0 for calculation

## Proposed Microformat
The following micro format list are optional unless marked as mandatory.
Optionals micro-format have no effect on CS

**class:** h-science

**rel-publication: (mandatory)** describe what kind of publication is the content. 
If not given, or not corresponding to the following list CS=0 and ignore all others CS modificators
- Meta-analysis (if selected CS start at 3 but can be amended by other microformat without exceeding CS=3)
- search
- synthesis
- transfer
- vulgarization (press should use this one)
- individual
- collective
- work-chapter
- technical-manual
- technical-sheet
- Congress-communication

**rel-abstract:** abstract of the publication

**rel-conclusion:** conclusion of the publication

**rel-tag:** contain science domain the publication concern. eg: biology, physic, chemistry etc. 

**rel-authors: (mandatory)** describe the content following will be a list of all author informations, if empty or not provided CS -1 modificator
- **rel-author-name: (mandatory)** Firstname and Lastname of the author
- **rel-author-position:** professor, chief, etc
- **rel-author-specialization: (mandatory)** if unrelated to rel-tag CS-1 modificator
- **rel-author-organization:** academia, laboratory, industry
- **rel-author-org-name:** the name of the organization author work for
- **rel-author-ref:** link to the author presentation from their university/laboratory/enterprise/work place website
- **rel-author-interest-conflicts:** declaration of interest conflict from the author. If none given or empty consider there is no interest conflict declared. **Honest interest conflict declaration must not be penalized to encourage this behavior**

**rel-quotation:** list of other publications referencing to this work, if not present or empty rel-quotation bot must consider no quotation exist. 
If no quotation exist CS -1 modificator. 
If more than 5 quotation is listed and available from certified domain CS+1 modificator

**rel-source:** used for list links to other publications as source. 
If not given, or link does not refer to an available existing resource from certified domain, credibility score=0 and ignore all other modificators.  
If given and available from certified domain CS+1 modificator.  
See certified domain section, each domain have its own score.  
The score of the domain can affect the CS.  
If the domain score is below 2,5 or not provided then CS-1 modificator

## Certified Domains
See: https://www.qoam.eu/journals
This list contain domain scoring which can be use as CS modificator. 
If the domain score is below 2,5 or not provided then CS-1 modificator
