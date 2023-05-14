# **Table Summarization**

The Task is as follows: <br>
Using any of the available language model via any open-source platform, can you try summarizing the following table to explain the values in a human readable format in either of the following ways:

a. Column wise <br>
b. Row wise <br>
c. Complete table summarization
<hr>

## Solution Approch (Using Column-wise):
1. Creating a sentence for each datapoint, utilized the column and row descriptions of the data.

```
    For example: For the data at (0, 0): 
            sentence = January 20.7 Average Temperature °C
```

2. Using different approaches to converting the above sentence into meaningful sentences: 

> In order to generate more meaningful variations of the sentence mentioned above, I employ three approaches. All of these approaches are based on a common basic model, i.e. Text2Text model:

-  Method 1: Direct Text2Text
> directly to generate alternative sentences by utilizing the Text2Text generation pipeline

-  Method 2: Bag Of Words
> Adding some extra words to the sentence for introducing variations and then feeding it into the text2text model

- Method 3: Masking 
> Using Masking pipelines to add meaningful words to the original sentence then passed through the Text2Text generation model to generate alternative versions. By masking specific parts of the sentence and replacing them with words can provide more context or specificity  

3. Making a new sentence by combining the generated sentences from the Text2Text model column-wise 


> After generating alternative sentences for each datapoint, I combine the generated sentences column-wise. By aligning the sentences corresponding to each column, I create a new sentence that incorporates information from all the columns. This combined sentence provides a comprehensive representation of the data, highlighting the relationship between different column values


4. Then utilizing summarizing pipelines to summarize the whole combined sentence:


> To summarize the entire combined sentence, I employ Summarizing pipelines. By the combined sentence and extracting the most important details, I generate a summarized version that captures the key aspects of the original information

<hr>
