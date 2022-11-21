### 1. Number of matches played per year of all the years in IPL.

 select  season as year ,count(season) as numberOfYearMatchOccur from matches group by season;

### 2. Number of matches won of all teams over all the years of IPL.

 select winner as teamWinner ,count(winner) numberOfMtachesWinByPerTeam  from matches group by winner ;


### 3. For the year 2016 get the extra runs conceded per team.

 select batting_team as battingTeam ,sum(extra_runs) as getExtraRunsConcludedIn2016 from deliveries d  cross 
          join matches m where m.id=d.match_id and m.season=2016 group by batting_team;

### 4. For the year 2015 get the top economical bowlers.

   select bowler,sum(total_runs)/(count(bowler)/6.0) as economy from deliveries join matches where matches.id=deliveries.match_id and matches.season=2015     group by bowler  order by economy;


   
### 5 .  Create your own scenario.(the year 2015 get the extra runs conceded per team).


 select batting_team as battingTeam ,sum(extra_runs) as getExtraRunsConcludedIn2015 from deliveries d  cross 
          join matches m where m.id=d.match_id and m.season=2015 group by batting_team;
