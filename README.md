# Preparing_Data_Using_Alteryx_(In_Progress)

Coffee or Tea? - That is the question. 

In this project I engaged in a weekly challenge from Alteryx Academy. Here is the description of the challenge:

![Challenge Descr](https://user-images.githubusercontent.com/100732722/235212229-147bdc42-a21c-470c-8d67-e06d38482b61.png)

Source: https://data.world/2918diy/coffee-chain

Here is a snapshot of the data within the start file I was given:

![Start File](https://user-images.githubusercontent.com/100732722/235213134-590e8048-4f60-4e3f-9867-29a546ebac52.png)

Here is the organization of my entire workflow:

![Entire Workflow](https://user-images.githubusercontent.com/100732722/235213197-13558e22-ed98-45d3-90e4-f95916fcd268.png)

The first few questions regard coffee...Here is my coffee workflow:

![Coffee Flow](https://user-images.githubusercontent.com/100732722/235213413-75deed1a-4669-4df5-97e5-779f27240fac.png)


QUESTION 1: Which state is the biggest consumer of regular coffee?
 
 First, I create a custom filter to separate regular coffee from everything else...
 
 ![Coffee - Regular - Filter](https://user-images.githubusercontent.com/100732722/235213902-7c089506-9bee-4e07-b029-a2cb2cef56ee.png)
 
 Second, I use the Summarize tool to GROUP BY state and SUM total sales. This allows us to view consumption per state. 
 
 Side note: For this particular work flow, I changed the column header in the Summary tool solely to create clarity for myself...
 
 ![Coffee - Regular - Summarize](https://user-images.githubusercontent.com/100732722/235215662-544efb42-814c-4334-9b56-130291b4c9f8.png)
 
 Now I need to prep the data so i can select the highest grossing state later on in the workflow. So I use the SORT tool to do exactly that...
 
 ![Coffee - Regular - Sort](https://user-images.githubusercontent.com/100732722/235216347-039cdfc1-28fd-4546-8a65-8c57a384f3bc.png)
 
 Now that the consumption of regular coffee per state is sorted from biggest consumer to smallest consumer, we can pull the #1 state using the SAMPLE tool...
 
 ![Coffee - Regular - Sample](https://user-images.githubusercontent.com/100732722/235216807-c688b351-0423-4cf1-a43b-442d6af790dc.png)

BOOM! We have found the biggest consumer of regular coffee: California.


QUESTION 2: Which state is the biggest consumer of decaf coffee?

Let's do the same thing here as we did with regular coffee. Let's begin by taking all the data from the "False" output of our original filter tool and separate decaf coffee from all tea products...

![Coffee - Decaf - Filter](https://user-images.githubusercontent.com/100732722/235219327-e9c909fe-0132-4539-a753-691ffc50662f.png)

Time to utilize the summary tool to GROUP BY state and SUM sales while changing the name of "state" to "Biggest consumer of Decaf Coffee"...

![Coffee - Decaf - Summarize](https://user-images.githubusercontent.com/100732722/235220709-652de9b2-2cc9-4595-a492-41ceb08f2cbe.png)

Like before, we will now use the SORT tool to organize consumption levels per state in descending order so we can select the biggest consumer with our next tool...

![Coffee - Decaf - Sort](https://user-images.githubusercontent.com/100732722/235221240-2ec48f09-e801-4dfe-97c4-863258becb1a.png)

...The SAMPLE tool...time to select the biggest consumer of decaf coffee...

![Coffee - Decaf - Sample](https://user-images.githubusercontent.com/100732722/235222033-9c53425d-8b54-4a16-a300-882d4ddbc053.png)

BAM! We have found the biggest consumer of decaf coffee: Illinois.

QUESTION 3: Which type of coffee drink is the most popular?

At this point I developed a separate section within my workflow for this question. The connection is coming straight from the input file itself...

![Most Popular Coffee Flow](https://user-images.githubusercontent.com/100732722/235222843-1b4eb5f4-588b-48a7-8326-84076e9a83d4.png)
