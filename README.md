# Udacity Data Engineering Capstone

This project deals with criminal information from the City of São Paulo - Brazil. The information is provided by Kaggle (the links are in the notebook). The aim is to provide a solid and sanitized database for use in statistical and Business Inteligence analysis.


# Requirement
Kaggle datasets must be downloaded to a given directory. As a suggestion, that project files are mapped for a better structure as in the image below.
After download, the directory structure must be the same as listed below.

* data
 * crimes
   * BO_YEAR_*.csv
   * RDO_*.csv
 * properties
   * properati-BR-*.csv
   
   
## Choice of technology
Because the datasets are so large that python and pandas have trouble to processing, choosing Spark makes sense since datasets are not too big to have to use a big Hadoop cluster. The process can easily be performed locally on current computers.

Choosing to work with AWS S3 as a repository makes sense for its scalability and low cost. S3 has as query device, the AWS Athena, and a great integration with Redshift. This facilitates the consumer queries and surveys, that will do their analysis in the final result set.

## Future scenario

### Increases volume 100 times 
If the data volume increases 100 times, proper sizing of a Spark cluster can easily be done through AWS EMR.

### Periodic Update
For a daily update of the data, we can orchestrate Spark calls with AirFlow workflow.

### High data consumption
In case where there will be over 100 people consuming this data at the same time, we can use AWS Athena or Redshift as a way of distributing the data for consumption, and our Spark task writing directly to AWS S3.
