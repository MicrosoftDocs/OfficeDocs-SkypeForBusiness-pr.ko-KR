---
title: 비즈니스용 Skype 서버에서 모니터링 데이터에 액세스
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: '요약: 비즈니스용 Skype 서버에서 사용되는 모니터링 데이터에 대해 자세히 알아보습니다.'
ms.openlocfilehash: deff5dc5c21437cd89282578d2bf3f546f444f94
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826548"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>비즈니스용 Skype 서버에서 모니터링 데이터에 액세스
 
**요약:** 비즈니스용 Skype 서버에서 사용되는 모니터링 데이터에 대해 자세히 알아보습니다.
  
모니터링 데이터는 SQL Server 데이터베이스 쌍에 저장됩니다. 이러한 데이터베이스 쌍은 통화 정보 기록 데이터를 위한 LcsCdr과 체감 품질 데이터를 위한 QoEMetrics입니다. 이러한 두 데이터베이스는 특별한 사항이 없습니다. 즉, 이러한 데이터베이스에 저장되는 데이터는 일반적으로 SQL Server 데이터를 액세스하고 분석하는 데 사용되는 도구를 통해 액세스할 수 있습니다.
  
모니터링 데이터에 액세스하고 분석할 때 고려해야 하는 도구 중 하나는 비즈니스용 Skype 서버 모니터링 보고서입니다. 모니터링 보고서는 Microsoft SQL Server Reporting Services에서 게시되는 표준 보고서 집합입니다. 웹 브라우저를 통해 액세스할 수 있는 이러한 보고서는 모두 CDR 및 QoE 데이터베이스에 저장된 CDR(통화 정보 기록) 및 QoE(체감 품질) 레코드를 기반으로 사용, 통화 진단 정보 및 미디어 품질 정보를 제공합니다. 모니터링 보고서는 비즈니스용 Skype 서버와 함께 발송되고 비즈니스용 Skype 서버가 설치되고 모니터링이 구성된 후 비즈니스용 Skype 서버 배포 마법사에서 설치할 수 있습니다.
  
위에서 설명한 것처럼 모니터링 보고서를 위해서는 SQL Server Reporting Services를 사용해야 합니다. SQL Server Reporting Services는 SQL Server를 설치할 때 동시에 설치하거나 SQL Server 자체를 설치한 후 언제라도 설치할 수 있습니다.
  
자세한 내용은 비즈니스용 [Skype 서버에서 모니터링 보고서 설치 항목을 참조하세요.](../../deploy/deploy-monitoring/install-monitoring-reports.md)
  

