# AB-Testing
Data exploration and analytics over AB testing on the Cookie Cats, a hugely popular mobile puzzle game developed by Tactile Entertainment. 
# Problem
Where should the gates be placed?
# Solution
In this project, we're going to analyze an AB-test where we moved the first gate in Cookie Cats from level 30 -control- to level 40 -test-. In particular, we will look at the impact on player retention.
# Data explore and visualization
We did first some data exploration to understand a bit more of the data set.

There are 90189 lines of data and 5 columns.

![image](https://user-images.githubusercontent.com/96295365/154859206-583828a5-3e78-40df-bc17-7a6266fc691e.png)

![image](https://user-images.githubusercontent.com/96295365/154859360-b4936f31-be2a-440f-a887-0cb556f1a7c7.png)

We look into how many kinds of data are in each columns.

![image](https://user-images.githubusercontent.com/96295365/154859431-6425905b-88a1-4efe-8850-8be0d2a04a68.png)

There are no missing data in the data set.

![image](https://user-images.githubusercontent.com/96295365/154859492-d5c558d2-c30f-4395-9a42-233c01bb609e.png)

We want to know how many data are in each test, and the resouls shows the are about the same amount.

![image](https://user-images.githubusercontent.com/96295365/154860100-208ab406-9e71-4639-9791-3c41f2017113.png)

![image](https://user-images.githubusercontent.com/96295365/154860082-74a80628-4e5c-47f5-8e49-1a828b8264d2.png)

later on we looked into the average number of game rounds played by the player during the first week after installation for each version. 

![image](https://user-images.githubusercontent.com/96295365/154860184-fee3ac8c-28e4-4897-94ef-68f01253c6b8.png)

Compare the 2 game version (Gate 30 and Gate 40) in 2 retentions (1 day and 7 days) in pie chart.

Gate 30 & retentions 1 day

![image](https://user-images.githubusercontent.com/96295365/154860454-330b4cdb-263d-4b99-97fe-ad63622ab4e4.png)

Gate 30 & retentions 7 day

![image](https://user-images.githubusercontent.com/96295365/154860474-7057d541-fc92-4a2e-b241-694c63dc25f0.png)

Gate 40 & retentions 1 day

![image](https://user-images.githubusercontent.com/96295365/154860485-0aa6cb66-a757-4fc8-987f-abcee10f9232.png)

Gate 40 & retentions 7 day

![image](https://user-images.githubusercontent.com/96295365/154860505-2af90c62-dacb-4cbd-bc84-62a3e8edbb86.png)

Compare the 2 game version (Gate 30 and Gate 40) in 2 retentions (1 day and 7 days) in table.

![image](https://user-images.githubusercontent.com/96295365/154860566-178cf5e8-e606-4038-8df6-c8da268aad2e.png)

Learning from【DataCamp Project】Mobile Games A/B Testing at kaggle, we also looking into each version's distribution of players.

![image](https://user-images.githubusercontent.com/96295365/154860919-e26bf6d0-3be6-4ec8-8c3d-db514e7b008d.png)

![image](https://user-images.githubusercontent.com/96295365/154860946-dce6aacc-fbbb-4f1e-a34a-c3ec912d784b.png)



# Team
Asieh Mirzabagherian H. & 
Te-Hsin Tsai (Grace)
# Collaboration Type
Far distance via Slack, Trello, Colab and Github.
# colab link
https://colab.research.google.com/drive/1ogy2FdvZm5Hy1Ptw_duxXoZwU26i1Ozu?usp=sharing
