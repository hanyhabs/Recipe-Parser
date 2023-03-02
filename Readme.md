# Interactive Cook Book #

## Introduction

Recipe parsing is the process of extracting relevant information from a recipe text such as ingredients, quantities, cooking times, and instructions. By applying NLP techniques, we developed a recipe parser application that can automatically extract structured data from unstructured recipe text. This can be useful for various applications such as meal planning, recipe recommendation, and grocery shopping.
      In this process, we can use techniques such as named entity recognition, part-of-speech tagging, dependency parsing, and machine learning algorithms to identify and extract relevant information from recipe text. With this information, we can generate structured data such as ingredient lists, cooking directions, and nutritional information.

## Process
1) The cooking instructions to be stores in a sequential data structure, e.g. list
2) The user should be able to read/listen to the contents
3) The user can navigate between the steps
4) The user can ask questions

## Methodology

### UI (using tkinter library)###
  1) Define a window of 800x800
  2) Define textbox / button layout
    Textbox 1 (Input recipe): User input for recipe requirement. It opens the website www.allrecipes.com and enters the input in the search box, and selects the first      search suggestion. The webpage is then scraped when Button 1 “Search” is clicked.
    Textbox 2 (Input Query): User input for query. Main function is called when Button 2 “Set” is clicked.
    Textbox 3: This displays the answer to the query. There is a refresh button, that clears the textbox, and shows a list of possible questions in textbox 2 when          Button 3 is clicked (“Refresh”).

### Code ###
  1) Input the recipe name from the user, search on the website and open the link of the recipe.
  2) Scrape the webpage.
  3) Find Ingredients: Scrape all the ingredients from the website and store in a list. Additionally, The website uses symbols for fractions, so substituting ½ =         0.5, 1/3 = 0.34 etc
  4) Get Steps: Scrape all the steps from the website and store in a list.
  5) Get Kitchen Tools: We have a hand made lexicon of most commonly used kitchen tools. We iterate over every step to find matches and store in a list.
  6) Get Temperature: We have a hand made lexicon of temperature units. We iterate over every step to find matches and store in a list.
  7) Get Quantity:
    a. We tokenize the query
    b. Perform POS tagging on all the words
    c. 3 separate cases for 1-word, 2-word and 3-word ingredients. Match chain of words such that last word is a noun (s) (NN / NNS)/ proper noun(s) (NNP / NNPS) and         all previous words can be either adjective (JJ) or noun (s) (NN / NNS)/ proper noun(s) (NNP / NNPS). This will give us the ingredient whose quantity is to be         found
    d. Match ingredient in the ingredients step and display
  8) Get Previous: We match keywords previous / before, then remove all stopwords in the query. We match the remaining ingredient in the steps and display the              previous step. 
  9) Get Next: We match keywords next / fter, then remove all stopwords in the query. We match the remaining ingredient in the steps and display the next step. 
  10) Preparation Time / Cooking Time / Total Time / Number of Servings: Scrape all the ingredients from the website and store in a list.
  11) Question Selector: Takes user query and check keywords to understand which question is being asked, and accordingly calls the required function.
  
  ## Conclusion
  Recipe parsing using NLP is an exciting application of artificial intelligence that has the potential to transform the way we cook and consume food.
