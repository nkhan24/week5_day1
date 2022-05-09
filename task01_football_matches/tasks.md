# Football Matches - Tasks

Each of the questions/tasks below can be answered using a `SELECT` query. When you find a solution copy it into the code block under the question before pushing your solution to GitHub.

1) Find all the matches from 2017.

```sql
<!-- Copy solution here -->
SELECT * FROM matches WHERE season = '2017';

```

2) Find all the matches featuring Barcelona.

```sql
<!-- Copy solution here -->
SELECT * FROM matches WHERE hometeam = 'Barcelona' OR awayteam = 'Barcelona';

```

3) What are the names of the Scottish divisions included?

```sql
<!-- Copy solution here -->
SELECT name FROM divisions WHERE country = 'Scotland'; 

```

4) Find the division code for the Bundesliga. Use that code to find out how many matches Freiburg have played in the Bundesliga since the data started being collected.

```sql
<!-- Copy solution here -->
SELECT COUNT(id) FROM matches WHERE division_code = 'D1' AND (hometeam = 'Freiburg' OR awayteam = 'Freiburg');
374
```

5) Find the unique names of the teams which include the word "City" in their name (as entered in the database)

```sql
<!-- Copy solution here -->
SELECT DISTINCT hometeam FROM matches WHERE hometeam like '%City';
4 teams
```

6) How many different teams have played in matches recorded in a French division?

```sql
<!-- Copy solution here -->
SELECT COUNT(DISTINCT hometeam) FROM matches WHERE division_code = 'F1' OR division_code = 'F2';
61
```

7) Have Huddersfield played Swansea in the period covered?

```sql
<!-- Copy solution here -->
SELECT*FROM matches WHERE (hometeam = 'Huddersfield' AND awayteam = 'Swansea');
Yes they have
```

8) How many draws were there in the Eredivisie between 2010 and 2015?

```sql
<!-- Copy solution here -->
SELECT COUNT(ftr) FROM matches WHERE (ftr = 'D') AND (season > 2009 AND season < 2016) AND division_code = 'N
1';
431
```

9) Select the matches played in the Premier League in order of total goals scored from highest to lowest. Where there is a tie the match with more home goals should come first.

```sql
<!-- Copy solution here -->
SELECT COUNT(ftr) FROM matches WHERE (ftr = 'D') AND (season > 2009 AND season < 2016) AND division_code = 'N1';

```

10) In which division and which season were the most goals scored?

```sql
<!-- Copy solution here -->
SELECT SUM(fthg + ftag), season, division_code FROM matches GROUP BY division_code, season ORDER BY SUM DESC LIMIT 1;
EC

```

### Useful Resources

- [Filtering results](https://www.w3schools.com/sql/sql_where.asp)
- [Ordering results](https://www.w3schools.com/sql/sql_orderby.asp)
- [Grouping results](https://www.w3schools.com/sql/sql_groupby.asp)
