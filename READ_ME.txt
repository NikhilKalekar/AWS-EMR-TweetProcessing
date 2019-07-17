
This project/Assignment is based on AWS EMR,

We need to import this project in Intellij IDE and then build it to get the JAR file
which you can run on your AWS EMR clusters.

Steps:

1. Import this project in Intellij (Dont forget to Install Spark and SBT plugins!)
(Check your build.sbt file for correct version of Spark and Scala.)

2. Go in folder: 
	TweetAnalysis -> src -> main -> scala

3. you will find my code there, build it to generate a JAR file
(go on View -> toolWindow -> sbt
On the “sbt projects” pane on the right, expand “sbttasks” and then go down 
to the “package” task and double click on it)

4. After creating a JAR( will be in Target -> Scala2.11 folder) upload it to you s3 bin on AWS (Along with the Datasets used for the Assignment/project ).
Then Create a cluster on AWS EMR.

5. Select "AddSteps" under the cluster

6. 	a. Step type: spark application
	b. Deploy Mode: Cluster
	c. SparkOptions: --class "ClassName of Project"
	d. AppLocation: Location of JAR on s3 bin
	e. Arguments: Arguments required to execute the project 
	              eg: InputPath Num_Iteration OutputPath 

7. Your code will be executed and will be saved in the output path (Which you must have
given in the arguments)