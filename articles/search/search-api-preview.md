---
title: Preview feature list
titleSuffix: Azure Cognitive Search
description: Preview features are released so that customers can provide feedback on their design and utility. This article is a comprehensive list of all features currently in preview.

manager: nitinme
author: HeidiSteen
ms.author: heidist
ms.service: cognitive-search
ms.topic: conceptual
ms.date: 06/24/2021
---
# Preview features in Azure Cognitive Search

This article is a comprehensive list of all features that are in public preview. Preview functionality is provided without a service level agreement, and is not recommended for production workloads. For more information, see [Supplemental Terms of Use for Microsoft Azure Previews](https://azure.microsoft.com/support/legal/preview-supplemental-terms/).

Preview features that transition to general availability are removed from this list. If a feature isn't listed below, you can assume it is generally available. For announcements regarding general availability, see [Service Updates](https://azure.microsoft.com/updates/?product=search) or [What's New](whats-new.md).

|Feature&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  | Category | Description | Availability  |
|---------|------------------|-------------|---------------|
| [**Reset Documents**](search-howto-run-reset-indexers.md) | Indexer | Reprocesses individually selected search documents in indexer workloads. | [Search REST API 2020-06-30-Preview](/rest/api/searchservice/index-preview) |
|  [**Power Query connectors**](search-how-to-index-power-query-data-sources.md) | Indexer data source | Indexers can now index from other cloud platforms. If you are using an indexer to crawl external data sources for indexing, you can now use Power Query connectors to connect to Amazon Redshift, Elasticsearch, PostgreSQL, Salesforce Objects, Salesforce Reports, Smartsheet, and Snowflake. | [Sign up](https://aka.ms/azure-cognitive-search/indexer-preview) is required so that support can be enabled for your subscription on the backend. Access this data source using [Create Data Source (REST)](/rest/api/searchservice/create-data-source) with api-version=2020-06-30-Preview or the Azure portal.|
| [**SharePoint Online Indexer**](search-howto-index-sharepoint-online.md) | Indexer data source | New data source for indexer-based indexing of SharePoint content. | [Search REST API 2020-06-30-Preview](/rest/api/searchservice/preview-api/create-indexer) |
|  [**MySQL indexer data source**](search-howto-index-mysql.md) | Indexer data source | Index content and metadata from Azure MySQL data sources.| [Sign up](https://aka.ms/azure-cognitive-search/indexer-preview) is required so that support can be enabled for your subscription on the backend. Access this data source using [Create Data Source (REST)](/rest/api/searchservice/create-data-source) with api-version=2020-06-30-Preview, [.NET SDK 11.2.1](/dotnet/api/azure.search.documents.indexes.models.searchindexerdatasourcetype.mysql), and Azure portal. |
| [**Cosmos DB indexer: MongoDB API, Gremlin API, Cassandra API**](search-howto-index-cosmosdb.md) | Indexer data source | For Cosmos DB, SQL API is generally available, but MongoDB, Gremlin, and Cassandra APIs are in preview. | For Gremlin and Cassandra only, [sign up first](https://aka.ms/azure-cognitive-search/indexer-preview) so that support can be enabled for your subscription on the backend. MongoDB data sources can be configured in the portal. Otherwise, data source configuration for all three APIs is supported using [Create Data Source (REST)](/rest/api/searchservice/create-data-source) with api-version=2020-06-30-Preview or api-version=2019-05-06-Preview. |
| [**Native blob soft delete**](search-howto-index-changed-deleted-blobs.md) | Indexer data source | The Azure Blob Storage indexer in Azure Cognitive Search will recognize blobs that are in a soft deleted state, and remove the corresponding search document during indexing. | Add this configuration setting using [Create Indexer (REST)](/rest/api/searchservice/create-indexer) with api-version=2020-06-30-Preview or api-version=2019-05-06-Preview. |
| [**Semantic search**](semantic-search-overview.md) | Relevance (scoring) | Semantic ranking of results, captions, and answers. | [Search REST API 2020-06-30-Preview](/rest/api/searchservice/preview-api/search-documents) and Search Explorer (portal). |
| [**featuresMode parameter**](/rest/api/searchservice/preview-api/search-documents#query-parameters) | Relevance (scoring) | Relevance score expansion to include details: per field similarity score, per field term frequency, and per field number of unique tokens matched. You can consume these data points in [custom scoring solutions](https://github.com/Azure-Samples/search-ranking-tutorial). | Add this query parameter using [Search Documents (REST)](/rest/api/searchservice/preview-api/search-documents) with api-version=2020-06-30-Preview or 2019-05-06-Preview. |
| [**Normalizers**](search-normalizers.md) | Query |  Normalizers provide simple text pre-processing: consistent casing, accent removal, and ASCII folding, without invoking the full text analysis chain.| [Search REST API 2020-06-30-Preview](/rest/api/searchservice/preview-api/search-documents) |
| [**speller**](cognitive-search-aml-skill.md) | Query | Optional spelling correction on query term inputs for simple, full, and semantic queries. | [Search REST API 2020-06-30-Preview](/rest/api/searchservice/preview-api/search-documents) |
| [**moreLikeThis**](search-more-like-this.md) | Query | Finds documents that are relevant to a specific document. This feature has been in earlier previews. | Add this query parameter in [Search Documents (REST)](/rest/api/searchservice/search-documents) calls with api-version=2020-06-30-Preview, 2019-05-06-Preview, 2016-09-01-Preview, or 2017-11-11-Preview. |
| [**Azure Machine Learning (AML) skill**](cognitive-search-aml-skill.md) | AI enrichment (skills) | A new skill type to integrate an inferencing endpoint from Azure Machine Learning. Get started with [this tutorial](cognitive-search-tutorial-aml-custom-skill.md). | Use [Search REST API 2020-06-30-Preview](/rest/api/searchservice/) or 2019-05-06-Preview. Also available in the portal, in skillset design, assuming Cognitive Search and Azure ML services are deployed in the same subscription. |
| [**Entity Linking skill (v3)**](cognitive-search-skill-entity-linking-v3.md) | AI enrichment (skills)  | A cognitive skill used during indexing that returns a list of recognized entities with links to a well-known knowledge base. | Reference this preview skill using the Skillset editor in the portal or [Create Skillset (REST)](/rest/api/searchservice/create-skillset) with api-version=2020-06-30-Preview or api-version=2019-05-06-Preview. |
| [**Entity Recognition cognitive skill (v3)**](cognitive-search-skill-entity-recognition-v3.md) | AI enrichment (skills)  | A cognitive skill used during indexing that recognizes more entities than the previous version. | Reference this preview skill using the Skillset editor in the portal or [Create Skillset (REST)](/rest/api/searchservice/create-skillset) with api-version=2020-06-30-Preview or api-version=2019-05-06-Preview. |
| [**Sentiment cognitive skill (v3)**](cognitive-search-skill-sentiment-v3.md) | AI enrichment (skills)  | A cognitive skill used during indexing that evaluates unstructured text and for each record, provides sentiment labels. This version adds opinion mining. | Reference this preview skill using the Skillset editor in the portal or [Create Skillset (REST)](/rest/api/searchservice/create-skillset) with api-version=2020-06-30-Preview or api-version=2019-05-06-Preview. |
| [**PII Detection skill**](cognitive-search-skill-pii-detection.md) | AI enrichment (skills)  | A cognitive skill used during indexing that extracts personal information from an input text and gives you the option to mask it from that text in various ways. | Reference this preview skill using the Skillset editor in the portal or [Create Skillset (REST)](/rest/api/searchservice/create-skillset) with api-version=2020-06-30-Preview or api-version=2019-05-06-Preview. |
| [**Incremental enrichment**](cognitive-search-incremental-indexing-conceptual.md) | AI enrichment (skills) | Adds caching to an enrichment pipeline, allowing you to reuse existing output if a targeted modification, such as an update to a skillset or another object, does not change the content. Caching applies only to enriched documents produced by a skillset.| Add this configuration setting using [Create Indexer (REST)](/rest/api/searchservice/create-indexer) with api-version=2020-06-30-Preview or api-version=2019-05-06-Preview. |
| [**Debug Sessions**](cognitive-search-debug-session.md) | Portal, AI enrichment (skills) | An in-session skillset editor used to investigate and resolve issues with a skillset. Fixes applied during a debug session can be saved to a skillset in the service. | Portal only, using mid-page links on the Overview page to open a debug session. |

## How to call a preview REST API

Azure Cognitive Search always pre-releases experimental features through the REST API first, then through prerelease versions of the .NET SDK.

Preview features are available for testing and experimentation, with the goal of gathering feedback on feature design and implementation. For this reason, preview features can change over time, possibly in ways that break backwards compatibility. This is in contrast to features in a GA version, which are stable and unlikely to change with the exception of small backward-compatible fixes and enhancements. Also, preview features do not always make it into a GA release.

While some preview features might be available in the portal and .NET SDK, the REST API always has preview features.

+ For search operations, [**`2020-06-30-Preview`**](/rest/api/searchservice/index-preview) is the current preview version.

+ For management operations, [**`2019-10-01-Preview`**](/rest/api/searchmanagement/index-2019-10-01-preview) is the current preview version.

Older previews are still operational but become stale over time. If your code calls `api-version=2019-05-06-Preview` or `api-version=2016-09-01-Preview` or `api-version=2017-11-11-Preview`, those calls are still valid. However, only the newest preview version is refreshed with improvements.

The following example syntax illustrates a call to the preview API version.

```HTTP
POST https://[service name].search.windows.net/indexes/hotels-idx/docs/search?api-version=2020-06-30-Preview  
  Content-Type: application/json  
  api-key: [admin key]
```

Azure Cognitive Search service is available in multiple versions. For more information, see [API versions](search-api-versions.md).

## Next steps

Review the Search REST Preview API reference documentation. If you encounter problems, ask us for help on [Stack Overflow](https://stackoverflow.com/) or [contact support](https://azure.microsoft.com/support/community/?product=search).

> [!div class="nextstepaction"]
> [Search service REST API Reference (Preview)](/rest/api/searchservice/index-preview)
