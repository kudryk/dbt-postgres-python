# Welcome to dbt-postgres-python 👋 do more with dbt

dbt-postgres-python adapter is the ✨easiest✨ way to run your [dbt Python models](https://docs.getdbt.com/docs/building-a-dbt-project/building-models/python-models).

Starting with dbt v1.3, you can now build your dbt models in Python. This leads to some cool use cases that was once difficult to build with SQL alone. Some examples are:

- Using Python stats libraries to calculate stats
- Building forecasts
- Building other predictive models such as classification and clustering

This is fantastic! BUT, there is still one issue though! There is no Python support for Postgres. dbt-postgres-python provides the best environment to run your Python models that works with Postgres!

## Project background

This project is based off the [dbt-fal](https://github.com/fal-ai/dbt-fal) project. Thank you [FAL-AI](https://github.com/fal-ai) for starting that project.
Priorities change and FAL-AI in April, 2024 chose to archive that project and focus their efforts elsewhere.

My team at work used dbt-fal, so that we could run python code on postgres. As dbt-fal was not being kept up-to-date with DBT,
I chose to pick up that project and bring it up-to-date. As a result, this project will only support Postgres going forward.
Support for the FAL CLI has also been dropped.

## Getting Started

### 1. Install dbt-postgres-python
`pip install dbt-postgres-python`

### 2. Update your `profiles.yml` and add the fal adapter

```yaml
jaffle_shop:
  target: dev_with_fal
  outputs:
    dev_with_fal:
      type: fal  # "fal" type is kept for backwards compatibility
      db_profile: dev_postgres # This points to your main adapter
    dev_postgres:
      type: postgres
      ...
```

Don't forget to point to your main adapter with the `db_profile` attribute. This is how the fal adapter knows how to connect to your data warehouse.

### 3. Add your python models

Add in your python models to your project just as you would your SQL models. Follow DBT's [instructions](https://docs.getdbt.com/docs/build/python-models) 
on how to do so.

```python
# a_python_model.py

import ...

def model(dbt, session):

    my_sql_model_df = dbt.ref("my_sql_model")

    final_df = ...  # stuff you can't write in SQL!

    return final_df
```

### 4. `dbt run`!
That is it! It is really that simple 😊
