---
title: 비즈니스용 Skype 서버의 CQD (통화 품질 대시보드) 용 데이터 API
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: '요약: 통화 품질 대시보드의 데이터 API에 대해 자세히 알아보세요. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: b8ff4823fad320ae57b8f06104afbb354c09b4eb
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888437"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>비즈니스용 Skype 서버의 CQD (통화 품질 대시보드) 용 데이터 API
 
**요약:** 통화 품질 대시보드의 데이터 API에 대해 자세히 알아보세요. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
데이터 API는 비즈니스용 Skype 서버용 통화 품질 대시보드에 대 한 프로그래밍 방식의 액세스를 제공 합니다.
  
## <a name="data-api-for-call-quality-dashboard"></a>통화 품질 대시보드의 데이터 API

데이터 API는 체감 품질 큐브에 대 한 쿼리 인터페이스를 제공 합니다. 데이터 API는 지정 된 차원과 필터를 기반으로 집계 된 체감 품질 메트릭을 제공 하는 다차원 데이터베이스 작업을 위한 REST API입니다.
  
미삭 작업은 다음 표에 나와 있습니다.
  

|**작업**|**설명**|
|:-----|:-----|
|[큐브 가져오기](get-cube.md) <br/> |사용 가능한 차원과 측정값의 목록을 가져옵니다.  <br/> |
|[차원 구성원 가져오기](get-dimension-members.md) <br/> |차원 구성원 가져오기 작업은 특정 차원의 구성원 목록을 반환 합니다. 또한 구성원 목록을 필터링 하 고 하위 집합을 가져오는 기능을 제공 하 여 회선 전송 비용을 줄입니다.  <br/> |
|[쿼리 실행](run-query.md) <br/> |쿼리 실행 작업은 지정 된 차원, 측정값, 필터에 따라 큐브에 대 한 쿼리를 실행 하 고 데이터를 다시 반환할 수 있는 기능을 제공 합니다.  <br/> |
|[캐시 지우기](clear-cache.md) <br/> |캐시 지우기 작업은 쿼리 및 데이터에 대 한 서버의 캐시를 삭제 합니다. 이렇게 하면 캐시가 다시 설정 되 고 나중에 새 요청에 대 한 체감 품질 큐브에 대 한 최신 데이터를 받게 됩니다.  <br/> |
|[통합 로그 가져오기](get-integration-log.md) <br/> |통합 로그 가져오기 작업 체감 품질 큐브 처리에서 작업을 설명 하는 로그 항목의 목록을 반환 합니다.  <br/> |
|[마지막 통합 데이터 가져오기](get-last-integration-data.md) <br/> |큐브에서 마지막 통합 데이터를 가져옵니다.  <br/> |
   
 **데이터 API에 대 한 CORS (교차 원본 리소스 공유) 지원**
  
데이터 API는 교차 원본 리소스 공유 (CORS)를 지원 합니다. CORS는 한 도메인에서 실행 되는 웹 응용 프로그램이 다른 도메인의 리소스에 액세스할 수 있도록 하는 HTTP 기능입니다. 웹 브라우저는 [같은 원본 정책](https://www.w3.org/Security/wiki/Same_Origin_Policy) 같은 원본 정책 이라고 하는 보안 제한을 구현 하 여 웹 페이지에서 다른 도메인의 api를 호출 하지 못하게 합니다. CORS는 한 도메인 (원본 도메인)이 다른 도메인의 Api를 호출할 수 있는 안전한 방법을 제공 합니다. CORS에 대 한 자세한 내용은 [cors 사양을](https://www.w3.org/TR/cors/) 참조 하세요.
  
 **Data API 용 CORS 사용**
  
 다음은 corsTrustedOrigin 응용 프로그램 설정에 나열 된 두 개의 도메인을 보여 주는 데이터 API web.config의 일부입니다. 이러한 서버에서 로드 된 스크립트에의 한 모든 요청은 Data API에서 신뢰 합니다.
  
정확한 프로토콜, 호스트 이름 및 포트 (있는 경우)를 포함 해야 합니다. 슬래시 문자 (/)를 끝에 넣지 마세요. 여러 항목을 쉼표로 구분 하 여 지정할 수 있습니다.
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


