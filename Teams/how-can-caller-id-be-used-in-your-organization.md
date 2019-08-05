---
title: 조직에서 발신자 ID를 사용 하는 방법
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: 발신자 ID는 CallingLineIdentity 이라는 정책을 사용 하 여 전화 시스템 사용자에 대 한 인바운드와 아웃 바운드 호출 모두에 대해 제어할 수 있습니다.
ms.openlocfilehash: c0cd798f7aaed3b513db9d74fc52d458b9d17078
ms.sourcegitcommit: bf7de2101862a154eb375c06bc89e6e0c4872119
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2019
ms.locfileid: "36183542"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>조직에서 발신자 ID를 사용 하는 방법

발신자 ID는 CallingLineIdentity 이라는 정책을 사용 하 여 전화 시스템 사용자에 대 한 인바운드와 아웃 바운드 호출 모두에 대해 제어할 수 있습니다.
  
모든 휴대폰 시스템 사용자는 PSTN 연결에 관계 없이 발신자 ID 기능을 사용할 수 있습니다.
  
- 온라인 PSTN 연결
    
- 비즈니스용 Skype 클라우드 Connector Edition에서 온-프레미스 PSTN 연결 (Cloud Connector Edition 1.4.2 이상 필요)
    
- 비즈니스용 Skype 서버에 온-프레미스 PSTN 연결 (비즈니스용 Skype Server 2015 CU5 이상 필요)
    
> [!NOTE]
> 이 정책은 비즈니스용 Skype 2015 서버에서 사용할 수 없습니다. 
  
## <a name="outbound-caller-id"></a>아웃 바운드 발신자 ID

아웃 바운드 PSTN 발신자 ID에 사용할 수 있는 세 가지 옵션이 있습니다.
  
- 사용자에 게 할당 된 전화 번호입니다 (기본값).
    
- Office 365 전화 번호 인벤토리에 있는 통화 요금제에서 *서비스* 및 무료 번호로 분류 된 전화 번호입니다. ** 일반적으로 조직 자동 전화 교환 또는 통화 대기열에 할당 됩니다.
    
- 익명으로 설정 합니다.
    
그러나 아웃 바운드 발신자 ID에 대해 이러한 유형의 전화 번호를 지정할 수는 없습니다.
  
- 통화 요금제 전화 번호 인벤토리에서 *사용자* 로 분류 된 모든 전화 번호
    
- 비즈니스용 Skype Server 온-프레미스 전화 번호
    
아웃 바운드 발신자 ID를 설정 하려면 [사용자의 발신자 Id 설정을](/microsoftteams/set-the-caller-id-for-a-user)참조 하세요.
  
### <a name="end-user-control-of-outbound-caller-id"></a>아웃 바운드 발신자 ID의 최종 사용자 제어

EnableUserOverride 특성을 사용 하면 단일 또는 여러 사용자가 자신의 발신자 ID 설정을 **익명**으로 변경할 수 있습니다. 이는 CallingLineIdentity 정책이 LineURI 또는 대체의 Callingidin매개 변수를 사용 하 여 구성 된 경우에만 적용 됩니다. EnableUserOverride의 기본값은 False입니다.
  
최종 사용자는 비즈니스용 Skype 데스크톱 클라이언트의 **설정** 탭을 사용 하 여 발신자 ID를 **익명** 으로 설정 하 고, **최종 사용자** 에 게 전화 걸기 (관리자가 사용 하도록 설정한 경우)를 선택 하려면 **모든 통화에 대해 내 전화 번호 및 프로필 정보 숨기기를 선택 합니다. **.
  
||||
|:-----|:-----|:-----|
|**창을** <br/> |**버전** <br/> |**지원** <br/> |
|간편 실행  <br/> |12 월 6 일에 릴리스된 현재 채널 2016-버전 1611 (빌드 7571.2072)  <br/> |'  <br/> |
|간편 실행  <br/> |2 월 22 일에 릴리스된 지연 채널의 첫 번째 릴리스 2017-버전 1701 (빌드 7766.2060)  <br/> |'  <br/> |
|간편 실행  <br/> |6 월 13 일에 릴리스된 지연 채널 2017-버전 1701 (빌드 7766.2092)  <br/> |'  <br/> |
|MSI  <br/> |비즈니스용 Skype  <br/> |아니요  <br/> |
|Ac  <br/> |비즈니스용 Skype  <br/> |아니요  <br/> |
   
## <a name="inbound-caller-id"></a>인바운드 발신자 ID

BlockIncomingCallerID 특성을 사용 하면 들어오는 PSTN 호출에 대 한 발신자 ID를 차단할 수 있습니다. 이 특성을 설정할 수 있지만 사용자 설정 페이지에서는 최종 사용자가 사용할 수 없습니다. 현재는 온라인 PSTN 연결 에서만 사용할 수 있습니다.
  
아웃 바운드 발신자 ID를 설정 하려면 [사용자의 발신자 Id 설정을](/microsoftteams/set-the-caller-id-for-a-user)참조 하세요.
  
## <a name="related-topics"></a>관련 항목
[전화 번호 전송 일반적인 질문](/microsoftteams/transferring-phone-numbers-common-questions)

[통화 요금제에 사용 되는 다른 종류의 전화 번호](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)

[비상 통화 약관](/microsoftteams/emergency-calling-terms-and-conditions)

[비즈니스용 Skype Online: 비상 전화 부인 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
