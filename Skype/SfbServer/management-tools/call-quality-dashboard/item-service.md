---
title: CQD (통화 품질 대시보드의 항목 서비스)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: '요약: 통화 품질 대시보드의 리포지토리 API에 포함 된 항목 서비스에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 585ba97d9dedbfcbbd572069a792a121e6156afe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186882"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a>CQD (통화 품질 대시보드의 항목 서비스)
 
**요약:** 통화 품질 대시보드의 리포지토리 API에 포함 된 항목 서비스에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
항목 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다.
  
## <a name="item-service"></a>항목 서비스

리포지토리 API는 사용자를 위해 응용 프로그램 정의 콘텐츠를 저장 하는 데 사용할 수 있는 항목 서비스 라는 간단한 콘텐츠 관리 서비스를 제공 합니다. 
  
시스템 콘텐츠는 시스템 사용자가 소유 하 고 있으며 모든 사용자가 읽기 전용 권한을 사용 하 여 공유 합니다. 전용 사용자 콘텐츠는 일반 사용자에 게 소유 되며, 소유자만 해당 파일을 수정 하거나 삭제할 수 있지만, 모든 사용자에 게는 여전히 읽기 전용 권한이 있습니다.
  
> [!NOTE]
> 이 API 문서는 리포지토리 API의 읽기 전용 작업을 설명 합니다. 
  
통화 품질 대시보드는 보고서 및 쿼리를 리포지토리 데이터베이스의 항목으로 저장 합니다. 항목에는 선택적 하위 항목이 있을 수 있으며, 통화 품질 대시보드는 하위 항목 기능을 사용 하 여 보고서 및 쿼리를 계층 구조로 구성 합니다.
  
항목 서비스에는 다음 개념이 포함 되어 있습니다.
  
- **Item** -리포지토리의 기본 요소입니다. 각 항목은 정확히 한 명의 사용자가 소유 합니다.
    
- **하위 항목** -리포지토리의 기본 조직 메커니즘입니다. 항목에는 0 개 또는 하나 이상의 하위 항목이 있을 수 있습니다.
    
- **Item 상위** 항목-사용자의 기본 항목인 최상위 항목에서 시작 하 여 지정 된 항목으로 이어지는 항목의 목록입니다.
    
- **항목 콘텐츠** -항목에 저장 된 응용 프로그램 관련 콘텐츠입니다. 통화 품질 대시보드는 보고서 및 쿼리의 JSON 표현을 내용에 저장 합니다.
    
미삭 작업은 다음 표에 나와 있습니다.
  

|**작업**|**설명**|
|:-----|:-----|
|[항목 가져오기](get-items.md) <br/> |항목 가져오기 저장소의 모든 항목을 반환 합니다.  <br/> |
|[항목 가져오기](get-item.md) <br/> |항목 가져오기 특정 항목을 반환 합니다.  <br/> |
|[하위 항목 가져오기](get-sub-items.md) <br/> |하위 항목 가져오기 특정 항목의 하위 항목을 반환 합니다.  <br/> |
|[Item 상위 항목 가져오기](get-item-ancestors.md) <br/> |Item 상위 항목 가져오기 특정 항목의 조상을 반환 합니다.  <br/> |
|[항목 업데이트](update-item.md) <br/> |리포지토리의 특정 항목을 업데이트 합니다.  <br/> |
   

