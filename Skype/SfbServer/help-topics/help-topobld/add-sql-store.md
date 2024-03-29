---
title: SQL 저장소 추가
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddSqlStorePage
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 8ec39dfc-c58d-4fdb-b61e-f71dd691cef8
description: 새 SQL 저장소를 정의하려면(기본 인스턴스 또는 명명된 인스턴스) SQL Server 기반 데이터베이스 및 SQL Server 인스턴스를 지정하는 경우 다음을 지정합니다.
ms.openlocfilehash: e8228063ee3569e1e72683f63af663e13541de03
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62384506"
---
# <a name="add-sql-store"></a>SQL 저장소 추가

새 SQL 저장소를 정의하려면(기본 인스턴스 또는 명명된 인스턴스) SQL Server 기반 데이터베이스 및 SQL Server 인스턴스를 지정하는 경우 다음을 지정합니다.

정의할 데이터베이스 인스턴스를 호스팅할 SQL Server 서버의 FQDN(FQDN)을 지정합니다.

데이터를 호스팅할 SQL Server 인스턴스를 지정합니다. 기본 인스턴스를 지정할 수도 있고 명명된 인스턴스를 지정할 수도 있습니다.

특정 인스턴스에서의 데이터베이스 배치는 분명하게 파악해야 합니다. 서버 배치 및 데이터베이스 인스턴스 배치에 대한 자세한 내용은 [Server Collocation in a Front End Pool Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-an-enterprise-edition-front-end-pool-deployment) 및 [Server Collocation in a Standard Edition Server Deployment](/previous-versions/office/lync-server-2013/lync-server-2013-server-collocation-in-a-standard-edition-server-deployment)를 참조하십시오.