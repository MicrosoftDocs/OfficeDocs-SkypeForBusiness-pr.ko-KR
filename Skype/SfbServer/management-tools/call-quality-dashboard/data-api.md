---
title: 비즈니스용 Skype 서버 CQD(통화 품질 대시보드)용 데이터 API
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 25c2450a-f7b3-4dd2-987d-64f4246dd019
description: '요약: 통화 품질 대시보드에 대한 데이터 API에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버 위한 도구입니다.'
ms.openlocfilehash: 3204398dcf667f785f1efe71cc4d6dc5478ce54d
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675740"
---
# <a name="data-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>비즈니스용 Skype 서버 CQD(통화 품질 대시보드)용 데이터 API
 
**요약:** 통화 품질 대시보드에 대한 데이터 API에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버 위한 도구입니다.
  
Data API는 비즈니스용 Skype 서버 통화 품질 대시보드에 대한 프로그래밍 방식 액세스를 제공합니다.
  
## <a name="data-api-for-call-quality-dashboard"></a>통화 품질 대시보드용 데이터 API

Data API는 QoE 큐브에 대한 쿼리 인터페이스를 제공합니다. Data API는 지정된 차원 및 필터를 기반으로 집계된 QoE 메트릭을 제공하는 다차원 데이터베이스를 사용하기 위한 REST API입니다.
  
REST 작업은 다음 표에 포함되어 있습니다.
  

|**작업**|**설명**|
|:-----|:-----|
|[큐브 가져오기](get-cube.md) <br/> |사용 가능한 차원 및 측정값 목록을 가져옵니다.  <br/> |
|[차원 구성원 가져오기](get-dimension-members.md) <br/> |차원 멤버 가져오기 작업은 특정 차원의 멤버 목록을 반환합니다. 또한 멤버 목록을 필터링하고 하위 집합을 가져와 전신 전송 비용을 줄이는 기능도 제공합니다.  <br/> |
|[쿼리 실행](run-query.md) <br/> |쿼리 실행 작업은 지정된 차원, 측정값 및 필터를 기반으로 큐브에서 쿼리를 실행하고 데이터를 다시 반환하는 기능을 제공합니다.  <br/> |
|[캐시 지우기](clear-cache.md) <br/> |캐시 지우기 작업은 쿼리 및 데이터에 대한 서버의 캐시를 삭제합니다. 그러면 캐시가 다시 설정되고 나중에 QoE Cube에서 새 요청에 대한 새 데이터를 가져옵니다.  <br/> |
|[통합 로그 가져오기](get-integration-log.md) <br/> |통합 로그 가져오기 작업은 QoE 큐브 처리의 활동을 설명하는 로그 항목 목록을 반환합니다.  <br/> |
|[마지막 통합 데이터 가져오기](get-last-integration-data.md) <br/> |큐브에서 마지막 통합 데이터를 가져옵니다.  <br/> |
   
 **데이터 API에 대한 CORS(원본 간 리소스 공유) 지원**
  
Data API는 CORS(원본 간 리소스 공유)를 지원합니다. CORS는 한 도메인에서 실행되는 웹 애플리케이션이 다른 도메인의 리소스에 액세스할 수 있도록 하는 HTTP 기능입니다. 웹 브라우저는 웹 페이지가 다른 도메인의 API를 호출하지 못하도록 하는 [동일 원본 정책](https://www.w3.org/Security/wiki/Same_Origin_Policy) 동일 원본 정책이라고 하는 보안 제한을 구현합니다. CORS는 한 도메인(원본 도메인)이 다른 도메인에서 API를 호출하도록 허용하는 안전한 방법을 제공합니다. CORS에 대한 자세한 내용은 [CORS 사양](https://www.w3.org/TR/cors/) 을 참조하세요.
  
 **데이터 API에 CORS 사용**
  
 다음은 corsTrustedOrigin 애플리케이션 설정에 나열된 두 개의 도메인을 보여 주는 Data API web.config 발췌한 것입니다. 이러한 서버에서 로드된 스크립트에서 수행한 모든 요청은 Data API에서 신뢰할 수 있습니다.
  
정확한 프로토콜, 호스트 이름 및 포트(있는 경우)를 포함해야 합니다. 끝에 슬래시 문자(/)를 넣지 마세요. 쉼표로 구분하여 여러 항목을 지정할 수 있습니다.
  
```xml
<configuration>
  <appSettings>
    <add key="corsTrustedOrigin" value="https://<trusted-server>,http://<another-trusted-domain>:8080" /> <!-- Domains which are trusted to get the data -->
    <add key="QoEDataLib.DebugMode" value="True" /> <!-- Setting this to True, allows seeing of the detail logs in status page -->
...  </appSettings>
</configuration>
```


