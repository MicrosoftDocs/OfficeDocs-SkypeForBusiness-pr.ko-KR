---
title: CQD (통화 품질 대시보드)에 대 한 사용자 설정 서비스
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
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: '요약: 통화 품질 대시보드의 리포지토리 API의 일부인 사용자 설정 서비스에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 1eef869523bf1590a00ca199727b33ec9e13ccba
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816647"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>CQD (통화 품질 대시보드)에 대 한 사용자 설정 서비스
 
**요약:** 통화 품질 대시보드의 리포지토리 API에 포함 된 사용자 설정 서비스에 대해 알아봅니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
사용자 설정 서비스는 통화 품질 대시보드의 리포지토리 API의 일부입니다.
  
## <a name="user-settings-service"></a>사용자 설정 서비스

사용자 설정은 응용 프로그램이 다양 한 용도에 대 한 메타 데이터를 저장 하는 데 사용할 수 있는 키-값 쌍으로, 사용자별 사용자 단위를 기반으로 합니다. 각 사용자는 사용자 설정 저장소를 받습니다. 소유자만 사용자 설정을 추가, 수정 및 제거할 수 있습니다.
  
 **전역 설정**
  
전역 설정은 시스템 사용자가 소유한 사용자 설정 이며, 모든 사용자는 읽기 전용 권한이 있습니다. 전역 설정은 저장소를 만드는 동안 만들어지고 변경 되지 않는 상수입니다.
  
각 사용자는 동일한 키를 사용 하 여 사용자 설정을 만들어 전역 설정을 재정의할 수 있습니다. 응용 프로그램이 유효한 사용자 설정을 요청할 때 API는 사용자 설정에 병합 된 전역 설정 집합을 반환 하 고, 각 사용자 설정이 각 전역 설정을 대체 합니다 (키가 동일한 경우). 또한 API는 응용 프로그램에서 재정의 되는 설정을 찾을 수 있도록 사용자 설정만 반환할 수 있습니다. 
  
미삭 작업은 다음 표에 나와 있습니다.

|**작업**|**설명**|
|:-----|:-----|
|[사용자 설정 가져오기](get-user-settings.md) <br/> |사용자 설정 가져오기 지정 된 사용자에 대 한 설정 목록을 반환 합니다.  <br/> |
|[사용자 설정 가져오기](get-user-setting.md) <br/> |사용자 설정 가져오기 단일 사용자 설정을 반환 합니다.  <br/> |
   

