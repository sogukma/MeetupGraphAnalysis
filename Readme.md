# Meetup Graph Analysis
## This is the project folder of the graph analysis about the Meetup network, which Malik performs as part of his bachelor thesis.

**Currently, the following files are included:**
- **Data Collection.ipynb:** Gathers, filters data about groups, events and RSVPs and transfers them to CSV files.
- **all CSV files with gathered data**
- **Graph Creation.ipynb:** Creates graph databases in neo4j using the data from the created CSV files about groups, events and RSVPs (currently it only works on localhost)
- **Querying Trends.ipynb:**: Brings new insights into current trends regarding localities, topics and events.
- **Behaviour analysis of People and Groups.ipynb:** Behavioural analyses of groups and people are carried out here. Thereby among other things competitors are recognized.
- **Command Central.ipynb:** Has Cypher-querys for the administration of the database.

## Instruction
1. Start **DataCollection.ipynb** and follow the instructions step by step. This will create new CSV files on your local storage.
2. Start **GraphCreation.ipynb** and follow the instructions step by step. This will create a graph database from the previously created CSV files.
3. Now you can use **QueryingTrends.ipynb**  and **QueryingOracleGroups.ipynb** to retrieve data from the graph database using queries. don't forget to open the database connection before.
## System requirements
- Jupyter environment
- required libraries (will be specified soon)
- neo4j database
### coming soon:
- Docker configuration
