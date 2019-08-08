---
title: 백 엔드 서버에서 SQL Server 인스턴스 및 데이터베이스 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Microsoft SQL Server 데이터베이스 및 인스턴스를 제거한 후에는이를 실행 하는 서버를 제거 하거나 다른 데이터베이스를 사용 하도록 서버를 다시 구성한 후에 제거 합니다. 현재 SQL Server를 중지 하거나 현재 서버를 다시 구성 하 여 데이터베이스를 더 이상 사용 하지 않거나 사용할 수 없는 경우에는이 항목의 절차를 수행 해야 합니다.
ms.openlocfilehash: 6c526499e3036c9a10b8dc92ccc519f21ae8bc96
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244435"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>백 엔드 서버에서 SQL Server 인스턴스 및 데이터베이스 제거

Microsoft SQL Server 데이터베이스 및 인스턴스를 제거한 후에는이를 실행 하는 서버를 제거 하거나 다른 데이터베이스를 사용 하도록 서버를 다시 구성한 후에 제거 합니다. 현재 SQL Server를 중지 하거나 현재 서버를 다시 구성 하 여 데이터베이스를 더 이상 사용 하지 않거나 사용할 수 없는 경우에는이 항목의 절차를 수행 해야 합니다.
  
보관 서버 또는 모니터링 서버의 데이터베이스나 인스턴스를 제거 하려면 먼저 서버 역할을 제거 해야 합니다. 마찬가지로, 프런트 엔드 풀에 대 한 인스턴스 또는 데이터베이스를 제거 하려면 먼저 종속 서버 역할을 제거 하거나 다시 구성 해야 합니다. 이러한 절차는 collocated 데이터베이스와 서버에 대 한 별도의 인스턴스를 구분 하지 않습니다. 프로시저는 데이터베이스의 collocation에 영향을 받지 않습니다.
  
## <a name="in-this-section"></a>이 섹션의

- [프런트 엔드 풀에 대 한 SQL Server 데이터베이스 제거](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [모니터링 서버용 SQL Server 데이터베이스 제거](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [보관 서버용 SQL Server 데이터베이스 제거](remove-the-sql-server-database-for-an-archiving-server.md)
    

