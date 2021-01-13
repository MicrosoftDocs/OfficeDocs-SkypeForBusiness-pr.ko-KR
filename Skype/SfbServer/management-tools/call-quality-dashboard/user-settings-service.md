---
title: CQD(통화 품질 대시보드)에 대한 사용자 설정 서비스
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
ms.assetid: eafeb54a-2574-415b-b991-a0ff0470d8c3
description: '요약: 통화 품질 대시보드용 리포지토리 API의 일부인 사용자 설정 서비스에 대해 자세히 알아보습니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.'
ms.openlocfilehash: 2b2fc9810f1eceb74974dc105263b0bdcf37ae01
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803039"
---
# <a name="user-settings-service-for-call-quality-dashboard-cqd"></a>CQD(통화 품질 대시보드)에 대한 사용자 설정 서비스
 
**요약:** 통화 품질 대시보드에 대한 리포지토리 API의 일부인 사용자 설정 서비스에 대해 자세히 알아보습니다. 통화 품질 대시보드는 비즈니스용 Skype 서버용 도구입니다.
  
사용자 설정 서비스는 통화 품질 대시보드에 대한 리포지토리 API의 일부입니다.
  
## <a name="user-settings-service"></a>사용자 설정 서비스

사용자 설정은 응용 프로그램이 사용자 기준 응용 프로그램 동작을 사용자 지정하는 등 다양한 목적으로 메타데이터를 저장하는 데 사용할 수 있는 키-값 쌍입니다. 각 사용자는 사용자 설정에 대한 저장소를 수신합니다. 소유자만 사용자 설정을 추가, 수정 및 제거할 수 있습니다.
  
 **전역 설정**
  
전역 설정은 시스템 사용자가 소유한 사용자 설정으로, 모든 사용자가 해당 설정에 대한 읽기 전용 액세스 권한을 습니다. 전역 설정은 상수로, 리포지토리를 만들 때 만들어지며 변경되지 않습니다.
  
각 사용자는 동일한 키로 사용자 설정을 만들어 전역 설정을 다시 만들 수 있습니다. 응용 프로그램에서 유효 사용자 설정을 요청하면 API는 사용자 설정과 병합된 전역 설정 집합을 반환합니다. 각 사용자 설정은 키가 동일한 경우 각 전역 설정이 해당 전역 설정으로 바) 됩니다. 또한 API는 응용 프로그램에서 어떤 설정이 다시 정해진지 찾을 수 있도록 사용자 설정만 반환할 수 있습니다. 
  
REST 작업은 다음 표에 포함되어 있습니다.

|**작업**|**설명**|
|:-----|:-----|
|[사용자 설정 가져오기](get-user-settings.md) <br/> |사용자 설정으로 이동하면 지정된 사용자에 대한 설정 목록이 반환됩니다.  <br/> |
|[사용자 설정 가져오기](get-user-setting.md) <br/> |사용자 설정에서 단일 사용자 설정을 반환합니다.  <br/> |
   

