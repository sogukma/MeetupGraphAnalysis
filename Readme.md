# Meetup Graph Analysis
## This is the technical documentation that helps to set up the Meetup graph analysis tool, which Malik developed as part of his Bachelor thesis.

**Currently, the following files are included:**
- **Data Collection.ipynb:** Gathers, filters new data about groups, events and RSVPs and transfers them to CSV files.
- **Graph Creation.ipynb:** Creates graph databases in neo4j using the data from the created CSV files about groups, events and RSVPs.
- **Querying Trends.ipynb:** Brings new insights into current trends in terms of locations, topics and events.
- **Behaviour analysis of People and Groups.ipynb:** Behavioural analyses of groups and people are carried out here. In doing so, among other things competitors are recognized.
- **Command Central.ipynb:** Has Cypher-queries for the administration of the database.
- **all CSV files with gathered data**

## System components
- Jupyter Notebook
- neo4j (username:"neo4j"; password="1")
- both are running locally on Docker

## Docker configuration
### Run Jupyter on Docker:
1.	Get Jupyter Notebook from DockerHub 
  ~~~~
  docker pull sogukma/meetup_analysis:meetup_jupyter
  ~~~~
2.	Run Jupyter Notebook with the following command
  ~~~~
  docker run --name {container_name} -p 8888:8888 -v ~/notebooks:/home/jovyan sogukma/meetup_analysis:meetup_jupyter
  ~~~~
  - This will also create a "notebooks" folder in your computer's main directory.
3.	Download the ZIP file with the Jupyter Notebook files of this project:
  - Link: **https://github.com/sogukma/MeetupGraphAnalysis**
  - Unpack it and copy the content (except the .gitignore file) into the newly created "notebooks" folder.
4.	Access the program by typing the following URI into your browser:
  - **192.168.99.100:8888/?token=xxxxxxx**
  - Replace **xxxxxx** with the token given in the Docker window.
5.	Now you are able to use the Jupyter files. Since the database has not yet been set up, you cannot perform any analyses with it.
6. Optional: To enable codefolding in Jupyter Notebook, enter these commands in Docker:
  ~~~~
  docker exec {container_name} jupyter contrib nbextension install --user
  ~~~~
  ~~~~
  docker exec {container_name} jupyter nbextensions_configurator enable --user
  ~~~~
 - Then go to **192.168.99.100:8888/nbextensions** in your browser and activate **"codefolding"** there.
### Run neo4j on Docker:
1.	Get neo4j (with APOC) from DockerHub
  ~~~~
  docker pull discsports/neo4j-apoc
  ~~~~
2.	Run neo4j with the following command
  ~~~~
  docker run -p 7474:7474 -p 7687:7687 --name {container_name} --env=NEO4J_ACCEPT_LICENSE_AGREEMENT=yes discsports/neo4j-apoc
  ~~~~
3. Enter the link **http://192.168.99.100:7474/browser/** in your browser.
4. Enter the initial credentials
  * url: **bolt://192.168.99.100:7687**
  * username: **neo4j** 
  * password: **neo4j**
5. Now you will be prompted to change your password. Change it to **"1"**.
6. Now go back to the Jupyter notebook and open the file **Graph Creation.ipynb**. Follow the instructions there to create the graph database.
7. Now you are able to perform analyses with the tool. For this you can use the Jupyter files **Behaviour analysis of People and Groups.ipynb** and **Querying Trends.ipynb**.
### Note: All necessary drivers for Jupyter Notebook and neo4j are already pre-installed.

## Next steps
If Jupyter Notebook and neo4j have been successfully installed, they can be used for the analysis. Among other things, the following additional actions can be performed on them:
1. Start **DataCollection.ipynb** and follow the instructions step by step. This will create new CSV files on your local storage based on new data.
2. Start **GraphCreation.ipynb** and follow the instructions step by step. This will create a graph database from the previously created CSV files.
3. Now you are able to perform analyses with the tool. For this you can use the Jupyter files **Behaviour analysis of People and Groups.ipynb** and **Querying Trends.ipynb**.
