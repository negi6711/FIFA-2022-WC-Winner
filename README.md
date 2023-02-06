# FIFA-2022-WC-Winner
I have been eagerly anticipating this World Cup for a while now. I have thoroughly enjoyed the time I have spent working on this Predictive Machine Learning project, as it has provided me with valuable learning opportunities, the chance to engage in extensive research, and the chance to put my newfound knowledge into practice.
It consist of two kaggle dataset consisting of all the results of the friendlies as well as competitive matches since 2018 WC (https://www.kaggle.com/datasets/martj42/international-football-results-from-1872-to-2017) & Fifa world ranking (https://www.kaggle.com/datasets/cashncarry/fifaworldranking)
During the data preperation I've only taken data from the last worldcup to the last match before 2022 WC starts.
The most important part of this project is to get the features that have predictive power to empower the result of a football match like
-Past game points made
-Past goals scored and suffered
-The importance of game (friendly or not)
-Rank of the teams
-Rank increasement of the teams
-Goals made and suffered by ranking faced
In order to create the features, I've separated the dataset in home team's and away team's dataset, unify them and calculate the past game values. After that, I've separated again and merge them, retrieving the original dataset. This proccess optimized the creation of the features.
Based on feature enginnering and data analysis of the data about which features are correlated and have more predictive power, final features are:
-rank_dif
-goals_dif
-goals_dif_l5
-goals_suf_dif
-goals_suf_dif_l5
-dif_rank_agst
-dif_rank_agst_l5
-goals_per_ranking_dif
-dif_points_rank
-dif_points_rank_l5
-is_friendly

Now that I've have a database ready and with columns with predictive power, I can start modelling.
After testing 3 models: Random Forest, Gradient Boosting & XGBoost, I saw that Gradient Boosting did the best for the dataset even though Random Forest was a bit better. It underfit though.
Also there wasn't that big of a difference between XGBoost & Gradient Boosting Clasifier and that's why I went with GBC.
After the model building, I just got the data of the matches from the Wikipedia and Fixtures.
One more logic I'll be using is that I'll be taking all stats like ranking, goal_scored_l5,goals_conceded_l5 from the last match. i.e if Portugal last match before WC was agianst Brazil their all stats will be taken upto that match.
I also store the team's points at the group and its probabilities of win in each game. The mean of team's wins probabilities will be used as tiebreaker when two teams have the same number of points.
Since the model simulates if team 1 will win or not win, it's needed to create some criteria to define a draw. Also, since we have not home advantage at World Cup, the idea is to predict game two times, changing team 1 and team 2. The team with the highest mean of probabilities will be assigned as winner. At the group phase, if "home team" win as team 1 and loses as team 2, or if "home team" win as team 2 and loses at team 1, there will be assigned a draw in that match.
For the WC simulation initially I went with getting the required stats and then will be comparing features of both teams
About the first group games simulation:
-Not alot of crazy predictions. I think the teams who're predicted to advance, advanced out of group stage.
-Group B never saw a winner and that's still baffling as team like England is way better than other teams in the group.
About the R16, R8, Semi & Finals:
And that's the final simulation! Belgium has won the title! Hoping that my predictions are correct now.
It's nice to analyze too the possible upsets. Belgium passed against Germany. Spain - Brazil game is very tight, with Brazil passing by nearly ranking. The best game and the closest happens between Argentina and Brazil in SF, with Argentina passing with 1%. I think Belgium as finalist was the biggest upset of the simulation let alone winning the whole WC against ARGENTINA.



