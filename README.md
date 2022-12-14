# Copy Alternatives - Research

In this repository, we will compare the various options to __Azure Data Factory__ copy activities. As there are few scenarios where using default values can create challenges with running these pipelines in scale. for each of the options we will run using Azure Integration Runtime, Self Hosted Integration Runtime and Azure Data Factory Managed Integration Runtime. We will review:

- Performance

- Cost

- Operational aspects

The alternatives we will cover are:

- Using Azure Data Factory Copy Activity 
- Using a call to web activity to call a REST API - we will leverage Azure container apps to create a REST API.

__What would be covered?__

- The use cases requiring a copy activity.

- Detailed view on the experiment setup.

- Brief overview on the different compute options. (Azure Data Factory Managed Integration Runtime, Self Hosted Integration Runtime, Azure Integration Runtime)

- Detailed view on the experiment results.

- Conclusion

Ready to get started? Let's go!

## How does Azure Data Factory cost work?

The [documentation](https://learn.microsoft.com/en-us/azure/data-factory/pricing-concepts) provides a good overview on how the cost* is calculated through examples. The key points are:

- Orchestrator cost is calculated based on the number of activities and pipelines runs.

- Compute duration called [DIU](https://learn.microsoft.com/en-us/azure/data-factory/copy-activity-performance#data-integration-units)


*Cost - covering the pipeline execution and the compute resources used to run the pipeline.

With number of activities run in mind, it is suggested to try and reduce the number of activities in a pipeline. This is because the cost is calculated based on the number of activities run. The more activities you have in a pipeline, the more you will pay. For example if you need to copy 100 files, you can use a single copy activity to copy all 100 files. This will be cheaper than using 100 copy activities to copy 1 file each.

## Use cases requiring a copy activity


You receive data from multiple sources, all landing on your storage account. You need to move this from the landing zone to your lake. You can use a copy activity to move the data from the landing zone to the lake. You can also use a copy activity to move data from one location to another in the lake. Copy Activity is a very powerful activity that can be used in many scenarios, it is more useful when you have to move data from one location to another in the lake in bulk. 

An addtion to this use case could be a scenario where data has to be mnoved into a virtual network. In such scenarios you will to use either Self Hosted Integration Runtime or Azure Managed Integration Runtime. The Azure Integration Runtime is not supported in a virtual network.


## Experiment setup

## Compute options

### Azure Integration Runtime

### Azure Data Factory Managed Integration Runtime

### Self Hosted Integration Runtime

## Experiment results (place holder!)

We ran each type with multiple number of files to copy. The results are as follows: 

### 1000 files

| Experiment Description | DIU  | Activity Runs | External Activity Runs | Total Cost | Total Time |
|------------------------|------|---------------|------------------------|------------|------------|
| Azure IR + Copy   | 35   | Male   | 40   | 40   | 40   |
| Azure IR + ACA | 29   | Female | 30   | 30   | 30   |
| SHIR + Copy | 42   | Male   | 20   | 20   | 20   |
| SHIR + ACA | 42   | Male   | 20   | 20   | 20   |
| Managed IR + Copy | 42   | Male   | 20   | 20   | 20   |
| Managed IR + ACA | 42   | Male   | 20   | 20   | 20   |

### 2000 files

| Experiment Description | DIU  | Activity Runs | External Activity Runs | Total Cost | Total Time |
|------------------------|------|---------------|------------------------|------------|------------|
| Azure IR + Copy   | 35   | Male   | 40   | 40   | 40   |
| Azure IR + ACA | 29   | Female | 30   | 30   | 30   |
| SHIR + Copy | 42   | Male   | 20   | 20   | 20   |
| SHIR + ACA | 42   | Male   | 20   | 20   | 20   |
| Managed IR + Copy | 42   | Male   | 20   | 20   | 20   |
| Managed IR + ACA | 42   | Male   | 20   | 20   | 20   |


### 5000 files

| Experiment Description | DIU  | Activity Runs | External Activity Runs | Total Cost | Total Time |
|------------------------|------|---------------|------------------------|------------|------------|
| Azure IR + Copy   | 35   | Male   | 40   | 40   | 40   |
| Azure IR + ACA | 29   | Female | 30   | 30   | 30   |
| SHIR + Copy | 42   | Male   | 20   | 20   | 20   |
| SHIR + ACA | 42   | Male   | 20   | 20   | 20   |
| Managed IR + Copy | 42   | Male   | 20   | 20   | 20   |
| Managed IR + ACA | 42   | Male   | 20   | 20   | 20   |

### 10000 files

| Experiment Description | DIU  | Activity Runs | External Activity Runs | Total Cost | Total Time |
|------------------------|------|---------------|------------------------|------------|------------|
| Azure IR + Copy   | 35   | Male   | 40   | 40   | 40   |
| Azure IR + ACA | 29   | Female | 30   | 30   | 30   |
| SHIR + Copy | 42   | Male   | 20   | 20   | 20   |
| SHIR + ACA | 42   | Male   | 20   | 20   | 20   |
| Managed IR + Copy | 42   | Male   | 20   | 20   | 20   |
| Managed IR + ACA | 42   | Male   | 20   | 20   | 20   |


## Conclusion
