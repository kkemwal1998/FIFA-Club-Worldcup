Project Name: FIFA 2021

Objective: Ensuring 5Cs of Fifa database by performing data-Cleaning, data-visualisation, data-Clustering, data-Modeling and data-Insights

Brief Desciription: 
The project utilized an uncleaned version of the Kaggle FIFA dataset as its foundational data source. Through dedicated effort, I acquired a comprehensive understanding of the subject matter, delving into advanced data concepts over a substantial duration of time. This involved cleaning and modifying a vast array of information and crafting visual representationsn using Python Jupyer notebook aimed at facilitating detailed information about the players who played in the tournament. These efforts were directed towards enabling informed decision-making processes reflective of the players' key performance metrics and their net worth. In this project, I learned about:-
   a) Formatting, transformation, cleaning and standardization of data using Pandas,and Numpy.
   b) Hierarchical clustering: Performed hierarchical clustering of players information based on their wages using Scipy library with the help of Dendrogram.
   c) Data Modeling: Performed reggression analysis using Sklearn library by relationship between player's net worth as independent vairables and thier performance in the 
      match.
   d) Data Visualization: Performed data visualization of player's key performance metrics using Seaborn and Matplot libraries.
   e) Data insights: It consists of the conclusion drawn from each procedure in the process.
   
Problems Encountered:
During the progression of the data cleaning phase, I encountered a challenge while attempting to convert dataframe columns containing information pertaining to players' wages, values, and release clauses. Initially stored as strings, these columns featured currency symbols ('€'), as well as indicators for million ('M') and thousand ('K'). The specific issue arose during the conversion of figures located at the zeroth index position within the dataframe to float data type, resulting in an error. Subsequent research revealed that this issue is a prevalent occurrence within the realm of data analytics.

Solution: 
In order to address this issue, I followed a certain sequence of steps which were:-
  a) Eradication of string types from the figures like '€' using Python replace function. Eg: FIFA['Release Clause'].replace('€','',regex=True,inplace=True)
  b) Creating and applying functions to the columns in order to change their data type which can be seen as follows:
        i) Function -1:-
            def CONV(value):
              if 'K' in value:
                  k = value.replace('K',' ')
                  A = pd.to_numeric(k)
                  V1 = A*1000
                  return float(V1)
              
              elif 'M' in value:
                  m = value.replace('M',' ')
                  B = pd.to_numeric(m)
                  V2 = B*1000000
                  return float(V2)
              
              else:
                  return float(value)

        ii) Function -2:-
              FIFA['Value'] = DF_FIFA['Value'].apply(CONV)
              FIFA['Release Clause'] = DF_FIFA['Release Clause'].apply(CONV)
              FIFA['Wage'] = DF_FIFA['Wage'].apply(CONV)
              FIFA
