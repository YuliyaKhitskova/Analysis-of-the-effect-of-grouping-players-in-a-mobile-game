# Analysis-of-the-effect-of-grouping-players-in-a-mobile-game
Player behavior when forming gaming alliances is examined. The influence of alliances on their spending and the possibility of changing pricing policies are discussed.
The attached file contains calculations for three hypotheses regarding player grouping.
The calculations include an exploratory data analysis: data types, empty values, descriptive statistics, and payment distribution.
Hypothesis 1: Most created groups are inactive.
Before conducting the analysis, the criteria for an active and inactive guild must be defined. The data frame data—guild_data and energy—were also combined before the calculations.
Based on the EDA and conditions, three options for understanding guild activity are considered.
1. "Soft option" (soft scenario).
2. "Moderate option" (moderate scenario).
3. "Hard option" (hard scenario).
"Soft" option (scenario 1 is the most lenient option; that is, any activity, even the smallest activity according to one of the assessment parameters, will be considered as activity). We assume that guilds with at least minimal activity can be transformed into more active ones. Active guilds are defined as those with more than one member and at least one condition from the activities listed in the data description is met (there are 10 parameters in total). Accordingly, we consider two conditions necessary. Groups were analyzed over a period of 90 days; we only have the group creation date. If we had the date of each activity, we could introduce a criterion that no more than (for example, 30 days (the number of days is arbitrary). This should be determined based on the data) have passed since the last activity.
1. "Moderate" activity (Scenario 2). We select all "non-military" indicators. According to the preliminary analysis, a large number of empty values ​​correspond to the "military" characteristics of the guild. Therefore, the guild must meet all of the following conditions:
1) n_added_characters > 1 – the number of added members AND
2) level > 1 OR n_missions_completed > 0 AND
3) n_talents > 0 AND
4) total_energy > 0
2. "Hard" activity mode (scenario 3).
Let's add the is_active_super_strong column, where TRUE means the guild is active. We'll add a very hard mode when scenario 2 (the "Moderate" mode) is fully met, plus we'll add conditions when the guild has completed three more military metrics (see the calculation file).
1) Started a war, i.e. n_times_flag_turned_on > 0.
2) mean_place > 0 (average rank in guild wars > 0; this seems to be a more lenient indicator than the guild's war rating (mean_rating), as it may be related to a single war.
3) n_seasons > 0 - the total number of war seasons in which more than 0 players participated.
Hypothesis 2: Players who purchase premium items create more active guilds, since by investing in the game, the user values ​​the effort invested more.
Hypothesis 3: If the first hypothesis is correct, should the cost of guild creation be significantly increased, including making it a premium item (costing real money)?
