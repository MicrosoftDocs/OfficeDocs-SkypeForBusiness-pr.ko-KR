---
title: CQD(통화 품질 대시보드)에 대한 데이터 API를 비즈니스용 Skype 서버
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
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: '요약: 통화 품질 대시보드용 데이터 API에 대해 자세히 알아보는 방법을 설명하는 문서입니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.'
ms.openlocfilehash: cadb726714816f80fa818d9a706640fa52bd75529e6fc58d39ab63fe907b3bb8
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54333330"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>CQD(통화 품질 대시보드)에 대한 데이터 API를 비즈니스용 Skype 서버
 
**요약:** 통화 품질 대시보드용 데이터 API에 대해 자세히 알아보습니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.
  
데이터 API는 통화 품질 대시보드에 대한 프로그래밍 비즈니스용 Skype 서버.
  
## <a name="data-api-for-call-quality-dashboard"></a>통화 품질 대시보드용 데이터 API

데이터 API는 QoE 큐브에 대한 쿼리 인터페이스를 제공합니다. 데이터 API는 지정된 차원 및 필터를 기반으로 집계된 QoE 메트릭을 제공하는 다차원 데이터베이스 작업을 위한 REST API입니다.
  
REST 작업은 다음 표에 포함되어 있습니다.
  

|**작업**|**설명**|
|:-----|:-----|
|[큐브 가져오기](get-cube.md) <br/> |사용 가능한 크기 및 측정 목록을 얻습니다.  <br/> |
|[차원 구성원 가져오기](get-dimension-members.md) <br/> |차원 구성원 작업에서는 특정 차원의 구성원 목록을 반환합니다. 또한 구성원 목록을 필터링하고 하위 집합을 얻을 수 있는 기능을 제공하여 전신 전송 비용을 줄일 수 있습니다.  <br/> |
|[쿼리 실행](run-query.md) <br/> |쿼리 실행 작업을 사용하면 지정된 차원, 측정값 및 필터를 기반으로 큐브에서 쿼리를 실행하고 데이터를 반환할 수 있습니다.  <br/> |
|[캐시 지우기](clear-cache.md) <br/> |캐시 지우기 작업을 수행하면 쿼리 및 데이터에 대한 서버의 캐시가 삭제됩니다. 이렇게 하면 캐시가 다시 설정됩니다. 그러면 이후에 새 요청에 대한 QoE 큐브에서 새 데이터를 얻게 됩니다.  <br/> |
|[통합 로그 가져오기](get-integration-log.md) <br/> |통합 로그 얻기 작업은 QoE 큐브 처리의 활동을 설명하는 로그 항목 목록을 반환합니다.  <br/> |
|[마지막 통합 데이터 가져오기](get-last-integration-data.md) <br/> |큐브에서 마지막 통합 데이터를 얻습니다.  <br/> |
   
 **데이터 API에 대한 CORS(원본 간 리소스 공유) 지원**
  
데이터 API는 CORS(원본 간 리소스 공유)를 지원합니다. CORS는 한 도메인에서 실행되는 웹 응용 프로그램이 다른 도메인의 리소스에 액세스할 수 있도록 하는 HTTP 기능입니다. 웹 브라우저는 웹 페이지가 [](https://www.w3.org/Security/wiki/Same_Origin_Policy) 다른 도메인의 API를 호출하지 못하게 하는 동일한 원본 정책과 동일한 원본 정책으로 알려진 보안 제한을 구현합니다. CORS는 한 도메인(원본 도메인)이 다른 도메인의 API를 호출할 수 있도록 안전한 방법을 제공합니다. [CORS에 대한 자세한 내용은 CORS](https://www.w3.org/TR/cors/) 사양을 참조합니다.
  
 **데이터 API에 CORS 사용**
  
 다음은 corsTrustedOrigin 응용 프로그램 web.config 나열된 두 개의 도메인을 보여 주며 데이터 API 응용 프로그램의 발췌문입니다. 이러한 서버에서 로드된 스크립트가 요청하는 모든 요청은 데이터 API에서 신뢰합니다.
  
정확한 프로토콜, 호스트 이름 및 포트(있는 경우)를 포함해야 합니다. 슬래시 문자(/)를 끝에 두지 않습니다. 항목이 여러 개이면 각 항목을 각기 각자 구분하여 지정할 수 있습니다.
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
…  </appSettings>
</configuration>
```


