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

# Queries:

# Database information:
