---
title: 조직에서 발신자 ID를 사용하는 방법
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: CallingLineIdentity라는 정책을 사용하여 전화 시스템 사용자의 인바운드 및 아웃바운드 호출에 대해 호출자 ID를 제어할 수 있습니다.
ms.openlocfilehash: cd2074fec3027f1172b6ea681013f53994963cb5
ms.sourcegitcommit: 2874aec7768bb46ed4506c1a2d431841f47190bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "47255451"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a>조직에서 발신자 ID를 사용하는 방법

CallingLineIdentity라는 정책을 사용하여 전화 시스템 사용자의 인바운드 및 아웃바운드 호출에 대해 호출자 ID를 제어할 수 있습니다.
  
호출자 ID 기능은 PSTN 연결에 관계없이 모든 전화 시스템 사용자가 사용할 수 있습니다.

- Microsoft 통화 요금제 

- 전화 시스템 직접 라우팅 
  
- 온라인 PSTN 연결
    
- 비즈니스용 Skype Cloud Connector Edition을 사용하여 프레미스 PSTN 연결(Cloud Connector Edition 1.4.2 이상 필요)
    
- 비즈니스용 Skype Server와의 프레미스 PSTN 연결(비즈니스용 Skype Server 2015 CU5 이상 필요)
    
> [!NOTE]
> 이 정책은 비즈니스용 Skype 2015 서버에서 사용할 수 없습니다. 
  
## <a name="outbound-caller-id"></a>아웃바운드 호출자 ID

아웃바운드 PSTN 호출자 ID에 사용할 수 있는 세 가지 옵션이 있습니다.
  
- 사용자에게 할당된 전화 번호(기본값).
    
- 통화 플랜 전화 번호  인벤토리에서 서비스 및 무료 번호로 분류되는 전화 번호입니다.  일반적으로 조직 자동 전화 회의 또는 통화 큐에 할당됩니다.
    
- 익명으로 설정
    
그러나 아웃바운드 발신자 ID에는 이러한 유형의 전화 번호를 할당할 수 없습니다.
  
- 통화 요금제 전화 번호  인벤토리에서 사용자로 분류된 모든 전화 번호
    
- 비즈니스용 Skype Server-프레미스 전화 번호
    
아웃바운드 호출자 ID를 설정하는 경우 사용자의 [호출자 ID를 참조합니다.](/microsoftteams/set-the-caller-id-for-a-user)
  
### <a name="end-user-control-of-outbound-caller-id"></a>아웃바운드 호출자 ID의 최종 사용자 제어

EnableUserOverride 특성을 사용하면 단일 또는 여러 사용자가 호출자 ID 설정을 익명으로 변경할 수 **있습니다.** 이는 LineURI 또는 Substitute의 CallingIDSubstitute 매개 변수로 CallingLineIdentity 정책이 구성된 경우만 적용됩니다. EnableUserOverride의 기본값은 False입니다.
  
최종 사용자는 비즈니스용 Skype 데스크톱 클라이언트의  설정 탭을 사용하여 발신자  ID를 익명으로 설정하고, 최종 사용자(관리자가 사용하도록 설정한 경우)를 선택한 다음, 모든 통화에 대해 내 전화 번호 및 프로필 정보 숨기기를 선택할 수 **있습니다.**  Teams에서 사용자는 오른쪽 위 모서리에 있는 프로필 사진으로 이동하여 통화 설정을 선택한 다음 발신자 ID 아래에서 모든 통화에 대한 내 전화 번호 및 프로필 정보 숨기기를 선택할  >   **수 있습니다.** 
  
||||
|:-----|:-----|:-----|
|**Windows** <br/> |**버전** <br/> |**지원** <br/> |
|Click-to-Run  <br/> |2016년 12월 6일 릴리스된 현재 채널 - 버전 1611(빌드 7571.2072)  <br/> |예  <br/> |
|Click-to-Run  <br/> |2017년 2월 22일 릴리스된 지연 채널의 첫 번째 릴리스 - 버전 1701(빌드 7766.2060)  <br/> |예  <br/> |
|Click-to-Run  <br/> |2017년 6월 13일 릴리스된 지연 채널 - 버전 1701(빌드 7766.2092)  <br/> |예  <br/> |
|MSI  <br/> |비즈니스용 Skype  <br/> |아니요  <br/> |
|Mac  <br/> |비즈니스용 Skype  <br/> |아니요  <br/> |
   
## <a name="inbound-caller-id"></a>인바운드 호출자 ID

전화 번호가 Azure AD의 사용자와 연결된 경우 전화 시스템에서 외부 전화 번호에 대해 호출된 ID를 보여 주게 됩니다. 전화 번호가 Azure AD에 없는 경우 사용할 수 있는 경우 텔코에서 제공하는 표시 이름이 표시됩니다.

BlockIncomingCallerID 특성은 들어오는 PSTN 호출에서 호출자 ID를 차단할 수 있습니다. 이 특성을 설정할 수 있지만 사용자 설정 페이지에서 최종 사용자가 사용할 수 없습니다. 또한 현재 온라인 PSTN 연결에서만 사용할 수 있습니다.
  
아웃바운드 호출자 ID를 설정하는 경우 사용자의 [호출자 ID를 참조합니다.](/microsoftteams/set-the-caller-id-for-a-user)
  
## <a name="related-topics"></a>관련 항목
[전화 번호 전송 자주 묻는 질문](/microsoftteams/transferring-phone-numbers-common-questions)

[통화 요금제에 사용되는 다양한 종류의 전화 번호](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[조직의 전화 번호 관리](/microsoftteams/manage-phone-numbers-for-your-organization)

[긴급 통화 사용 약관](/microsoftteams/emergency-calling-terms-and-conditions)

[비즈니스용 Skype Online: 긴급 통화 고지 사항 레이블](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 
