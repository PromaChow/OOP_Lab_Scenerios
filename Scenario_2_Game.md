
Note: Read the scenario and design it.

Design a program for a small sports tournament tracker with the following requirements:

Each **Team** has a unique name and contains a collection (ArrayList) of **Player** objects. A **Player** has two attributes: a name and a skill rating. A team does not store its overall strength directly; instead, the team’s strength is always calculated dynamically as the average skill rating of its current players. This value must be recalculated whenever a player is added to or removed from the team.

Matches are played between two teams and recorded as **MatchResult** objects. Each MatchResult stores references to the two teams involved and their respective scores. A team must not store its win, loss, or draw counts as separate fields. Instead, its performance record must always be derived by scanning all MatchResult objects in which the team participated.

There are three types of teams, each following a different scoring rule under a common ranking system:

* A **ProfessionalTeam** earns 3 points for a win and 1 point for a draw.
* An **AmateurTeam** earns 2 points for a win and 1 point for a draw.
* A **YouthTeam** earns 2 points for a win, 1 point for a draw, and receives an additional bonus point in any match where it scores 3 or more goals, regardless of the match outcome.

Each team must be able to calculate its total points by applying its specific scoring rule to all its matches. It must also be able to display its details, including team name, current roster strength, and total points.

A **LeagueManager** class must manage the system. It should:

* Store all teams in an ArrayList, ensuring that no two teams have the same name.
* Store all MatchResult objects in a separate ArrayList.
* Allow recording a match only if both participating teams already exist in the system.
* Generate a final ranking of all teams sorted in descending order of total points. If two teams have equal points, the tie must be broken using their average roster strength (higher strength ranks higher).

The program must demonstrate:

* At least five teams across all three tiers.
* At least six matches played among them.
* At least one tie in total points that is resolved using the strength-based tiebreaker.
* A final ranking output showing all teams in order.



Rubrics:

| Criteria | Marks |
| --- | --- |
| 1. Use of All Principles of OOP | 3 |
| 2. Implementation of All Required Classes | 4 |
| 3. Logical Correctness / Functionality | 3 |
