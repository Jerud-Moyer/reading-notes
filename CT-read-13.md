## mongoDB
### Aggregation pipeline
- The aggregation pipeline is a framework for data aggregation modeled on the concept of data processing pipelines. Documents enter a multi-stage pipeline that transforms the documents into aggregated results
### Pipeline
- The MongoDB aggregation pipeline consists of stages. Each stage transforms the documents as they pass through the pipeline. Pipeline stages do not need to produce one output document for every input document; e.g., some stages may generate new documents or filter out documents.
- Pipeline stages can appear multiple times in the pipeline with the exception of $out, $merge, and $geoNear stages. For a list of all available stages, see Aggregation Pipeline Stages
- MongoDB provides the db.collection.aggregate() method in the mongo shell and the aggregate command to run the aggregation pipeline.
### Pipeline Expressions
- Some pipeline stages take a pipeline expression as the operand. Pipeline expressions specify the transformation to apply to the input documents. Expressions have a document structure and can contain other expression
- Pipeline expressions can only operate on the current document in the pipeline and cannot refer to data from other documents: expression operations provide in-memory transformation of documents.
### Aggregation Pipeline Behavior
- In MongoDB, the aggregate command operates on a single collection, logically passing the entire collection into the aggregation pipeline. To optimize the operation, wherever possible, use the following strategies to avoid scanning the entire collection.
### Pipeline Operators and Indexes
- MongoDB’s query planner analyzes an aggregation pipeline to determine whether indexes can be used to improve pipeline performance.

## Aggregations in MongoDB by Example
### Starting an aggregation pipeline
- to begin an aggregation, call the aggregate function on a collection
- The aggregate function accepts an array of data transformations which are applied to the data in the order they're defined. This makes aggregation a lot like other data flow pipelines: the transformations that are defined first will be executed first and the result will be used by the next transformation in the sequence
### Matching documents
- The first stage of the pipeline is matching, and that allows us to filter out documents so that we're only manipulating the documents we care about. The matching expression looks and acts much like the MongoDB find function or a SQL WHERE clause
### Grouping documents
- Once we've filtered out the documents we don't want, we can start grouping together the ones that we do into useful subsets. We can also use groups to perform operations across a common field in all documents, such as calculating the sum of a set of transactions and counting documents
### Gaining insights with Sum, Min, Max and Avg