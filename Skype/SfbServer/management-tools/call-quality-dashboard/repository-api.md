---
title: CQD(통화 품질 대시보드)에 대한 리포지토리 API(비즈니스용 Skype 서버
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: d53e990f-1c5f-46d1-9eb1-8396782c2753
description: '요약: 통화 품질 대시보드용 리포지토리 API에 대해 자세히 알아보는 방법을 설명하는 문서입니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.'
ms.openlocfilehash: 21765c4766e7fc729988f2b8ba23241175a96584
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60759700"
---
# <a name="repository-api-for-call-quality-dashboard-cqd-in-skype-for-business-server"></a>CQD(통화 품질 대시보드)에 대한 리포지토리 API(비즈니스용 Skype 서버
 
**요약:** 통화 품질 대시보드용 리포지토리 API에 대해 자세히 알아보습니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.
  
리포지토리 API는 호출 품질 대시보드에 대한 프로그래밍 비즈니스용 Skype 서버.
  
## <a name="repository-api-for-call-quality-dashboard"></a>통화 품질 대시보드용 리포지토리 API

리포지토리 API는 리포지토리 데이터베이스에 대한 데이터 액세스 인터페이스를 제공합니다. 리포지토리를 사용하면 사용자가 사용자에게 의미 있는 방식으로 콘텐츠를 그룹화할 수 있도록 콘텐츠를 트리 또는 그래프 구조로 구성할 수 있습니다. 리포지토리는 리포지토리를 나타내는 기본 제공 사용자인 시스템 사용자와 리포지토리의 권한이 부여된 사용자를 나타내는 일반 사용자의 두 가지 일반 사용자 유형을 지원합니다.
  
리포지토리 API는 다음과 같은 세 가지 일반 서비스로 구성됩니다. 
  
- [CQD용 사용자](user-service.md) 서비스 - 사용자 액세스용입니다.
    
- 항목 및 항목에 저장된 콘텐츠에 액세스하기 위한 [CQD(통화](item-service.md) 품질 대시보드)에 대한 항목 서비스입니다.
    
- [User 설정 Service for Call Quality Dashboard(CQD)](user-settings-service.md) - 사용자 서비스 액세스용 설정.
    
통화 품질 대시보드에서는 리포지토리 API를 사용하여 다음 정보를 관리합니다. 
  
- **User** - 리포지토리에 액세스할 수 있는 사용자의 표현입니다.
    
- **Report** - 리포지토리 항목에 콘텐츠로 저장된 쿼리 목록을 포함
    
- **Query** - 리포지토리 항목에 콘텐츠로 저장된 데이터 API에서 데이터를 검색하는 데 사용됩니다.
    
- **사용자 설정** - 사용자의 선택적 응용 프로그램 동작을 설명합니다.
    
  **리포지토리 API에 대한 CORS(원본 간 리소스 공유) 지원**
  
리포지토리 API는 CORS(원본 간 리소스 공유)를 지원합니다. CORS는 한 도메인에서 실행되는 웹 응용 프로그램이 다른 도메인의 리소스에 액세스할 수 있도록 하는 HTTP 기능입니다. 웹 브라우저는 웹 페이지가 [](https://www.w3.org/Security/wiki/Same_Origin_Policy) 다른 도메인의 API를 호출하지 못하게 하는 동일한 원본 정책과 동일한 원본 정책으로 알려진 보안 제한을 구현합니다. CORS는 한 도메인(원본 도메인)이 다른 도메인의 API를 호출할 수 있도록 안전한 방법을 제공합니다. [CORS에 대한 자세한 내용은 CORS](https://www.w3.org/TR/cors/) 사양을 참조합니다.
  
 **리포지토리 API에 CORS 사용**
  
 다음은 corsTrustedOrigin 응용 프로그램 web.config 나열된 두 개의 도메인을 보여 주며 리포지토리 API 응용 프로그램의 발췌문입니다. 이러한 서버에서 로드된 스크립트가 요청하는 모든 요청은 리포지토리 API에서 신뢰합니다.
  
정확한 프로토콜, 호스트 이름 및 포트(있는 경우)를 포함해야 합니다. 슬래시 문자(/)를 끝에 두지 않습니다. 항목이 여러 개이면 각 항목을 각기 각자 구분하여 지정할 수 있습니다.
  
```xml
<repositoryConfiguration>
    <service corsTrustedOrigin="https://<trusted-server>,http://<another-trusted-domain>:8080"" />
    <diagnostics eventLevel="Verbose" systemLoggedEventLevel="Error">
      <traceLog enabled="true" fileName="repository_trace.log" />
    </diagnostics>
 </repositoryConfiguration>
```


