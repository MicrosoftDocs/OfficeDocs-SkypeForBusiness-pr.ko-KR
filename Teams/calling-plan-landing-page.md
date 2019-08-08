---
title: Microsoft 팀의 통화 계획
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
description: 통화 계획 랜딩 페이지
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83e2516ac9fd142c6cb965539ff22c4900811888
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237176"
---
# <a name="which-calling-plan-is-right-for-you"></a>사용자에 게 적합 한 통화 요금제는 무엇 인가요? 

[시작](get-started-with-teams-quick-start.md)하기를 완료 했습니다. 조직에서 [채팅, 팀, 채널, & 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md) 을 사용 하 여 팀을 롤아웃 했습니다. [모임 & 회의](deploy-meetings-microsoft-teams-landing-page.md)를 배포 했을 수도 있습니다. 이제 클라우드 음성 작업 부하를 추가할 준비가 되었고, 통화 요금제로 Microsoft 전화 시스템을 사용 하 여 PSTN (공개 교환 전화 네트워크)에 연결 하기로 결정 했습니다. 

이 문서에서는 조직의 요구 사항에 따라, 호출 계획에 대 한 핵심 배포 의사 결정과 구성할 수 있는 추가 고려 사항을 설명 합니다. Microsoft의 클라우드 음성 제공에 대 한 자세한 내용은 [Microsoft 팀에서 클라우드 음성을](cloud-voice-landing-page.md) 참조 하세요.


## <a name="learn-more-about-calling-plans"></a>통화 요금제에 대 한 자세한 정보

다음 문서는 Microsoft 통화 계획 배포 및 사용에 대 한 자세한 정보를 제공 합니다.

- [Office 365의 전화 시스템](what-is-phone-system-in-office-365.md)
- [Office 365에 대 한 통화 요금제](calling-plans-for-office-365.md)
- [통화 요금제 설정](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>핵심 배포 결정

Microsoft를 전화 통신 회사로 사용 하려면 통화 요금제 라이선스를 얻고 전화 시스템 사용자에 게 할당 해야 합니다. 

사용할 수 있는 통화 계획에는 두 가지 유형이 있습니다.

- 국내 통화 요금제 
- 국내 및 국제 통화 요금제

|질문 하기|함수 |
|------------|-------|
|내 지역에서 사용 가능한 통화 요금제가 있나요? 요금제 서비스를 호출할 사용자 위치 | 자세한 내용은 [오디오 회의 및 통화 요금제의 국가 및 지역 사용 가능성](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)을 참조 하세요. | 
사용자에 게 국제 통화가 필요 한가요? | 자세한 내용은 [Office 365에 대 한 요금제 호출](calling-plans-for-office-365.md)을 참조 하세요. |
내 사용자가 통화 계획 라이선스를 보유 하 고 있나요? | 라이선스를 구입 하 여 할당 하려면 [2 단계: 라이선스 구입 및 할당](set-up-calling-plans.md#step-2-buy-and-assign-licenses)을 참조 하세요. |
사용자에 게 직접 바로 안쪽 전화 접속 (a) 전화 번호를 사용 하 고 있습니까? | 전화 번호를 얻으려면 [3 단계: 전화 번호 받기를](set-up-calling-plans.md#step-3-get-phone-numbers)참고 하세요. |
|||

### <a name="transfer-phone-numbers-to-office-365"></a>Office 365에 전화 번호 전송

현재 서비스 공급자에서 팀으로 전화 번호를 쉽게 전송할 수 있습니다. 전화 번호를 팀으로 이식 하면 Microsoft가 서비스 공급자가 되며 해당 전화 번호로 청구 됩니다. 자세한 내용은 [Office 365으로 전화 번호 전송을](transfer-phone-numbers-to-office-365.md)참조 하세요.


### <a name="phone-numbers-and-emergency-locations"></a>전화 번호 및 비상 위치

Office 365의 통화 요금제를 사용 하는 경우 조직의 모든 사용자에 게 고유한 직접 안쪽 전화 접속 (a) 전화 번호 및 해당 하 고 확인 된 긴급 주소가 있어야 합니다. 긴급 주소 내에서 비상 위치 (예: 사무실 번호 또는 바닥 번호)를 지정할 수도 있습니다. 

|질문 하기|함수 |
|:------------|:-------|
|긴급 주소 및 위치 정보를 자세히 확인 하려면 어떻게 하나요? |자세한 내용은 [긴급 위치, 주소 및 통화 라우팅 이란?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)을 참조 하세요.


### <a name="calling-identity"></a>통화 id

기본적으로 모든 아웃 바운드 통화는 지정 된 전화 번호를 통화 id (발신자 ID)로 사용 합니다. 통화를 받는 사람은 발신자를 빠르게 확인 하 고 통화 수락 또는 거부 여부를 결정할 수 있습니다.

|질문 하기|함수 |
|:------------|:-------|
|발신자 ID를 마스킹 또는 사용 하지 않도록 설정 하 시겠습니까? | 발신자 ID를 변경 하거나 차단 하려면 [사용자의 발신자 Id 설정을](set-the-caller-id-for-a-user.md)참조 하세요. |
|||




