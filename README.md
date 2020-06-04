# Workload generation for Web services with workload characterization and workload modelling
1. Download the google cluster data. 
2. Install the PSPP Statistical tool - https://archive.org/download/pspp-setup/pspp-setup.zip
3. Load the Google trace file into the PSPP statistical tool to analyze the statistical information about the real workload. 
4. Create a client and server Instance in Amazon Web Service according to specifications.
5. In both these instances, install Apache Ant and Java as prerequisites to run the statistical tool Faban. 
   Apache Ant:  https://ant.apache.org/bindownload.cgi
   Java: https://www.oracle.com/java/technologies/javase-jdk14-downloads.html#license-lightbox
6. Install Faban in both the client and server instance. 
7. Set $JAVA_HOME and $FABAN_HOME. 
8. The faban driver


