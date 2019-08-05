---
title: 비즈니스용 Skype 서버의 데이터 모니터링에 액세스
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 845385ca-5532-4fa2-91b9-51c6de6fec91
description: '요약: 비즈니스용 Skype 서버에서 사용 되는 모니터링 데이터에 대해 알아봅니다.'
ms.openlocfilehash: b5000c2fdec4933ef3377800b011ef15df8b4fb7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197477"
---
# <a name="access-monitoring-data-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 데이터 모니터링에 액세스
 
**요약:** 비즈니스용 Skype 서버에서 사용 되는 모니터링 데이터에 대해 알아봅니다.
  
모니터링 데이터는 SQL Server 데이터베이스 쌍 (LcsCdr)에 저장 되며, 통화 세부 정보를 기록 하 고 QoEMetrics 데이터에 대 한 품질을 제공할 수 있습니다. 이러한 두 데이터베이스에 대 한 특별 한 것이 없습니다. 즉, SQL Server 데이터에 액세스 하 고 분석 하는 데 일반적으로 사용 하는 도구를 사용 하 여 해당 데이터베이스에 저장 된 데이터에 액세스할 수 있습니다.
  
모니터링 데이터에 액세스 하 고 분석 하기 위해 고려해 야 할 도구 중 하나는 비즈니스용 Skype 서버 모니터링 보고서입니다. 모니터링 보고서는 Microsoft SQL Server Reporting 서비스에 의해 게시 되는 표준 보고서 집합입니다. 웹 브라우저를 사용 하 여 액세스할 수 있는 이러한 보고서에는 CDR 및 체감 품질 데이터베이스에 저장 된 CDR (통화 정보 기록) 및 체감 품질 (사용 품질) 레코드를 기준으로 하는 사용량, 호출 진단 정보 및 미디어 품질 정보가 제공 됩니다. 모니터링 보고서는 비즈니스용 skype 서버와 함께 제공 되며, 비즈니스용 skype server를 설치 하 고 모니터링을 구성한 후 비즈니스용 Skype 서버 배포 마법사에서 설치할 수 있습니다.
  
참고로, 모니터링 보고서에는 SQL Server Reporting Service를 사용 해야 합니다. Sql server Reporting Service는 sql Server를 설치할 때와 동시에 설치 하거나 SQL Server 자체 설치 후 언제 든 설치할 수 있습니다.
  
자세한 내용은 [비즈니스용 Skype 서버의 모니터링 보고서 설치](../../deploy/deploy-monitoring/install-monitoring-reports.md)항목을 참조 하세요.
  

