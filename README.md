# AB-Testing
This project is a data analytics with AB testing on the Cookie Cats, a popular mobile puzzle game developed by Tactile Entertainment. Variations of AB testing are the different Gates in level 30 and level 40. In the provided dataset by  [MÜRŞIDE YARKIN](https://www.kaggle.com/mursideyarkin/mobile-games-ab-testing-with-cookie-cats/notebook), the first gate in Cookie Cats is moved from level 30 -control- to level 40 -test- for exploring the impact on player retention. When a player installed the game, he or she was randomly assigned to either gate_30 or gate_40.

## Goal
Finding out "Where should the gates be placed?"

![Gates Picture](https://github.com/AsiMrz/AB-Testing/blob/507755ce9d0c8b0abbf3ee3d16a55f3139f84fa0/cc_gates.png)

## Process and Pipeline
During the process, We analyze the player retentions 
1. Data exploration
2. Data Visualization
3. Bootstrapping
4. T-test
(Picture)

## Data Exploration and Visualisation
Since the provided Dataset did not need to be cleaned or any other extra work, we started straightly with Data Exploration.
Meanwhile, we could learn a bit more about the data set.

### Some General Info:

The Dataset contains 90189 lines of data and 5 columns.

![image](https://user-images.githubusercontent.com/96295365/154859206-583828a5-3e78-40df-bc17-7a6266fc691e.png)

![image](https://user-images.githubusercontent.com/96295365/154859360-b4936f31-be2a-440f-a887-0cb556f1a7c7.png)

**Data types:** We look into how many kinds of data are in each column.

![image](https://user-images.githubusercontent.com/96295365/154859431-6425905b-88a1-4efe-8850-8be0d2a04a68.png)

There are **no missing data** in the data set.

![image](https://user-images.githubusercontent.com/96295365/154859492-d5c558d2-c30f-4395-9a42-233c01bb609e.png)

Since the test will be on the comparison of two gates, we **compare the number of users** in both. As the results show they are about the same amount.

![image](https://user-images.githubusercontent.com/96295365/154860100-208ab406-9e71-4639-9791-3c41f2017113.png)

![image](https://user-images.githubusercontent.com/96295365/154860082-74a80628-4e5c-47f5-8e49-1a828b8264d2.png)

Later on, we looked into the average number of game-rounds played by the player during the **first week** after installation for each version of gates. 

![image](https://user-images.githubusercontent.com/96295365/154860184-fee3ac8c-28e4-4897-94ef-68f01253c6b8.png)

**The comparison of the 2 game version (Gate 30 and Gate 40) in 2 retentions (1 day and 7 days)**

Gate 30 & retentions 1 day 
![image](https://user-images.githubusercontent.com/96295365/154860454-330b4cdb-263d-4b99-97fe-ad63622ab4e4.png)
Gate 30 & retentions 7 day
![image](https://user-images.githubusercontent.com/96295365/154860474-7057d541-fc92-4a2e-b241-694c63dc25f0.png)

Gate 40 & retentions 1 day
![image](https://user-images.githubusercontent.com/96295365/154860485-0aa6cb66-a757-4fc8-987f-abcee10f9232.png)

Gate 40 & retentions 7 day
![image](https://user-images.githubusercontent.com/96295365/154860505-2af90c62-dacb-4cbd-bc84-62a3e8edbb86.png)

As it is schown in this table, we can see there a slight difference between the percentage of the users who came back after one day and one week in different gates.

![image](https://user-images.githubusercontent.com/96295365/154860566-178cf5e8-e606-4038-8df6-c8da268aad2e.png)

**The distribution of game rounds** 
Learning from【DataCamp Project】Mobile Games A/B Testing at kaggle, we also looking into each version's distribution of players. In the plot below we can see that some players install the game but then never play it (0 game rounds).

![image](https://user-images.githubusercontent.com/96295365/154860919-e26bf6d0-3be6-4ec8-8c3d-db514e7b008d.png)

![image](https://user-images.githubusercontent.com/96295365/154860946-dce6aacc-fbbb-4f1e-a34a-c3ec912d784b.png)

We explored the user behavior with campring the percentage of each version's game rounds times.

Gate 30's player game rounds times

![image](https://user-images.githubusercontent.com/96295365/154861093-55c459e6-cdd7-4fc1-8440-32a21654e121.png)

Gate 40's player game rounds times

![image](https://user-images.githubusercontent.com/96295365/154861116-5b8565fd-bafc-4daf-a503-3620dd0ff1b0.png)

## Sampling by Bootstraping 
**Definition:** The basic idea of bootstrapping is that inference about a population from sample data (sample → population) can be modelled by resampling the sample data and performing inference about a sample from resampled data (resampled → sample). In bootstrap-resamples, the 'population' is in fact the sample, and this is known; hence the quality of inference of the 'true' sample from resampled data (resampled → sample) is measurable. (Wikipedia)

      `boot_1d = []
       boot_7d = []
       for i in range(500):
            boot_mean_1 = df.sample(frac=1, replace=True).groupby('version')['retention_1'].mean()
            boot_mean_7 = df.sample(frac=1, replace=True).groupby('version')['retention_7'].mean()
            boot_1d.append(boot_mean_1)
            boot_7d.append(boot_mean_7)`
    
Here, we define a loop for making two separate random list of the bootstrapped means for each A/B group: the first day retention and the seventh retention.

## AB Testing
The kernel density estimate plot of the bootstrap distributions

         `fig, (ax1,ax2) = plt.subplots(1, 2, sharey=True, figsize=(13,5))

           boot_1d.plot.kde(ax=ax1)
           ax1.set_xlabel("retantion rate",size=12)
           ax1.set_ylabel("number of sample",size=12)
           ax1.set_title("1 day retention rate distribution", fontweight="bold",size=14)
           boot_7d.plot.kde(ax=ax2)
           ax2.set_xlabel("retantion rate",size=12)
           ax2.set_title("7 days retention rate distribution", fontweight="bold",size=14)
           plt.show()`
           
![ABtesting](https://github.com/AsiMrz/AB-Testing/blob/7e735c93de97c6408c8d34bd5590b07bf5ae226c/ABtesting.jpg)

## Team
Asieh Mirzabagherian H. & 
Te-Hsin Tsai (Grace)

## Collaboration Type
Far distance via Slack, Trello, Colab and Github.

## colab link

