---
title: Microsoft Teams에서 계획 호출
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: Teams의 Cloud Voice에서 조직에 가장 적합한 Microsoft Phone System 호출 계획을 결정합니다.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b88af706f79dd195e2f9363ff45e586a1123686f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102734"
---
# <a name="which-calling-plan-is-right-for-you"></a>사용자에게 적합한 통화 플랜은 무엇인가요? 

시작 을 [완료한 것입니다.](get-started-with-teams-quick-start.md) 조직 전체에서 [채팅, 팀, 채널 및 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md)이 포함된 Teams를 배포했습니다. 회의 를 통해 [모임을 & 수 있습니다.](deploy-meetings-microsoft-teams-landing-page.md) 이제 클라우드 음성 워크로드를 추가할 준비가 됐고, PSTN(공용 전환 전화 네트워크)에 연결하기 위해 통화 계획과 함께 Microsoft Phone System을 사용하기로 결정했습니다. 

이 문서에서는 호출 계획에 대한 핵심 배포 결정과 조직의 요구에 따라 구성하려는 추가 고려 사항을 설명합니다. Microsoft의 클라우드 음성 제공에 대한 자세한 내용은 [Microsoft Teams의](cloud-voice-landing-page.md) Cloud Voice를 읽어야 합니다.


## <a name="learn-more-about-calling-plans"></a>통화 계획에 대해 자세히 알아보기

다음 문서에서는 Microsoft 호출 요금제 배포 및 사용에 대한 자세한 정보를 제공합니다.

- [Microsoft 365 또는 Office 365의 전화 시스템](what-is-phone-system-in-office-365.md)
- [Microsoft 365 또는 Office 365 요금제 호출](calling-plans-for-office-365.md)
- [통화 플랜 설정](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>핵심 배포 결정사항

Microsoft를 전화 통신 사업자로 사용하려면 전화 요금제 라이선스를 획득하고 휴대폰 시스템 사용자에게 할당해야 합니다. 

사용할 수 있는 통화 계획에는 두 가지 유형이 있습니다.

- 국내 통화 계획 
- 국내 및 국제 통화 계획

|본인에게 질의하기|작업 |
|------------|-------|
|내 지역에서 통화 요금제를 사용할 수 있나요? 통화 계획 서비스가 있는 사용자 위치는 무엇입니까? | 자세한 내용은 오디오 회의 및 통화 계획에 대한 국가 및 지역 [가용성을 참조하세요.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) | 
내 사용자에게 국제 통화가 필요합니까? | 자세한 내용은 [Microsoft 365 또는 Office 365 요금제 호출을 참조하세요.](calling-plans-for-office-365.md) |
내 사용자에게 통화 계획 라이선스가 있나요? | 라이선스를 구입하고 할당하는 경우 2단계: 라이선스 구입 [및 할당을 참조합니다.](set-up-calling-plans.md#step-2-buy-and-assign-licenses) |
각 사용자에게 DID(직접 내선 다이얼) 전화 번호가 있나요? | 전화 번호를 얻은 경우 [3단계: 전화 번호 를 를 참조합니다.](set-up-calling-plans.md#step-3-get-phone-numbers) |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>Microsoft 365 또는 Office 365로 전화 번호 전송

현재 서비스 공급자에서 Teams로 전화 번호를 쉽게 전송할 수 있습니다. 휴대폰 번호를 Teams로 포트한 후 Microsoft는 서비스 공급자가 되고 해당 전화 번호에 대한 요금을 청구합니다. 자세한 내용은 Teams로 [전화 번호 전송을 참조하세요.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)


### <a name="phone-numbers-and-emergency-locations"></a>전화번호와 긴급 위치

Microsoft 365 또는 Office 365에서 통화 계획을 사용할 경우 조직의 모든 사용자는 고유한 직접 전화 번호(DID) 전화 번호와 해당 유효성이 검사된 긴급 주소가 필요합니다. 비상 주소(예: 사무실 번호 또는 바닥 번호) 내에서 응급 위치를 지정할 수도 있습니다. 

|본인에게 질의하기|작업 |
|:------------|:-------|
|긴급 주소 및 위치 정보를 얼마나 자세히 사용하나요? |자세한 내용은 긴급 위치, 주소 및 통화 [라우팅이란? 을 참조하세요.](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)


### <a name="calling-identity"></a>ID 호출

기본적으로 모든 아웃바운드 호출은 할당된 전화 번호를 호출 ID(발신자 ID)로 사용됩니다. 전화 수신자는 발신자를 빠르게 확인하고 통화를 수락할지 거부할지를 결정할 수 있습니다.

|본인에게 질의하기|작업 |
|:------------|:-------|
|발신자 ID를 마스크하거나 사용하지 않도록 설정하나요? | 호출자 ID를 변경하거나 차단하는 경우 사용자에 대한 [발신자 ID 설정 을 참조합니다.](set-the-caller-id-for-a-user.md) |
|||