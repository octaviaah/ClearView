# Sequence diagrams

## Request tips
Resume tips are generated after the candidate uploads its resume. When doing so, the resume will be publish to RabbitMQ. The Resume Functions module will consume the message and send it to ClearViewAI for tips. Once the generation of tips is completed, the module will save the data in the database so the API can read the data and display the information to the candidate.
![](RequestTipsDiagram.png)

## Upload resume for anonymization 
When uploading a resume for anonymization, the resume will be send to the Message Broker, RabbitMQ. The message will then be consumed by the Resume Function module, which will send the original data uploaded by the candidate to the Blob storage that will prevent any changes to the original data, then send the uploaded data to the ClearViewAI module for anonymization. Once the anonymization process is completed, the Resume Module will write the anonymized data into the database.
![](Anonymization.png)

## Resume visualization
When a hiring manager wants to look at an anonymized resume, the resume is read directly from the database by ClearViewAPI.
![](ResumeVisualization.png)