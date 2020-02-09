# Week 4 – Exercise 3 Relational Databases

_In [ODAT section 2.4](https://o-date.github.io/draft/book/arranging-and-storing-data-for-the-long-haul-databases.html) you will have read about different types of data recording formats (flat tables, csv files, JSON, relational databases). In your research as archaeologists you will mostly likely use desktop SQL programs like MS Access, since these are often freely available to University students. However, even if you only use these kinds of software with useful graphical user interfaces, it is still important to understand why these programs work and how they structure your data._ 

_If you wish to delve further into SQL, check out ODAT’s “[A Gentle Introduction to SQL](https://mybinder.org/v2/gh/o-date/sqlite/master?filepath=intro%20to%20sql.ipynb)” exercises._ 

For this exercise we will work from a relational database created for a PhD dissertation project by __Adrienne Frie__. The project, _Cultural Constructions of Nature: Animal representation and use in Early Iron Age southeastern Slovenia, which took a holistic approach to investigating the place of animals in the cultural world of the Dolenjska Hallstatt culture (c. 800-300 BCE) in SE Slovenia_. It was a multi-scalar analysis that addressed regional, contextual, and artifact-level patterning in animal depictions, comparing them to patterns in faunal remains to elucidate relationships between Early Iron Age humans and animals in southeastern Europe. This research was interdisciplinary, and took into account animal behavior, local environments, and the socioeconomic structures surrounding animal husbandry and other human-animal interactions. The results highlighted the multifaceted nature of human-animal relationships and the fundamental role played by visual culture in these interactions, where multiple complementary, competing, and even opposing ideologies and modes of practice existed simultaneously, and were negotiated through time. Please do not use this data without citing: “_Frie, Adrienne. 2017. Cultural Constructions of Nature: Animal representation and use in Early Iron Age southeastern Slovenia. Unpublished PhD dissertation. University of Wisconsin-Milwaukee._” 

1.	To begin, download the file “Frie-DissDatabase.accdb” from the Week 4 GitHub repository to a location on your local hard drive. 

2.	Open “Frie-DissDatabase.accdb.” Click on the “Database Tools” tab and click on “Relationships.” Note the different tables that are included in this database.  

![alt text](https://github.com/kgarstki/ANTH-641_Week-4/blob/master/Images/Image7.jpg)

3.	In a relational database each table represents a discrete category of information, which is then linked to one another by a common field. The lines between each table represent a connection between the two fields – this means that if you list “Brezje – Gomile” for a field in Table 1, that link will connect the record in Table 2 with the same entry in that field. These connections are sometimes referred to as hierarchies, because they represent different scales of information – artifacts might be at the lowest scale, while the site, region, or country might be the largest scale. 

4.	Click on the Site Form on the left side of the screen. A form records the same information as the equivalent Table. A form is just a different way to represent the data recorded in a table – some people find forms to be an easier way to view data in a table. In the Site Form, note what types of data are recorded here and why it would be important to record that information.

![alt text](https://github.com/kgarstki/ANTH-641_Week-4/blob/master/Images/Image8.jpg)

5. Next, open the Artifact Form as you did for the Site Form (just click OK when a box pops up). Click in the “Artifact Type” field. Then click the “Filter” button on the Home dashboard. Make sure ONLY the artifact type “Belt Plate” is selected. How many artifact records are left after you applied this filter? (Hint: look at the bottom right of the form). This number represents all of the belt plates recorded in this dataset.	

![alt text](https://github.com/kgarstki/ANTH-641_Week-4/blob/master/Images/Image9.png)

6. A benefit to organizing data in this relational form is that you can utilize data in multiple tables to identify patterns, while maintaining a “tidier” organization of different categories of data. Queries are simply more complex finds/filters – they allow you to specify which fields you want to assess, even from different tables at the same time (ex: how many women were buried with fibulae in this dataset). Let’s try to run a query on our data. Under the Create tab, click on Query Design. Add the tables, “Artifact,” “Site,” “Context,” “ArtifactDesc.” 

7.	Next, we’re going to choose which fields we’d like to include in our query. In the first column on the bottom of the screen, use the drop-down menu to choose the field Site.Site. This is indicating that we want the name of the site to show up in our query. Proceed to add the following fields to each of the next columns: Site.Date, Context.Tum#, Context.Grave#, Artifact.Species, Context.Published Gender, ArtifactDesc.ArtifactDesc. 

![alt text](https://github.com/kgarstki/ANTH-641_Week-4/blob/master/Images/Image10.png)

8.	Then click Run at the top “Design” tab. You will now find a new table that includes data from four different tables. You should have returned 576 records (the total number of artifacts in the study).

![alt text](https://github.com/kgarstki/ANTH-641_Week-4/blob/master/Images/Image11.png)

9.	Let’s narrow our query, to try and identify some meaningful patterns in the data. Go back to the query design at the bottom right side of the table. 

![alt text](https://github.com/kgarstki/ANTH-641_Week-4/blob/master/Images/Image12.png)

10.	We want to see all of the fibulae found in graves associated with female burials. First, in the ArtifactDesc column, type in “Fibula” in the row titled Criteria: Then, in the Published Gender column, type in Like “Female” in the Criteria: row. This limits our query to include only records where the artifact was a fibula and if the grave was designated as a Female, Probable Female, of Male and Female burial. You should come up with 19 records. Make sure to save your query. 

11.	Now try making your own query. Include fields that would be important for you to record, and use two or more data tables. When you’re done, save it as “YOURNAME_query.”

12.	There are even more tools that you can use to quantify different relationships between the data. Crosstabs are specialized queries to assess how often two variables co-occur. Let’s create one and look at how the animals that are represented on artifacts change depending on the gender designation of the associated burial. Begin a query as you did before and include the Species table and the Context table. 

13.	Click on the Crosstab icon in the Design tab at the top. In your first column at the bottom half of the page choose the Species.CommonName field. In the Crosstab: row, choose this field as “Row Heading” and Sort by “Ascending.” In the second column, choose Context.Published Gender and make it your “Column Heading” and “Descending.” The third column is also Species.CommonName – change the Total: row to say “Count,” and choose “Value” from the Crosstab: drop-down menu. For each crosstab, you need one Row, one Column, and one Value. Then hit the Run button. 

![alt text](https://github.com/kgarstki/ANTH-641_Week-4/blob/master/Images/Image13.png)

14.	Make sure to save your crosstab.

15.	Try making a crosstab on your own. When you’re done, save it with the name “YOURNAME_Crosstab.” 

16.	Save your updated Frie-DissDatabase_YOURNAME. Upload the updated database (with your new queries) in your ANTH 641_Week 4 repo. 

	






