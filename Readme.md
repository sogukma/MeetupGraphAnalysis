This is the project folder of the graph analysis about the Meetup network, which Malik performs as part of his bachelor thesis.

Currently, the following files are included:
- dataCollection.ipynb: In this Notebook data about groups, events and RSVPs are gathered, filtered and transferred to CSV files.
- CSV files created by "dataCollection.ipynb"
- graphCreation.ipynb: This Notebook creates graph databases in neo4j using the data from the created CSV files about groups, events and RSVPs (currently it only works on localhost)
