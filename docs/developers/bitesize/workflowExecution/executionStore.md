# Workflow Execution: The Execution Store

## Purpose

The Execution Store is a data structure owned and maintained inside each 
`WorkflowExecutionActor` (see [Major Actors](majorActors.md)).

Its purpose is to hold the current _status_ of what the workflow is doing, 
what it has done, and what it has left to do. If the WOM graph holds a static
representation of the workflow which doesn't change as the workflow is run, the
Execution Store holds the dynamic status of each node in the graph at any given moment
in time.

The Execution Store is also used to answer questions like "which nodes in the
workflow graph are ready to run because their dependencies are satisfied?".

**Note:** The Execution Store does **not** hold the values which are generated by
running the various nodes in the WOM graph. That is the domain of the [Value Store](valueStore.md). 

## Data Structure

The Execution Store is a mapping from WOM nodes (and a shard index, if necessary)
to the execution status of those nodes in the actual workflow.

## Examples

Some worked through examples of how the Execution Store and Value Store change as workflows progress
are given on the [Execution and Value Store Examples](executionAndValueStoreExamples.md) page.