---
description: 'sys.pdw_database_mappings (Transact-sql) '
title: sys.pdw_database_mappings (Transact-sql) |Microsoft Docs
ms.custom: ''
ms.date: 10/17/2017
ms.prod: sql
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
dev_langs:
- TSQL
ms.assetid: 4ae2c71e-dd56-41ea-a16b-64936175b459
author: ronortloff
ms.author: rortloff
monikerRange: '>= aps-pdw-2016 || = sqlallproducts-allversions'
ms.openlocfilehash: fb32b46347105b6dd80bf8013fe263018fad80e3
ms.sourcegitcommit: 22dacedeb6e8721e7cdb6279a946d4002cfb5da3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/14/2020
ms.locfileid: "92035010"
---
# <a name="syspdw_database_mappings-transact-sql"></a>sys.pdw_database_mappings (Transact-sql) 
[!INCLUDE [pdw](../../includes/applies-to-version/pdw.md)]

  将数据库的 **database_id**映射到计算节点上使用的物理名称，并提供系统上数据库所有者的 **主体 id** 。 将 **sys.pdw_database_mappings** 联接到 **sys.databases** 和 **sys.pdw_nodes_pdw_physical_databases**。  
  
|列名|数据类型|说明|范围|  
|-----------------|---------------|-----------------|-----------|  
|physical_name|**nvarchar (36) **|计算节点上数据库的物理名称。<br /><br /> **physical_name** 和 **database_id** 构成此视图的键。||  
|database_id|**int**|数据库的对象 ID。 请参阅 [sys.databases &#40;transact-sql&#41;](../../relational-databases/system-catalog-views/sys-databases-transact-sql.md)。<br /><br /> **physical_name** 和 **database_id** 构成此视图的键。||  
  
## <a name="examples-sspdw"></a>示例：[!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 下面的示例将 sys.pdw_database_mappings 联接到其他系统表，以显示数据库的映射方式。  
  
```  
SELECT DB.database_id, DB.name, Map.*, Phys.*   
FROM sys.databases AS DB  
JOIN sys.pdw_database_mappings AS Map  
    ON DB.database_id = Map.database_id  
JOIN sys.pdw_nodes_pdw_physical_databases AS Phys  
    ON Map.physical_name = Phys.physical_name  
ORDER BY DB.database_id, Phys.pdw_node_id;  
```  
  
## <a name="see-also"></a>另请参阅  
 [Azure Synapse Analytics 和并行数据仓库目录视图](../../relational-databases/system-catalog-views/sql-data-warehouse-and-parallel-data-warehouse-catalog-views.md)   
 [sys.pdw_index_mappings &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-pdw-index-mappings-transact-sql.md)   
 [sys.pdw_table_mappings &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-pdw-table-mappings-transact-sql.md)   
 [sys.pdw_nodes_pdw_physical_databases &#40;Transact-sql&#41;](../../relational-databases/system-catalog-views/sys-pdw-nodes-pdw-physical-databases-transact-sql.md)  
  
  

