# customer-feedback

*** For this project, I'm using Python and Pandas to clean and analyse customer feedback data. Understanding the emotion, sources, dates, and confidence scores in the data is my goal. A polished CSV file is produced at the end of the comprehensive data cleansing procedure, which is included within a Jupyter Notebook. I then use Pandas, NumPy, and Matplotlib in another Notebook to carry out various statistical studies. To efficiently depict trends connected to data sources and emotion distribution, visual representations like histograms and bar graphs are used. As part of my research, I am also investigating the analysis of daily confidence score patterns by drawing conclusions from the "DateTime" column.
	
	
Technologies  and tools used: 
	
• Jupyter Notebook : open-source software
• Python : code language written
• Pandas: data manipulation and library for Python

File name : 
feelings.ipynb

Data Source: https://www.kaggle.com/datasets/vishweshsalodkar/customer-feedback-dataset

	
### 1 - Import Statements and Libraries:  Import necessary libraries and tools for data cleaning process.
	
	
```
import pandas as pa
data = pd. read_csv("sentiment-analysis.csv", header=0) 
```

``` 
import pandas as pa
data = pd. read_csv("sentiment-analysis.csv", header=0)
```
	
### 2 - Split Data : To better organise the database, we divided it into columns with their respective names.
	
	
\``` 
	
data['Text, Sentiment, Source, Date/Time, User ID, Location, Confidence Score'].str.split(',')
	
data['Text, Sentiment, Source, Date/Time, User ID, Location, Confidence Score'].str.split(',',n=1)
	
data = data['Text, Sentiment, Source, Date/Time, User ID, Location, Confidence Score'].str.split(',',n=7, expand=True)
	
/```
	
	
### 3 - Rename method : For better syntax practise, I renamed column 'Date/Time' to 'DateTime' in this case.
	
	
	\``` 
	
	data.rename(columns={0:'Text',
	                           1:'Sentiment',
	                           2:'Source',
	                           3:'Date/Time',
	                           4:'User ID',
	                           5:'Location',
	                           6:'Confidence Score'}, inplace=True)
	data
	
	data.rename(columns = {'Date/Time':'DateTime'}, inplace = True)
	/```
	
	
	
	
	4 - Drop duplicates : method to remove duplicated rows, such no values like NaN additionally Specifying which row is providing this information.
	
	\``` 
	
	data.drop_duplicates()
	data.drop(labels=[96, 97], axis=0)
	/```
	
	5 - Save .CSV - Once the cleaning is finished, use the following procedure to save the changed DB .csv format for use in the next step.
	
	\``` 
	
	 data.to_csv('modified_feelings.csv', index=True)
	
	/```
