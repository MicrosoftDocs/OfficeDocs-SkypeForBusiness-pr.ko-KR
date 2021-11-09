---
title: 스키마 파티션의 복제 확인
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
ms.localizationpriority: medium
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: Active Directory 도메인 서비스 포리스트에 Schema 확장이 복제된 것을 확인하려면 다음을 완료합니다.
ms.openlocfilehash: ad48543f6b14e3e65750582caa42d050b0c2cd58
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60848001"
---
# <a name="verify-replication-of-schema-partition"></a>스키마 파티션의 복제 확인
 
Active Directory 도메인 서비스 포리스트에 Schema 확장이 복제된 것을 확인하려면 다음을 완료합니다.
  
1. Enterprise Admins 그룹의 구성원으로 적용된 Active Directory 도메인 서비스 포리스트에서 도메인 컨트롤러(스마마 마스터 역할을 보유하는 도메인 컨트롤러가 아님)에 로그온합니다.
    
2. **시작**, **관리 도구** 를 차례로 클릭한 다음 **ADSI 편집** 을 클릭하여 ADSI 편집을 엽니다.
    
    > [!TIP]
    > 또는 **시작**, **실행** 을 차례로 클릭한 다음 **adsiedit.msc** 를 입력하여 ADSI 편집을 시작합니다.
  
3. MMC(Microsoft Management Console) 트리에서 아직 선택되어 있지 않으면 ADSI 편집을 클릭합니다.
    
4. **동작** 메뉴에서 **연결** 을 클릭합니다.
    
5. **잘 알려진 명명 컨텍스트를 선택합니다.** 아래에 있는 **연결 설정** 대화 상자에서 **스키마** 를 선택한 다음 **확인** 을 클릭합니다.
    
6. 스키마 컨테이너 아래에서 CN=ms-RTC-SIP-SchemaVersion을 검색합니다. 이 개체가 있고 **rangeUpper** 특성 값이 1150이고 **rangeLower** 특성 값이 3이면 스키마가 업데이트 및 복제된 것입니다. 이 개체가 없거나 **rangeUpper** 및 **rangeLower** 특성 값이 지정된 대로가 아니면 스키마가 수정되지 않았거나 복제되지 않은 것입니다.
    
> [!NOTE]
> 스키마 복제 확인 시 아직 복제에 성공했음이 표시되지 않으면 약 15분간 기다린 다음 다시 확인하십시오. Active Directory 복제는 느슨한 일관성 모델을 기반으로 하여 서버 및 인프라의 여러 요인에 따라 일부 복제 대기 시간이 발생할 수 있습니다. 
  

