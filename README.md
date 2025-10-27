# MIST4610-Group-Project Group 4

**Team Members:**
1. Jake Cheong
2. Brian Kim
3. Bethel Mekuria
4. Eric Xu
5. Liam McKenna

# Problem Discription:
As a collective group, we built a relational data on the workings of a tennis management system. The central entity in the model is the _Team_ entity with each team representing many individual players in their respective partcipitating teams as well interlinking coaches, tournaments, match details, rankings, and conference details. This system is designed to accurately model the relationship between each entites. After populating each entitity with sample data we aim to simulate accurate and realistic tennis information. Ultimately, this database will serve as an analytical tool and a comprehensive management for evaluating the understanding the organization of tennis program.

# Data Model:

Explanation of data model:

Our model is structured off the collegiate tennis management system, with the Team _entity_ serving as the central component. Inside the _Team_ entity contains a one-to-one relationship between Coach, with a single coach assigned to a team and each team having a specific coach. The Coach entity itself also includes information such as first name, last name, expereince, years, and email.

Teams are also composed of many players, and players can represent different teams in different seasons. To portray this, we used a many-to-many relationship between _Team_ and _Player_ through the third entity: _TeamRoster_. The Player table also contains information such as first name, last name, gender, class year, nationality.

Teams compete in Tournaments and this is shown through the entity: _TournamentResults_ that links _Team_ and _Match_ through a many-to-many relationship beccause each tournament has multiple matches where teams and players participate. _Tournament_ include name, level, start date, end date.

The _Match_ entity holds details on round, player, and team. Since many players are in a match, a many-to-many relationship is used to connect _Match_ and _Player_ through _matchPLayer_. 


# Data Dictionary:

<img width="663" height="358" alt="Screenshot 2025-10-26 at 9 23 09 PM" src="https://github.com/user-attachments/assets/309b5032-509f-48b4-944d-3dee3ee18415" />

<img width="656" height="366" alt="Screenshot 2025-10-26 at 9 23 15 PM" src="https://github.com/user-attachments/assets/254964cc-4911-45a6-8984-397133dd8ab8" />

<img width="674" height="538" alt="Screenshot 2025-10-26 at 9 23 30 PM" src="https://github.com/user-attachments/assets/609514f8-8133-4d37-a170-6dd41cdf1c3c" />

<img width="668" height="328" alt="Screenshot 2025-10-26 at 9 23 36 PM" src="https://github.com/user-attachments/assets/163d42f8-efd3-4fac-a01f-a746d1aa6333" />

<img width="691" height="664" alt="Screenshot 2025-10-26 at 9 23 52 PM" src="https://github.com/user-attachments/assets/efc78f11-181a-4e31-9a1c-85033d2cb0a0" />

<img width="693" height="625" alt="Screenshot 2025-10-26 at 9 24 02 PM" src="https://github.com/user-attachments/assets/4e7f1e52-9d72-432b-854c-2e574a9857e0" />

<img width="660" height="390" alt="Screenshot 2025-10-26 at 9 24 10 PM" src="https://github.com/user-attachments/assets/84ea10fd-c242-4487-879b-754b7ba8b6b0" />

<img width="689" height="318" alt="Screenshot 2025-10-26 at 9 24 15 PM" src="https://github.com/user-attachments/assets/58001ae6-59b2-4dde-b7f7-efd2e94310b2" />

# Queries: 
**QUERY 1**: Lists each player’s first name, last name, age, and the college team they play for. It connects the player information with their team roster to show which college team each player represents.

<img width="1119" height="766" alt="Screenshot 2025-10-26 at 6 52 28 PM" src="https://github.com/user-attachments/assets/17310f76-6caa-4106-865d-57f343b8cf48" />

Query 1 allows managers to quickly verify player eligibility and team rosters by showing each player’s age along with which college they are affiliated with. Managers would need this information when registering teams for tournaments, especially ones with strict age requirements and that require age verification before the player is allowed to participate. Having all of this information in one place would reduce the amount of time managers spend verifying player information. 


**Query 2:** Lists the date and winner of all tournaments that took place in Texas. It uses RegEXP to find any tournament that contains “TX” in its name.

<img width="791" height="372" alt="Screenshot 2025-10-26 at 7 04 48 PM" src="https://github.com/user-attachments/assets/16c00c96-66ee-4728-80e1-32e945785d9e" />

Query 2 allows managers to evaluate the success of hosting a tournament in Texas by using historical data. This would help them determine whether to schedule future tournaments in Texas or not based on the quality of teams that have won there, and compare the Texas venue performance against tournaments held in other states to make future location decisions.

**Query 3:** Lists the team’s ID, college name, and division of teams that belong to the “SEC” conference. It connects the team and conference tables to filter only teams whose conference classification is “SEC” and then sorts the results alphabetically by college name.

<img width="627" height="375" alt="image" src="https://github.com/user-attachments/assets/7339b56f-f1f3-47cc-83eb-3c467ec0c79d" />

Query 3 helps managers to quickly view all teams associated with the SEC conference. Managers can use this information to schedule matches within the conference and coordinate conference level events or tournaments. It also allows them to analyze how many and which teams fall under a particular classification, such as the SEC or ACC.

**Query 4:** Lists all players from UGA, showing each player’s ID, name, age, and gender. It connects the team, teamRoster, and player tables to identify which players belong to the University of Georgia’s tennis team.

<img width="652" height="470" alt="image" src="https://github.com/user-attachments/assets/bc022a01-e0ee-4eb2-94d5-2ea0effea238" />

Query 4 allows managers to view the roster of a specific school’s team like the University of Georgia. It helps them verify team rosters and player details before tournaments and ensures compliance with age or gender eligibility rules. It also helps generate school specific reports.


**Query 5:** Lists the first name, last name, and age of all players whose age is above the average age of all players in the system. It first calculates the average age across all players, then filters out the players who are younger than the average age. The results are sorted in descending order.

<img width="1148" height="758" alt="Screenshot 2025-10-26 at 7 21 47 PM" src="https://github.com/user-attachments/assets/c2e1fac2-fc0d-45f0-a73f-f100d5939dec" />

Query 5 allows managers to identify players who may have a competitive advantage due to their physical maturity level or having more experience compared to other players. Coaches might rely on the ones that are older and are more experienced to make them the team captain or help with training younger teammates. Managers might also use this information to make sure that competition remains fair and balanced during matches and tournaments.


**Query 6:** Lists the player ID, first name, and last name of all players who have competed in matches but do not have a ranking in the system. It joins player information with their match participation records, then uses a subquery to verify that each player does not have an entry in the Ranking table. The results are sorted alphabetically by players' last name, then first name. 

<img width="928" height="569" alt="Screenshot 2025-10-26 at 7 23 38 PM" src="https://github.com/user-attachments/assets/d8d197b4-79ec-431e-b06c-b45d0d91c302" />

Query 6 allows managers to identify competitors who do not have rankings. Rankings are important in determining eligibility for tournaments, so this query helps managers catch and fix gaps in the system.


**Query 7:** Identifies which team has participated in the most tournaments. It joins team information with tournament results, groups the data by team, and counts how many tournaments each team entered. The results are sorted in descending order, and only the top team with maximum participation is shown.

<img width="866" height="416" alt="Screenshot 2025-10-26 at 7 23 55 PM" src="https://github.com/user-attachments/assets/8a702271-c52c-4dc3-87d2-2759b98f8155" />

Query 7 allows managers to identify and recognize the most committed and active team that has participated in the most tournaments. This is useful for award programs and also attracting sponsors who want to partner with highly visible teams. Managers can also use this data to allocate resources more efficiently, as teams that participate more actively may need additional support with expenses like traveling and tennis equipment.


**Query 8:** lists all college teams that have not participated in any tournaments. It compares the team table with the tournamentResult table and returns only teams that do not have any matching tournament entries. The results are sorted alphabetically by the college's name

<img width="625" height="500" alt="image" src="https://github.com/user-attachments/assets/04e42e84-a577-4fa8-98e2-a3e1d5efbfee" />

Query 8 helps managers and tournament organizers identify which teams have not yet competed in any tournaments. This would allow for outreach and engagement efforts to make sure each team has the opportunity to join upcoming events. It also helps with scheduling and planning because can target these inactive teams for invitations or reminders.

**Query 9:**calculates the average player age and the total roster size for each college team. It joins the team, teamRoster, and player tables to combine team and player data. It groups the results by each college, and sorts them from the oldest average team to the youngest.

<img width="787" height="572" alt="image" src="https://github.com/user-attachments/assets/0e3e1862-0396-4ae7-a979-4e1d7f7be954" />

Query 9 helps managers see the age composition and roster size of each team. This helps managers identify whether a team is mostly experienced upperclassmen, who are seasoned and my bring leadership or developing younger players. The roster size data allows them to assess player availability, which helps ensure that each team has enough athletes to cover tournaments and avoid burnout.
# Database information:
