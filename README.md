# MLOps Platforms

## What This Is

This is a resource for understanding and evaluating MLOps platforms. It is an especially confusing landscape with [hundreds of tools available](https://huyenchip.com/2020/12/30/mlops-v2.html). This project here just looks at platforms.

Just understanding platforms alone is complex. Platforms have their own specializations and there is no clear line between a tool and a platform. We explain this in the [Thoughtworks Guide (COMING SOON!)](#) and the below illustrates how some of the platforms specialize in particular areas (bottom) and others aim to cover the whole lifecycle with equal focus:

[MLOps Landscape Diagram](images/whitepaper_MLOps_Landscape.png)

Even platforms that have a similar scope have different concepts and strategies, making them hard to compare directly. This repository provides resources for evaluating MLOps platforms.

If you're wondering what process to use to evaluate MLOps platforms, see the [Thoughtworks Guide (COMING SOON!)](#). If you know how to evaluate MLOps platforms and want materials, read on.

## Format

We provide an open format of categories and have links to vendor documentation within cells to highlight features. This lets vendors do things their own ways and helps readers find the detail they need.

## Platform Concepts Intros

In addition to the comparison matrix in the next section, we provide short marketing-free introductions to key concepts of some of the platforms. This provides context to make sense of the features in the matrix.

- [AWS Sagemaker](AWS_Google_Azure.md#amazon), [Google Vertex](AWS_Google_Azure.md#google) and [Microsoft Azure ML](AWS_Google_Azure.md#azure)
- [Databricks](Dataiku_Databricks_h2o.md#databricks-lakehouse-platform), [Dataiku](Dataiku_Databricks_h2o.md#dataiku) and [h2o](Dataiku_Databricks_h2o.md#h2oai)
- [kubeflow](kubeflow_mlflow.md#kubeflow) and [mlflow](kubeflow_mlflow.md#mlflow)

## Comparison Matrix

We suggest to click through to the [master spreadsheet in google sheets](https://docs.google.com/spreadsheets/d/1nRqjnD7SCMJGmYR2gdZJ84YolLnHAMJwjSG7z7VcM6c/edit?usp=sharing):

[![matrix](images/spreadsheet_screenshot.png)](https://docs.google.com/spreadsheets/d/1nRqjnD7SCMJGmYR2gdZJ84YolLnHAMJwjSG7z7VcM6c/edit?usp=sharing)

If you can't access or don't like google sheets then there is a [translation of the matrix into Github markdown](markdown_matrix.md)


## Contributions

Everyone is welcome to contribute, including vendors. Language should be neutral - marketing language will not be accepted.

Changes are welcome by PR but if you wish to add a new platform/column to the matrix, please create your column in a new spreadsheet (following our format) and link from an issue or PR. A maintainer will then update the [master spreadsheet](https://docs.google.com/spreadsheets/d/1nRqjnD7SCMJGmYR2gdZJ84YolLnHAMJwjSG7z7VcM6c/edit?usp=sharing) used to [generate the markdown](https://tabletomarkdown.com/convert-spreadsheet-to-markdown/).


## Disclaimer

We do our best to keep this information accurate and up-to-date but cannot provide guarantees. References to documentation are provided throughout so readers can check for themselves. If you spot anything inaccurate then please raise an issue or pull request (see Contributing section above).
