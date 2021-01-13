---
title: CQD용 사용자 서비스
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
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: '요약: 통화 품질 대시보드에 대한 리포지토리 API의 일부인 사용자 서비스에 대해 자세히 알아보습니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: d9f4b771a1bf5efeece4f8fb87195d8567f0426e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803078"
---
# <a name="user-service-for-cqd"></a>CQD용 사용자 서비스
 
**요약:** 통화 품질 대시보드에 대한 리포지토리 API의 일부인 사용자 서비스에 대해 자세히 알아보습니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
사용자 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다.
  
## <a name="user-service"></a>사용자 서비스

리포지토리 API는 사용자 프로비전(새 사용자 계정 만들기)이 자동으로 암시적으로 수행되는 간소화된 사용자 관리 모델을 제공합니다. 사용자가 리포지토리 API에 대해 처음으로 요청을 하면 리포지토리에서 새 사용자 레코드를 만듭니다. 
  
통화 품질 대시보드에서는 새 사용자에 대한 사용자 전용 항목도 자동으로 만듭니다. 새 사용자 전용 항목은 시스템 사용자 항목의 완전한 복제본입니다. 이렇게 하면 사용자가 직접 사용자 지정을 시작할 수 있는 보고서 및 쿼리의 복사본으로 시작할 수 있습니다. 
  
> [!NOTE]
> 통화 품질 대시보드를 사용하여 사용자는 언제든지 전용 항목을 다시 설정할 수 있습니다. 
  
 **특수 사용자 ID**
  
리포지토리 API에는 특정 사용자를 지정하는 정수 값이 필요한 REST API URIS가 포함되어 있습니다. 예:  `https://<portal>/QoERepositoryService/repository/user/{userId}` . 여기서 {userId}는 0, 1 등의 정수 값으로 대체해야 합니다.
  
또한 리포지토리 API는 URIS의 {userId}에 두 개의 특수 사용자 ID를 허용합니다.
  
-  *default*  - 현재 API와 상호 작용하고 있는 사용자를 나타내는 경우 이렇게 하면 응용 프로그램에서 실제 사용자 ID 값을 추적하지 않고 현재 사용자의 콘텐츠에 액세스할 수 있습니다. 예: `https://<portal>/QoERepositoryService/repository/user/default` .
    
-  *system*  - 시스템 사용자를 나타 내는 것입니다. 이렇게 하면 응용 프로그램에서 실제 사용자 ID 값을 모르고 시스템 사용자 콘텐츠에 액세스할 수 있습니다. 예: `https://<portal>/QoERepositoryService/repository/user/system` .
    
달리 명시되지 않은 경우 URIS의 {userId}에서 특수 사용자 ID를 사용할 수 있습니다. 
  
REST 작업은 다음 표에 포함되어 있습니다.
  
|**작업**|**설명**|
|:-----|:-----|
|[사용자 가져오기](get-users.md) <br/> |리포지토리에 있는 사용자 목록을 반환합니다.  <br/> |
|[사용자 가져오기](get-user.md) <br/> |사용자 레코드를 반환합니다.  <br/> |
   

