---
title: 스키마 파티션 복제 확인
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: 스키마 확장이 Active Directory 도메인 서비스 포리스트에 성공적으로 복제 되었는지 확인 하려면 다음을 수행 합니다.
ms.openlocfilehash: c8417d4b1df11536f733ad68b1546fb4cf7de0ce
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197408"
---
# <a name="verify-replication-of-schema-partition"></a>스키마 파티션 복제 확인
 
스키마 확장이 Active Directory 도메인 서비스 포리스트에 성공적으로 복제 되었는지 확인 하려면 다음을 수행 합니다.
  
1. 스키마 확장이 엔터프라이즈 관리자 그룹의 구성원으로 적용 된 Active Directory 도메인 서비스 포리스트에서 도메인 컨트롤러 (스키마 마스터 역할을 보유 하는 도메인 컨트롤러 제외)에 로그온 합니다.
    
2. ADSI 편집 열기: **시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **adsi 편집**을 클릭 합니다.
    
    > [!TIP]
    > 또는 **시작**을 클릭 하 고 **실행**을 클릭 한 다음 **ADSIEDIT** 를 입력 하 여 ADSI 편집을 시작 합니다.
  
3. MMC (Microsoft Management Console) 트리에서 아직 선택 하지 않은 경우 ADSI 편집을 클릭 합니다.
    
4. **작업** 메뉴에서 **연결 대상**을 클릭 합니다.
    
5. **연결 설정** 대화 상자의 **잘 알려진 명명 컨텍스트 선택**에서 **스키마**를 선택한 다음 **확인**을 클릭 합니다.
    
6. 스키마 컨테이너 아래에서 CN = ms-RTC-SIP-SchemaVersion을 검색 합니다. 이 개체가 존재 하 고, **Range upper** 특성의 값이 1150이 고, **range lower** 특성의 값이 3 이면 스키마가 성공적으로 업데이트 되 고 복제 된 것입니다. 이 개체가 존재 하지 않거나, **Range upper** 및- **lower** 특성 값이 지정 되지 않은 경우 스키마는 수정 되거나 복제 되지 않은 것입니다.
    
> [!NOTE]
> 스키마 복제 검사에서 아직 복제에 실패 한 경우 약 15 분 후에 다시 확인 합니다. Active Directory 복제는 일관성을 유지 하는 모델을 기반으로 하며, 서버와 인프라의 여러 요인에 따라 일부 복제 대기 시간이 발생할 수 있습니다. 
  

