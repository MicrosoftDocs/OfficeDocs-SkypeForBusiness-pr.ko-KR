---
title: Microsoft Teams에서 통화 계획
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
description: Teams의 Cloud Voice에서 조직에 가장 적합한 Microsoft 전화 시스템 통화 계획을 결정하십시오.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 71fe92646a3a2976e9a4d393e54ea56a7669b400
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031854"
---
# <a name="which-calling-plan-is-right-for-you"></a>사용자에게 적합한 통화 플랜은 무엇인가요? 

시작을 [완료합니다.](get-started-with-teams-quick-start.md) 조직 전체에서 [채팅, 팀, 채널 및 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md)이 포함된 Teams를 배포했습니다. 회의에 모임을 & [수도 있습니다.](deploy-meetings-microsoft-teams-landing-page.md) 이제 클라우드 음성 워크로드를 추가할 준비가 됐고, PSTN(공용 전화망)에 연결하기 위해 통화 계획과 함께 Microsoft Phone System을 사용하기로 결정했습니다. 

이 문서에서는 통화 계획에 대한 핵심 배포 결정과 조직의 요구에 따라 구성하려는 추가 고려 사항을 설명합니다. 또한 Microsoft의 클라우드 음성 제안에 대한 자세한 내용은 [Microsoft Teams의](cloud-voice-landing-page.md) Cloud Voice를 읽어야 합니다.


## <a name="learn-more-about-calling-plans"></a>통화 요금제에 대해 자세히 알아보기

다음 문서에서는 Microsoft 통화 요금제 배포 및 사용에 대한 자세한 정보를 제공합니다.

- [Microsoft 365 또는 Office 365의 전화 시스템](what-is-phone-system-in-office-365.md)
- [Microsoft 365 또는 Office 365용 통화 요금제](calling-plans-for-office-365.md)
- [통화 플랜 설정](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a>핵심 배포 결정사항

Microsoft를 통신사로 사용하려면 통화 요금제 라이선스를 획득하여 전화 시스템 사용자에게 할당해야 합니다. 

사용할 수 있는 통화 요금제에는 두 가지 유형이 있습니다.

- 국내 통화 요금제 
- 국내 및 국제 통화 요금제

|본인에게 질의하기|작업 |
|------------|-------|
|통화 요금제는 내 지역에서 사용할 수 있나요? 통화 요금제 서비스를 사용할 사용자 위치는 무엇입니까? | 자세한 내용은 오디오 회의 및 통화 요금제에 대한 국가 및 지역 [가용성을 참조하세요.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md) | 
내 사용자에게 국제 통화가 필요한가요? | 자세한 내용은 [Microsoft 365 또는 Office 365에](calling-plans-for-office-365.md)대한 통화 요금제를 참조하세요. |
내 사용자에게 통화 요금제 라이선스가 있나요? | 라이선스를 구입하고 할당하기 위해 2단계: 라이선스 구입 [및 할당을 참조합니다.](set-up-calling-plans.md#step-2-buy-and-assign-licenses) |
각 사용자에게는 DID(직접 전화 번호) 전화 번호가 있나요? | 전화 번호를 얻습니다. [3단계: 전화 번호 보기를 참조합니다.](set-up-calling-plans.md#step-3-get-phone-numbers) |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>Microsoft 365 또는 Office 365로 전화 번호 이전

현재 서비스 공급자에서 Teams로 전화 번호를 쉽게 전송할 수 있습니다. 전화 번호를 Teams로 포식하면 Microsoft가 서비스 공급자가 되고 해당 전화 번호에 대한 요금을 청구합니다. 자세한 내용은 Teams로 전화 [번호 이전을 참조하세요.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)


### <a name="phone-numbers-and-emergency-locations"></a>전화번호와 긴급 위치

Microsoft 365 또는 Office 365의 통화 요금제에서는 조직의 모든 사용자에게 고유한 DID(직접 전화 번호) 전화 번호와 확인된 해당 긴급 주소가 필요합니다. 긴급 주소 내에서 긴급 위치(예: 사무실 번호 또는 층 번호)를 지정할 수도 있습니다. 

|본인에게 질의하기|작업 |
|:------------|:-------|
|긴급 주소 및 위치 정보를 얼마나 자세히 원하나요? |자세한 내용은 긴급 [위치,](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)주소 및 통화 라우팅이란?


### <a name="calling-identity"></a>ID 호출

기본적으로 모든 아웃바운드 호출은 발신자 ID(발신자 ID)로 할당된 전화 번호를 사용하게 됩니다. 전화 수신자는 발신자를 빠르게 확인하고 통화를 수락할지 거부할지를 결정할 수 있습니다.

|본인에게 질의하기|작업 |
|:------------|:-------|
|호출자 ID를 마스킹하거나 사용하지 않도록 설정하나요? | 발신자 ID를 변경하거나 차단하는 경우 사용자의 호출자 [ID 설정을 참조합니다.](set-the-caller-id-for-a-user.md) |
|||




