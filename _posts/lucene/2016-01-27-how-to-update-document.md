---
layout: post
comments: true
categories: lucene
---
## lucene 中如何更新docment



	indexWriter.deleteDocuments(NumericRangeQuery.newIntRange("id", id, id, true, true));
	indexWriter.addDocument(doc);


