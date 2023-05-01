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

...

**QUESTION 1: Which state is the biggest consumer of regular coffee?**
 
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

...

**QUESTION 2: Which state is the biggest consumer of decaf coffee?**

Let's do the same thing here as we did with regular coffee. Let's begin by taking all the data from the "False" output of our original filter tool and separate decaf coffee from all tea products...

![Coffee - Decaf - Filter](https://user-images.githubusercontent.com/100732722/235219327-e9c909fe-0132-4539-a753-691ffc50662f.png)

Time to utilize the summary tool to GROUP BY state and SUM sales while changing the name of "state" to "Biggest consumer of Decaf Coffee"...

![Coffee - Decaf - Summarize](https://user-images.githubusercontent.com/100732722/235220709-652de9b2-2cc9-4595-a492-41ceb08f2cbe.png)

Like before, we will now use the SORT tool to organize consumption levels per state in descending order so we can select the biggest consumer with our next tool...

![Coffee - Decaf - Sort](https://user-images.githubusercontent.com/100732722/235221240-2ec48f09-e801-4dfe-97c4-863258becb1a.png)

...The SAMPLE tool...time to select the biggest consumer of decaf coffee...

![Coffee - Decaf - Sample](https://user-images.githubusercontent.com/100732722/235222033-9c53425d-8b54-4a16-a300-882d4ddbc053.png)

BAM! We have found the biggest consumer of decaf coffee: Illinois.

...

**QUESTION 3: Which type of coffee drink is the most popular?**

At this point I developed a separate section within my workflow for this question. The connection is coming straight from the input file itself...

![Most Popular Coffee Flow](https://user-images.githubusercontent.com/100732722/235222843-1b4eb5f4-588b-48a7-8326-84076e9a83d4.png)

I begin by using the FILTER tool to separate coffee from tea...

![Most Popular Coffee - Filter](https://user-images.githubusercontent.com/100732722/235225960-20e51c35-0176-46e2-9aa5-b7baf0fc38d7.png)

Time to GROUP BY and SUM just like we've done twice before...

![Popular Coffee - Summarize](https://user-images.githubusercontent.com/100732722/235226476-46e09f84-06c8-484d-ba87-ee655add74af.png)

SORT BY sales in descending order...

![Popular Coffee - Sort](https://user-images.githubusercontent.com/100732722/235479827-610cfa14-9cb7-454e-afd2-73eb65043528.png)

Considering the data is now sorted from MOST popular to LEAST popular coffee drink by sales, I will pull the most popular drink via the SAMPLE tool...

![Popular Coffee - Sample](https://user-images.githubusercontent.com/100732722/235480384-da64085d-4a77-4d06-ae39-c5cd78ef976a.png)

**...Now it is time to repeat the same process as we did for Coffee, but for Tea...**

![Tea Flow](https://user-images.githubusercontent.com/100732722/235483411-52e5a928-6995-4060-a9ae-2caeb126f3bb.png)

![Most Popular Tea](https://user-images.githubusercontent.com/100732722/235483762-7562cc45-026e-4145-bf61-8b8731646fc7.png)

...

...At this point we have found the answer to which state consumes the most amount of Regular/Decaf Coffee & Tea... it is time to put the answers together into a presentable format...

I decided to create new columns named after the result in which we were looking for...

*Biggest consumer of regular coffee*
![Biggest Consumer of Regular Coffee - Formula](https://user-images.githubusercontent.com/100732722/235484729-30d610c6-4f09-40fd-8199-357daf8fdc3d.png)

*Biggest consumer of decaf coffee*
![Biggest Consumer of Decaf Coffee - Formula](https://user-images.githubusercontent.com/100732722/235484863-2a569be6-e34c-4c1c-bace-f940171ffefc.png)

*Most popular type of coffee drink*
![Most Popular Coffee Drink - Formula](https://user-images.githubusercontent.com/100732722/235485085-4274e25c-6f3e-4532-90fc-1a1bb86a4a13.png)

*Biggest consumer of regular tea*
![Biggest Consumer of Regular Tea - Formula](https://user-images.githubusercontent.com/100732722/235484929-95e4fec2-d8bc-4be8-9b0c-4bfa3d983cd8.png)

*Biggest consumer of decaf tea*
![Biggest Consumer of Decaf Tea - Formula](https://user-images.githubusercontent.com/100732722/235485112-c474f175-92be-4924-aa0e-8a9087041d9d.png)

*Most popular type of tea drink*
![Most Popular Tea - Formula](https://user-images.githubusercontent.com/100732722/235487264-b23518ac-41c7-421f-9c65-eb8a0816d7db.png)

...

Once the answers to the questions have been individualized, I used the UNION tool to bring them all together by position...

![Union](https://user-images.githubusercontent.com/100732722/235485647-03d7be62-bae2-4231-be91-64886094d10e.png)

Use the SELECT tool to get rid of any unnecessary data...

![Select - Final](https://user-images.githubusercontent.com/100732722/235485843-4171e197-8075-45e1-8459-e0b074e0e9d8.png)

Ka-Pow!...We have officially prepped raw data for further analysis to determine whether coffee or tea is more popular than the other in the U.S.

Here are my personal results:
![Personal Results - Browse](https://user-images.githubusercontent.com/100732722/235486668-d1436729-1029-47b5-b209-6e5f106d766d.png)

Here are the results from Alteryx Academy:
![Challenge Solution](https://user-images.githubusercontent.com/100732722/235486743-bae342a4-c91e-4c70-83cf-e7d1b309128b.png)
