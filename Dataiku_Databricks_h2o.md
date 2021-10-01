
## Databricks, Dataiku, h2o.ai

Here we compare another selection of established platforms, this time not cloud providers. These three platforms all have particularly strong features for data preparation and training, they all have Spark integration and AutoML capabilities. But they&#39;re also very different in detail.

Databricks starts from data storage and data engineering and builds out to provide a platform for data engineering, machine learning and analytics. Dataiku&#39;s focus is making data analysis and ML accessible to analysts as well as speeding up ML for data scientists. H2O started as an open source Java-based engine for running machine learning algorithms. It is now a suite of tools consolidated into h2o.ai hybrid cloud.

### Databricks Lakehouse Platform

The Databricks Lakehouse Platform aims to bring data engineering, machine learning and analytics. One of its selling points is a unified architecture to try to break down silos and encourage collaboration. The platform contains areas that address particular needs, which they break down as:

- Delta Lake (flexible storage with built-in history)
- ETL
- Machine Learning
- Data Science
- Databricks SQL
- Security and Administration

[Delta Lake](https://databricks.com/product/data-science) is the reason why lakehouse gets its name. It&#39;s a format based on Parquet that makes it possible to ACID transactions to a data lake in cloud object storage. This makes it suitable for streaming as well as batch processing. Delta Lake can also enforce a schema, support schema modification and keep a transaction log. So you get a combination of the features of a data lake with those of a data warehouse - hence &#39;lakehouse&#39;.

We will focus primarily on the [Data Science](https://databricks.com/product/data-science) and [Machine Learning](https://databricks.com/product/machine-learning) parts of the platform.

#### Data Science

Delta Lake is [relevant to data scientists](https://databricks.com/discover/demos/machine-learning-with-mlflow) insofar as it helps bring a schema to otherwise schemaless data. This helps to ensure data quality and reduce friction between the data engineering and data science stages.

Databricks notebooks support a range of languages and ways of working with data. You can perform Spark operations, SQL, use python, R and more, all in the same notebook.

Different types of data work will have different compute needs. Databricks supports this with different [types of clusters](https://docs.databricks.com/clusters/index.html), including requests for specialist underlying compute like GPUs.

#### Machine Learning​ ![](RackMultipart20211001-4-1uea3e4_html_18d2f5aca421aef9.png)

Figure 25: Machine Learning with [Databricks](https://databricks.com/product/machine-learning).

Prepared features can be stored in the [platform&#39;s feature store](https://docs.databricks.com/applications/machine-learning/preprocess-data/index.html) so that they can be discovered and shared with other teams.

Model training support is integrated with notebooks - [training runs are tracked with mlflow](https://docs.databricks.com/applications/machine-learning/train-model/ml-quickstart.html) and the training job history can be seen from a panel next to the notebook. Trained models can go to the [model registry](https://docs.databricks.com/applications/machine-learning/manage-model-lifecycle/index.html), from which they can be transitioned between environments:

![](RackMultipart20211001-4-1uea3e4_html_d4edd3be0ceeb112.png)

Figure 26: Environment transitions with mlflow on Databricks.

Models can be deployed for [real-time inference/serving](https://docs.databricks.com/applications/machine-learning/model-deploy/index.html). [Batch inference is also supported](https://docs.databricks.com/applications/machine-learning/model-inference/index.html), either on models in a popular framework or using spark mllib. Spark also has support for streaming.

#### AutoML

Databricks offers [AutoML features](https://docs.databricks.com/applications/machine-learning/automl.html) within the context of notebooks. Python code is used to trial different algorithms and models for a dataset. In the background databricks creates notebooks specifically for each of the permutations that it trials, so that you can see what happened under the hood and leverage the code.

### Dataiku

Dataiku&#39;s tagline is &#39;Everyday AI, Extraordinary&#39; people. Its platform emphasises the visual, attempting to make data tasks faster and more accessible. Users are able to explore and clean data using Data Science Studio&#39;s simple visual interface and can also write code for transforming data. Pipelines can be built up visually and transformation steps (&#39;recipes&#39;) can be pre-built drag-and-drop or crafted using a chosen language/tool. Rather than competing with Spark or Hadoop, Dataiku integrates with these and other tools. It also includes features for deployment, monitoring and collaboration.

![](RackMultipart20211001-4-1uea3e4_html_56a6ae40c5b00304.png)

Figure 27: Machine Learning lifecycle areas supported by Dataiku.

#### Data Exploration and Transformation

Work in Data Science Studio happens within a project. A project can contain datasets, which can be selected from a wide variety of sources including cloud blob storage, databases, hadoop, spreadsheets, sharepoint, salesforce and social media. This variety is because the platform is designed to be used by a wide range of users. Where possible Data Science Studio keeps the data in its original location and performs the processing at source (e.g. by integrating with Hadoop).

Once the dataset is in the project then it can be explored and manipulated. Data Science Studio infers the data types of columns and can highlight missing values or outliers. There&#39;s an easy, spreadsheet-like interface for applying operations or writing formulas to handle missing values, apply transformations or create new columns:

![](RackMultipart20211001-4-1uea3e4_html_f8fd9bf3d22b2f8d.png)

Figure 28: Spreadsheet-like interface for data operations in Dataiku.

There are many built-in transformations for different data types and they can be previewed against a small sample of data before applying to the whole set. This kind of interface with the ability to interface to large databases and hadoop has a clear appeal to business-focused data analysts (which is a [key focus for Dataiku](https://www.youtube.com/watch?v=MUwloqMJ8BQ)) and is designed to also save time for those who are [comfortable getting into the code](https://www.youtube.com/watch?v=ryZRRIjQ5Z8).

Within a Data Science Studio you create Flows that correspond to Pipelines in other platforms. Within a Flow you can embed Recipes that transform Datasets. These Recipes can be pre-built, constructed visually (e.g. visual join operations) or written using code:

![](RackMultipart20211001-4-1uea3e4_html_3c859e293b373b1f.png)

Figure 29: A Flow in Dataiku. Recipes section on the right for adding steps to the Flow.

#### Model Building and Deployment

Data Science Studio provides a [Lab for assisted building of models](https://www.youtube.com/watch?v=cT4lRTNW9ns). Here you can build models using configurable AutoML with many tunable parameters (or you can use the defaults). You can also obtain predictions, explain predictions and output reports.

The Lab is a separate area from a Flow so to build a model within the Flow it needs to be &#39;Deployed&#39; into the Flow. This creates a training Recipe in the Flow and a Model as the output of the Recipe. The Flow could then have a step to generate predictions using the model (a Scoring step) or it could Deploy the model as an API. New runs will then [automatically replace the live version](https://www.youtube.com/watch?v=zWs_B_cVjtc) (with old versions kept as options to roll back to).

Models are not restricted to the AutoML features and can be [written with custom code](https://doc.dataiku.com/dss/latest/machine-learning/algorithms/in-memory-python.html#custom-models) or using [Spark MLLib](https://doc.dataiku.com/dss/latest/machine-learning/algorithms/mllib.html) or [H2O&#39;s Sparkling Water](https://doc.dataiku.com/dss/latest/machine-learning/algorithms/sparkling-water.html). Deploying a model creates an API endpoint. [API endpoints](https://doc.dataiku.com/dss/8.0/apinode/endpoints.html) can also be created for custom code functions or even SQL queries. Data Science Studio can also [host a frontend](https://doc.dataiku.com/dss/8.0/webapps/index.html#introduction-to-dss-webapps) with tools for building your own interactive Webapp or you can instead [publish a simple dashboard](https://doc.dataiku.com/dss/latest/dashboards/index.html).

[Metrics](https://knowledge.dataiku.com/latest/courses/automation/metrics-checks-hands-on.html) can be tracked for Datasets (such as number of records or records in a value range) or for Models (such as ROC AUC). Checks can then be created against these Metrics so that warnings are displayed if the Checks fail.

### H2o.ai

H2o.ai provides a range of products. We&#39;ll go over the key ones and how they relate to each other. Let&#39;s start with the open source product &#39;h2o&#39;, which is the oldest one and shares its name with the company. The latest version is called h2o-3 (which also helps separate the product from the company names).

#### H2o-3

H2o-3 comes with a UI called Flow. Within Flow you get a notebook-like environment for working with data and building models. Cells can be written with code or you can use a wizard-like interface to choose steps like [loading a file or imputing missing values](https://docs.h2o.ai/h2o/latest-stable/h2o-docs/data-munging.html) (which results in some [CoffeeScript going into the cell for us](https://towardsdatascience.com/getting-started-with-h2o-using-flow-b560b5d969b8)). Models can be trained [using built-in algorithms](https://docs.h2o.ai/h2o/latest-stable/h2o-docs/data-science.html).

![](RackMultipart20211001-4-1uea3e4_html_d01d9921ca18c040.png)

Figure 30: The Flow UI of h2o-3 - a notebook-like environment for working with data and building models.

The execution behind all this is an in-memory compute engine running in the Java Virtual Machine but you [can work with](https://docs.h2o.ai/h2o/latest-stable/h2o-docs/quick-start-videos.html#quick-start-videos) Python or R as well as CoffeeScript and can interface to Hadoop or Spark. Models can be [exported](https://towardsdatascience.com/getting-started-with-h2o-using-flow-b560b5d969b8) to run in other Java environments (e.g. [a Spring Boot app](https://aws.amazon.com/blogs/machine-learning/training-and-serving-h2o-models-using-amazon-sagemaker/)) or [outside of Java with the provided runtime libraries](https://www.h2o.ai/products/h2o-driverless-ai/mojo-deployment-options/).

![](RackMultipart20211001-4-1uea3e4_html_c3c1ad35fc5f9eff.png)

Figure 31: The h2o-3 compute engine and its uses.

#### Sparkling Water

This is [h2o-3 but on top of Spark](https://docs.h2o.ai/#sparkling-water). So you can [run h2o algorithms on Spark](https://docs.h2o.ai/sparkling-water/3.1/latest-stable/doc/about.html).

#### Steam

Steam is for [managing h2o jobs on top of Spark or Kubernetes](https://www.h2o.ai/enterprise-support/#enterprise-security).

#### Driverless AI

Where h2o-3 gives you assistance in building models, Driverless AI is an alternative approach that is full-on AutoML. With h2o-3 you pick the algorithm but with Driverless AI a range of algorithms get tried out for you to pick the best.

You start with data representing historical observations with outcomes. You connect Driverless AI to your data (it supports a range of sources) and it then lets you explore the data and visualize column stats/correlations. It does test-train split and lets you set some options before running experiments. It automatically evaluates a range of different algorithms and compositions of features:

![](RackMultipart20211001-4-1uea3e4_html_4600c1d9b2aac181.png)

Figure 32: The h2o Driverless AI interface showing an experiment configuration. On the left we see this experiment will train GLM, LightGBM and XGBoostGBM models.

Driverless AI takes the approach of offering defaults and letting more advanced users drill into the details of how the experiments are conducted. It then provides insights into the model created and which features are most important for which predictions (explationations). Models can be exported to be run in a range of environments, much like h2o-3 models.

#### MLOps

[H2o MLOps](https://docs.h2o.ai/mlops-release/latest-stable/docs/userguide/index.html) is a model deployment and monitoring suite that runs on kubernetes. It handles models built with h2o-3 or h2o Driverless AI or you can Bring Your Own Model (provided you [specify a detailed schema for it](https://docs.h2o.ai/mlops-release/latest-stable/docs/userguide/byom.html#mlops-byom)).

#### Wave

[Wave](https://www.h2o.ai/products/h2o-wave/) is for developing ML-enabled and data-focused applications in python. Developers use python to write the UI as well as the backend and the data-handling. This makes it easy to embed graphs and charts.

![](RackMultipart20211001-4-1uea3e4_html_6f70c1f6c2ba7ada.png)

Figure 33: Developing ML-enabled applications with UIs from python with h2o Wave.

#### Hybrid Cloud Platform

[H2o Hybrid Cloud Platform](https://docs.h2o.ai/h2o-ai-cloud/index.html) brings together other h2o products to provide an integrated setup for developing, deploying, hosting and sharing applications. It runs on kubernetes so it can be installed on public, private or hybrid clouds.

The public face of the platform is the [Appstore](https://docs.h2o.ai/h2o-ai-cloud/docs/userguide/basic-concepts). This shows a set of tiles for published apps built with Wave. The platform allows apps built with Wave to be operationalised and published to the Appstore. [Driverless AI and h2o-3 projects can also be leveraged](https://www.h2o.ai/hybrid-cloud/request-demo/). The Driverless AI projects are automatically available in the MLOps screens in the platform. Deployed models can be leveraged by apps built with Wave.

Deployed models can be monitored using the features from the MLOps product. Steam is also integrated for managing h2o jobs.
