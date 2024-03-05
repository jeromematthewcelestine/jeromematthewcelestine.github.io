# Home advantage in Fantasy Premier League

<center><img src="images/home_adv_fpl_pts-1.png" alt="" width="500"/></center>

## Summary

It is conventional wisdom among FPL managers that home advantage exists in Fantasy Premier League (FPL). In this short note, I describe the steps I took to demonstrate that this is indeed the case.

* Home advantage exists in FPL: players score more FPL points when their team plays at home than when their team plays away.

* FPL home advantage disappeared entirely in the 2020/21 behind-closed-doors season, in line with team-level home advantage.

* Virtually all FPL point-scoring actions exhibit home advantage (positive actions occur more frequently at home, while negative actions occur more frequently away). FPL home advantage exists across all player positions (goalkeeper, defender, midfielder, and forward).

## Introduction

### Background on home advantage

Home advantage is the tendency of teams to perform better when playing at home than when playing away. Home advantage is well documented across many sports, including soccer, basketball, cricket, hockey, rugby, and American football, among others ([Chicago Booth Review](https://www.chicagobooth.edu/review/home-field-advantage-facts-and-fiction)).

In soccer, home advantage has been shown to exist in English, German, Italian, French, and Spanish leagues. Interestingly, home advantage was greatly reduced in the 2020/21 season, when many matches were played behind closed doors (i.e., without supporters in attendance) due to the COVID-19 pandemic.

### Background on Fantasy Premier League

Fantasy Premier League (FPL) is an online fantasy football, in which participants assemble virtual teams of real-life Premier League footballers and score points based on their performances in Premier League matches. Participants in FPL ("managers") select a squad of 15 players within a budget and choose 11 to play in each "gameweek". Points are scored for a variety of actions, including goals, assists, clean sheets, and bonus points. Managers can make transfers and substitutions to improve their teams throughout the season.

### Data

I use data on FPL from 2016/17 through 2022/23. I make use of [Vaastav Anand's FPL Historical Dataset](https://github.com/vaastav/Fantasy-Premier-League).

I also use data on match results from <http://www.football-data.co.uk>.

Finally, I use data on the number of managers per season from [allaboutfpl.com](https://allaboutfpl.com/2022/06/number-of-people-who-played-fpl-each-season-how-many-play-fpl/).

## Results

### Home advantage

<center><img src="images/home_adv_fpl_pts-1.png" alt="" width="500"/></center>

Home advantage exists in FPL: players score more FPL points when their team plays at home than when their team plays away. Interestingly, FPL home advantage was nonexistent in 2020/21 and much lower than normal in 2021/22. In other seasons, home advantage is reasonably consistent: players score an average of 3.3-4.5 FPL points when playing at home but score only an average of 2.7-3.2 when playing away.

Note that in the analysis above and in what follows, I exclude all player/gameweek observations where *Percent selected by* is less than 0.5%, i.e., where a player is selected by less than 0.5% of participating managers. I make this exclusion because FPL includes team's full squads, which typically include many players (such as  third choice goalkeepers and youth players) who register very few minutes of play, if any, during the course of a season. By excluding players with low selection rates, I attempt to exclude these low-minutes players. Additionally, players with low selection rates are not very relevant to FPL.

<center><img src="images/home_adv_by_position-1.png" alt="" width="500"/></center>

Home advantage exists for all four player positions (goalkeeper, defender, midfielder, and forward). 

### Sources of home advantage

FPL points are based on a variety of different point-scoring actions, listed in the table below.

| FPL point-scoring action           | Points        |
|:-----------------------------------|:--------------|
| Played more than 0 minutes         | 1             |
| Played more than 60 minutes        | 1             |
| Goal scored (GK / DEF / MID / FWD) | 6 / 6 / 5 / 4 |
| Assist                             | 3             |
| Every 2 goals conceded (GK / DEF)  | -1            |
| Clean sheet (GK / DEF / MID)       | 6 / 6 / 1     |
| Every 3 saves (GK)                 | 2             |
| Yellow card                        | -1            |
| Red card                           | -3            |
| Penalty saved (GK)                 | 5             |
| Penalty missed                     | -2            |

Source: <https://fantasy.premierleague.com/help/rules>

<center><img src="images/home_adv_fpl_actions-1.png" alt="" width="500"/></center>

Almost all point-scoring actions in FPL contribute to home advantage in total points. There are significant differences between home and away matches in all plotted point-scoring actions except for red cards. (I omit *Penalties missed* and *Penalties saved* from the plot on account of their rarity.)

Interestingly, the average number of minutes played (per gameweek/player) is slightly higher for home games than for away games. The difference is small, however---approximately 68.5 minutes for home games vs 67.75 minutes for away games---and is therefore unlikely to be meaningful for FPL points.

## Do FPL managers take advantage of home advantage?

<center><img src="images/mngr_selection_home_vs_away-1.png" alt="" width="500"/></center>

FPL managers are not more likely to select players with home fixtures than players with away fixtures.

Ideally, we would also account for the selection of players in managers' first team of 11 players each gameweek: every gameweek, a manager must choose 11 players from the squad of 15 to "play" in that gameweek (i.e., to score points for the team). The remaining four players sit on the manager's "bench" and will only score points if they are automatically substituted, which happens if one or more players from the first team of 11 fail to register a single minute of play that gameweek. My guess is that managers may account for home and away fixtures in the first 11 and bench decisions more so than in overall squad selection decisions. Managers are restricted to a single 'free' transfer each gameweek---subsequent transfers cost 4 points---meaning that squads change slowly over time and players are typically held by managers for multiple gameweeks (during which they will likely play both home and away matches). However, our FPL dataset includes data only on selection in the squad of 15 (our 'Percent selected by' variable) and not on selection in each manager's first 11 every gameweek.









