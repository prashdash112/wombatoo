# WOMBATOO

#### Wombatoo is a python library which have the following features: 

1) Dataframe summary: Summary of dataframe in CSV format
2) Datacard: A single document having Timestamp, data owner, data source, data refresh cycle, data details, Intended use, data summary, ethical considerations, Recommendation and caveats. Some fields are pre-populated and the user can populate the rest to define a consice contract between data owner and data user.
3) Version: a local versioning tool using which a user can use to version small to medium datasets locally.
4) Report: A pandas-profiling report which can be saved in HTML, JSON and PDF formats.
5) Schema: A csv document having the schema of the dataset. Users can use it to validate the schema in the data pipeline. 

#### Installation

```
pip install wombatoo
```

```
from wombatoo import wombatoo
import pandas as pd

#reading df
df = pd.read_csv('base.csv')

if __name__ =="__main__":
    summary = wombatoo.metric_summary(df,path_to_save='summary.csv')
    datacard = wombatoo.datacard(df, path_to_save='Datacard_user.txt')
    version = wombatoo.version(df.head(5),file_name='fraud_bool', folder_path='./local_repo')
    report = wombatoo.generate_report(df=df.head(10), path_to_save='./Data_Profile_Report.html', pdf=False)
    schema = wombatoo.schema(df=df,path_to_save='schema.csv',show=1)
```
#### END