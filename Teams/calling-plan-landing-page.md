---
title: Microsoft Teams에서 통화 플랜
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
description: Teams의 Cloud Voice에서 조직에 가장 적합한 Microsoft 전화 시스템 통화 플랜을 결정합니다.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e11c6f6cbb53808ba259afd90420ac9855c9731d
ms.sourcegitcommit: d87991ed2d3e4d70edb048378763a17ff689b710
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2022
ms.locfileid: "66682477"
---
# <a name="which-calling-plan-is-right-for-you"></a>사용자에게 적합한 통화 플랜은 무엇인가요?

[시작을 완료했습니다](get-started-with-teams-quick-start.md). 조직 전체에서 [채팅, 팀, 채널 및 앱](deploy-chat-teams-channels-microsoft-teams-landing-page.md)이 포함된 Teams를 배포했습니다. [모임 & 회의를](deploy-meetings-microsoft-teams-landing-page.md) 배포했을 수도 있습니다. 이제 클라우드 음성 워크로드를 추가할 준비가 되었으며 통화 플랜과 함께 Microsoft Phone System을 사용하여 PSTN(공중 전화망)에 연결하기로 결정했습니다.

이 문서에서는 통화 플랜에 대한 핵심 배포 결정과 조직의 요구 사항에 따라 구성할 수 있는 추가 고려 사항에 대해 설명합니다. [Microsoft의 클라우드 음성](cloud-voice-landing-page.md) 제품에 대한 자세한 내용은 Microsoft Teams의 Cloud Voice를 참조해야 합니다.

## <a name="learn-more-about-calling-plans"></a>통화 플랜에 대해 자세히 알아보기

다음 문서에서는 Microsoft 통화 플랜 배포 및 사용에 대한 자세한 정보를 제공합니다.

- [Microsoft 365 또는 Office 365 전화 시스템](what-is-phone-system-in-office-365.md)
- [Microsoft 365 또는 Office 365 대한 통화 플랜](calling-plans-for-office-365.md)
- [통화 플랜 설정](set-up-calling-plans.md)

## <a name="core-deployment-decisions"></a>핵심 배포 결정사항

Microsoft를 전화 통신 사업자로 사용하려면 통화 플랜 라이선스를 획득하여 전화 시스템 사용자에게 할당해야 합니다.

사용할 수 있는 통화 플랜에는 두 가지 유형이 있습니다.

- 국내 통화 플랜
- 국제 통화 플랜

|본인에게 질의하기|작업 |
|------------|-------|
|내 지역에서 통화 플랜을 사용할 수 있나요? 통화 플랜 서비스가 있는 사용자 위치는 무엇인가요? | 자세한 내용은 [오디오 회의 및 통화 플랜의 국가 및 지역 가용성을 참조하세요](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). |
사용자에게 국제 통화가 필요한가요? | 자세한 내용은 [Microsoft 365 또는 Office 365 대한 통화 플랜](calling-plans-for-office-365.md)을 참조하세요. |
사용자에게 통화 플랜 라이선스가 있나요? | 라이선스를 구입하고 할당하려면 [2단계: 라이선스 구입 및 할당을 참조하세요](set-up-calling-plans.md#step-2-buy-and-assign-licenses). |
내 사용자에게 각각 직접 안쪽 다이얼(DID) 전화 번호가 있나요? | 전화 번호를 얻으려면 [3단계: 전화 번호 가져오기를 참조하세요](set-up-calling-plans.md#step-3-get-phone-numbers). |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a>Microsoft 365 또는 Office 365 전화 번호 전송

현재 서비스 공급자에서 Teams로 전화 번호를 쉽게 전송할 수 있습니다. 전화 번호를 Teams로 이식하면 Microsoft가 서비스 공급자가 되어 해당 전화 번호에 대한 요금을 청구합니다. 자세한 내용은 [Teams로 전화 번호 전송을 참조하세요](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).

### <a name="phone-numbers-and-emergency-locations"></a>전화번호와 긴급 위치

Microsoft 365 또는 Office 365 통화 플랜을 사용하면 조직의 모든 사용자에게 고유한 DID(직접 내부 전화 걸기) 전화 번호와 해당 유효성이 검사된 긴급 주소가 있어야 합니다. 긴급 주소(예: 사무실 번호 또는 바닥 번호) 내에서 긴급 위치를 지정할 수도 있습니다.

|본인에게 질의하기|작업 |
|:------------|:-------|
|긴급 주소 및 위치 정보를 얼마나 자세히 설명하나요? |자세한 내용은 [긴급 위치, 주소 및 통화 라우팅이란?을 참조하세요](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).

### <a name="calling-identity"></a>ID 호출

기본적으로 모든 아웃바운드 통화는 할당된 전화 번호를 호출 ID(발신자 ID)로 사용합니다. 전화 수신자는 발신자를 빠르게 확인하고 통화를 수락할지 거부할지를 결정할 수 있습니다.

|본인에게 질의하기|작업 |
|:------------|:-------|
|호출자 ID를 마스킹하거나 사용하지 않도록 설정하시겠습니까? | 호출자 ID를 변경하거나 차단하려면 [사용자의 호출자 ID 설정을 참조하세요](set-the-caller-id-for-a-user.md). |
|||
