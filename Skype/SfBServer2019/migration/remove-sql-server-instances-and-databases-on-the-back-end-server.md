---
title: 백 엔드 서버에서 SQL Server 인스턴스 및 데이터베이스 제거
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Microsoft SQL Server 데이터베이스와 인스턴스를 제거한 후 또는 다른 데이터베이스를 사용 하도록 서버를 다시 구성한 후에는 해당 서버를 제거 합니다. 현재 SQL Server를 중지 하거나 현재 서버를 다시 구성 하 여 데이터베이스가 사용 되지 않거나 사용할 수 없는 상태로 만들려면이 항목의 절차를 수행 해야 합니다.
ms.openlocfilehash: 6e108e4dfef86b482b839bd440f54702ab42107d
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752160"
---
# <a name="remove-sql-server-instances-and-databases-on-the-back-end-server"></a>백 엔드 서버에서 SQL Server 인스턴스 및 데이터베이스 제거

Microsoft SQL Server 데이터베이스와 인스턴스를 제거한 후 또는 다른 데이터베이스를 사용 하도록 서버를 다시 구성한 후에는 해당 서버를 제거 합니다. 현재 SQL Server를 중지 하거나 현재 서버를 다시 구성 하 여 데이터베이스가 사용 되지 않거나 사용할 수 없는 상태로 만들려면이 항목의 절차를 수행 해야 합니다.
  
보관 서버 또는 모니터링 서버에 대 한 데이터베이스 또는 인스턴스를 제거 하려면 먼저 서버 역할을 제거 해야 합니다. 마찬가지로 프런트 엔드 풀에 대 한 인스턴스 또는 데이터베이스를 제거 하려면 먼저 종속 서버 역할을 제거 하거나 다시 구성 해야 합니다. 이러한 절차는 배치된 데이터베이스나 개별 서버 인스턴스 간에 구분되지 않습니다. 데이터베이스 배치는 절차에 영향을 주지 않습니다.
  
## <a name="in-this-section"></a>이 섹션의 내용

- [프런트 엔드 풀에 대한 SQL Server 데이터베이스 제거](remove-the-sql-server-database-for-a-front-end-pool.md)
    
- [모니터링 서버용 SQL Server 데이터베이스 제거](remove-the-sql-server-database-for-a-monitoring-server.md)
    
- [보관 서버용 SQL Server 데이터베이스 제거](remove-the-sql-server-database-for-an-archiving-server.md)
    

