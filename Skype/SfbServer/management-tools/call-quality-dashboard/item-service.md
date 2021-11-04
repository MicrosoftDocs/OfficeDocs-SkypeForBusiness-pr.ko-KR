---
title: CQD(통화 품질 대시보드)에 대한 항목 서비스
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
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: '요약: 통화 품질 대시보드에 대한 리포지토리 API의 일부인 항목 서비스에 대해 자세히 알아보습니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.'
ms.openlocfilehash: a0a6ddc923ebf55e5b11ea794398286ca1d19728
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60760606"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>CQD(통화 품질 대시보드)에 대한 항목 서비스
 
**요약:** 통화 품질 대시보드에 대한 리포지토리 API의 일부인 항목 서비스에 대해 자세히 알아보습니다. 통화 품질 대시보드는 통화 품질 대시보드를 위한 비즈니스용 Skype 서버.
  
항목 서비스는 통화 품질 대시보드용 리포지토리 API의 일부입니다.
  
## <a name="item-service"></a>항목 서비스

리포지토리 API는 사용자에 대해 응용 프로그램 정의 콘텐츠를 저장하는 데 사용할 수 있는 간단한 콘텐츠 관리 서비스(항목 서비스)를 제공합니다. 
  
시스템 콘텐츠는 시스템 사용자가 소유하며 읽기 전용 액세스 권한이 있는 모든 사용자가 공유합니다. 전용 사용자 콘텐츠는 일반 사용자가 소유하며 소유자만 해당 콘텐츠를 수정하거나 삭제할 수 있지만 모든 사용자는 여전히 읽기 전용으로 액세스할 수 있습니다.
  
> [!NOTE]
> 이 API 설명서에는 리포지토리 API의 읽기 전용 작업이 설명되어 있습니다. 
  
통화 품질 대시보드에서는 보고서 및 쿼리를 리포지토리 데이터베이스에 항목으로 저장합니다. 항목에는 선택적 하위 항목이 있으며, 통화 품질 대시보드는 하위 항목 기능을 사용하여 계층 구조로 보고서 및 쿼리를 구성합니다.
  
항목 서비스에는 다음과 같은 개념이 포함되어 있습니다.
  
- **item** - 리포지토리의 기본 요소입니다. 각 항목은 정확히 한 사용자가 소유합니다.
    
- **하위 항목** - 리포지토리의 기본 조직 역학입니다. 항목에는 0개, 하나 이상의 하위 항목이 있습니다.
    
- **항목** 상위 항목 - 최상위 항목부터 시작하여 지정한 항목으로 이어지는 사용자의 기본 항목입니다.
    
- **항목 콘텐츠** - 항목에 저장된 응용 프로그램별 콘텐츠입니다. 통화 품질 대시보드에서는 보고서 및 쿼리의 JSON 표현을 콘텐츠에 저장합니다.
    
REST 작업은 다음 표에 포함되어 있습니다.
  

|**작업**|**설명**|
|:-----|:-----|
|[항목 가져오기](get-items.md) <br/> |Get Items는 리포지토리의 모든 Items를 반환합니다.  <br/> |
|[항목 가져오기](get-item.md) <br/> |Get Item은 특정 항목을 반환합니다.  <br/> |
|[하위 항목 가져오기](get-sub-items.md) <br/> |Get Sub-Items 항목의 하위 항목을 반환합니다.  <br/> |
|[상위 항목 가져오기](get-item-ancestors.md) <br/> |항목 조상을 구하면 특정 항목의 조상이 반환됩니다.  <br/> |
|[항목 업데이트](update-item.md) <br/> |리포지토리의 특정 항목을 업데이트합니다.  <br/> |
   

