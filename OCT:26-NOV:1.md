**Meeting to gather client requirements, OCT/28**

Before the meeting we set up with our client individually, we proposed a couple of questions in advance:

- Sample engines that our client have used before that can give us a picture of what are we expected to do
- Her users experiences with the engine metioned above?
- How can the data engine help her?
- Main features she is looking for in a "data engine"





**From the user requirements we gathered, we drafted two persona files**









##**Here are our meeting notes with our client**



*This is the meeting notes with Professor Holloway and Jamie on 28th Oct on client requirements. This note is made from Eric's recollections and notes taken*.



### What we know about the dataset:

Format and specific contents are not yet confirmed, but it is likely to have the following attributes:

- Media source
- Academia source
- Updated during an 24 hour interval so need to consider inclusion in calculation to track new inputs



### Target user

- Government officials
- Policy makers
- Researcher including 
  - Researcher
  - ”Proxy researchers“: researches responsible for rasing public attensions and advocating policy changes



###MoSCoW List at this moment

- Main difference will be in terms of target users, 
- No Functionalities required at this stage
- Will be updated as dataset structure is clear

- Primary data set looking for researches and policy makers
- Secondary user set for different user groups(undefined)



### Target usage:

The topics are elaborated based on meeting notes and my personal recollections and there may be points mis-interpreted. This part is consisted of possible topics and my proposed solutions, and how I view those questions.

1. **For policy maker to know where to spend the budget in AT**
   - This requirement is relatively ambiguous, and I think it's better to categorize it into the following usage scenarios.



2. **A step by step data filtering system on user questions**

   - Includes an interactive design with limited filter functions.

   - Targeting policy makers.

   - Uses a step by step guidence for filter function selections. 

   - For example, search for people has a disability, less than 60, salary over xxxx

   - Can set up filering system to solve this challenge, but functionalities is rather limited due to the unclear nature of the data set.

   - Not really sure how this idea linked to media posts/ academia posts.

     

3. **How media report on research message**

   - I interpret the message as "How media's choice on research breakthroughs is different as researches's evaluations".
   - Hard point: data set may not be designed for this comparison.
   - We can consider extracting common features in media's popular posts and suggests why those key words attracts popularity.
   - Researches' evaluations are also objective, may create diversified result when deploying model, which ultimately assumed a common perception(This is my understanding on the rule finding mechanism of any ML model).

   

4. **A transparent way to select the most relevent/influencial media post/research paper on a given question**

   - Transparency in decision making means that we should come up with a set of rules to evluate how different factors influences the effectiveness of a post
   - Rules can be dynamic but open to examinations
   - An example would be college ranking by the Thames or US news. They come up with a different set of rules to evaluate world wide colleges.
   - PS. Maybe we should consider Google search  :(

   

5. **Report user feedbacks and public views from media posts**

   - Will be consist of two parts : Analysis on special keywords + Report generator

   - We can do a classifier based on importance of keywords in a media/academica posts

   - Then calculate what is the most weighted characteristic words on public's view on a special policy for example.

   - Generate report/keywords lists based on the analysis results

   - A typical workflow will be: (example) 

     - Find the keywords: "policy change on disability cares"  -> "policy" + "disability care"
     - Found out publics opinions on that: count the most occured adjective on this category
     - Categorize keywords:  "Satisfactory", "Easy to access"
     - Generate a report based on our keywords and statistical analysis results

     

6. **Data portal**

   - Given a set of questions, and come up with a best answer/ best report to that questions
   - Maybe approached in three of the following ways:
     - Statistical analysis on keyword occurence, similar to proposal No.5
     - Earlier NLP models like "attentive Reader" / "Impatient Reader" that analysis the wording in the given questions and map them to a assumed answer in the "context" which is our dataset. This approach originally used CNN/DailyMail as datasets, especially the topic sentences from reports as questions and the full texts as answering contexts to train the model. This is somehow linked to our topic of media posts but I doubt whether I can finish this along with my team.
     - More advanced NLP models like "BERT", a model that maps answers to context, and extracts them form the contexts, are designed for this kind of problems and it does better in tagging than human in a challenge in 2018. Again, the difficulty will be possibilities to deploy and it requires a large data set to train using deep learning algorithms. (The dataset used for it is SQuAD and SQuAD2.0)
   - Also highly dependent on data set structure and avaliablities. Traning resources are also very important, I don't think it's feasible to run a deep learning model on our labtops
   - This approach are also quite similar to a chat bot, which is another interesting suggestion from our meeting





## Interesting proposal ideas(Having no confidence in completion though)

If the data set is mostly not labeled and contains a high level of non-usage, maybe consider a Snorkel approach. (Software by Stanford that use weak supervised learning to automate the taging process to prepare datasets for further trainings)

If the data is updated frequently(24hour interval), maybe consider deccentralised calculation procedure? I think some group was research on a distributed approach in training calculations. (Not really sure about this but I can look it up soon)

NLP in Open QA(They used training sets concluded from Daily Mails I think), reference to SQuAD as mentioned above.

