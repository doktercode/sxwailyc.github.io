---
layout: post
comments: true
categories: lucene
---
## lucene 中如何更新docment

## 根据ID删除对应的doc

代码

	indexWriter.deleteDocuments(NumericRangeQuery.newIntRange("id", id, id, true, true));
	indexWriter.addDocument(doc);


