---
description: 处理结果 - 检索结果集信息
title: " (ODBC) 检索结果集信息 |Microsoft Docs"
ms.custom: ''
ms.date: 03/03/2017
ms.prod: sql
ms.prod_service: database-engine, sql-database, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- result sets [ODBC]
- result sets [ODBC], fetching
ms.assetid: 34f235e4-f80b-4123-8764-9deb18506f14
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azuresqldb-current||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 072747868ddd3358c0cc074e16ba64ff4afe980d
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/17/2020
ms.locfileid: "88490832"
---
# <a name="processing-results---retrieve-result-set-information"></a>处理结果 - 检索结果集信息
[!INCLUDE[SQL Server Azure SQL Database Synapse Analytics PDW ](../../includes/applies-to-version/sql-asdb-asdbmi-asa-pdw.md)]

    
### <a name="to-get-information-about-a-result-set"></a>获取有关结果集的信息  
  
1.  调用 [SQLNumResultCols](../../relational-databases/native-client-odbc-api/sqlnumresultcols.md) 可获取结果集中的列数。  
  
2.  对于结果集中的每个列：  
  
    -   调用 [SQLDescribeCol](../../relational-databases/native-client-odbc-api/sqldescribecol.md) 以获取有关结果列的信息。  
  
     或  
  
    -   调用 [SQLColAttribute](../../relational-databases/native-client-odbc-api/sqlcolattribute.md) 可获取有关结果列的特定描述符信息。  
  
## <a name="see-also"></a>另请参阅  
[&#40;ODBC&#41;处理结果 ](../../relational-databases/native-client-odbc-how-to/processing-results-process-results.md)

[确定结果集的特征 &#40;ODBC&#41;](../../relational-databases/native-client-odbc-results/determining-the-characteristics-of-a-result-set-odbc.md)  
  
  
