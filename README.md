```python
import pandas as pd
from sqlalchemy import create_engine
```


```python
df = pd.read_excel("HR Data.xlsx")
```

### Connect to the MySQL database: 
Create a connection to your MySQL database using SQLAlchemy. 

Replace the placeholders with your MySQL database credentials:

```python
engine = create_engine('mysql+mysqlconnector://username:password@localhost:port/database')
```
### Write the DataFrame to the database: 
Use the `to_sql` method of the DataFrame to write the data into a MySQL table. Specify the table name and the database 

connection engine:

```python
table_name = 'your_table_name'
df.to_sql(table_name, con=engine, if_exists='replace', index=False)
```
In the above code, the if_exists parameter is set to 'replace', which means that if the table already exists, it will be replaced. You can change this behavior according to your needs.


```python
engine = create_engine('mysql+mysqlconnector://root:Tanui%401998@localhost:3306/humanresources')
```


```python
table_name = 'humanresource'
df.to_sql(table_name, con=engine, if_exists='replace', index=False)
```


```python
engine.dispose()
```
