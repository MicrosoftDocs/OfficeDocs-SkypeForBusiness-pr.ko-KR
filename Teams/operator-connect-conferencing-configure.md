---
title: 운영자 커넥트 회의 구성
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 운영자 회의를 구성하는 커넥트 자세히 알아보도록 합니다.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87358190d919519b39494576a05235df26ad4c7a
ms.sourcegitcommit: be8b820caf4b5a1a91ad444ba93da1df20bf63ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2021
ms.locfileid: "61257525"
---
# <a name="configure-operator-connect-conferencing"></a>운영자 커넥트 회의 구성

이 문서에서는 조직 및 사용자에 대한 연산자 커넥트 회의를 구성하는 방법을 자세히 설명합니다.

운영자 커넥트 회의를 구성하기 전에 이점 [및](operator-connect-conferencing-plan.md) 라이선스 요구 사항에 대한 커넥트 운영자 회의 계획을 읽어보아야 합니다.

이 문서에서 다루는 항목은 다음과 같습니다.

- [연산자 설정](#set-up-an-operator)
- [오디오 회의 브리지에 대한 번호 획득](#acquire-numbers-for-your-audio-conferencing-bridge)
- [사용자의 모임 초대에 포함된 기본 전화 번호 변경](#change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users)
- [운영자 Microsoft Teams 모임에서 아웃바운드 호출 보내기](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator)
- [운영자 관리](#manage-your-operators)
- [오디오 회의 브리지에서 릴리스 번호](#release-numbers-from-your-audio-conferencing-bridge)
- [Microsoft 오디오 회의 관리에 대한 추가 정보](#additional-information-on-managing-microsoft-audio-conferencing)

## <a name="set-up-an-operator"></a>연산자 설정

관리 센터에서 연산자를 설정, 편집 및 Teams 수 있습니다. 왼쪽 탐색 창에서 Voice **> 연산자로 이동합니다.**

연산자를 설정하는 경우:

1. **연산자를 선택 합니다.**   모든  **연산자 탭에서** 지역 또는 서비스별로 사용 가능한 연산자를 필터링하여 음성 요구에 적합한   연산자를 찾습니다. 그런 다음 사용할 연산자를 선택합니다. 연산자 커넥트 회의의 경우 운영자가 사용 가능한  제품으로 나열된 회의가 있는지 확인해야 합니다.

2. **국가를 선택합니다.**   연산자  **설정에서** 선택한 연산자를 사용하여 사용하도록 설정할 국가를 선택합니다.

3. **연락처 정보 제공**   전체 이름 및 전자 메일 주소를 포함한 연락처 정보는 운영자와 공유됩니다. 나중에 이 정보를 변경할 수 있습니다. 또한 전화 번호를 제공하는 옵션과 함께 회사 크기를 제공해야 합니다. 운영자는 이 정보를 사용하여 운영자 회의에 대한 자세한 커넥트 연락합니다.

4. 데이터 전송 알림에 동의합니다.

5. **연산자를 추가합니다.**   저장할  **연산자로 추가를**   선택합니다.

## <a name="acquire-numbers-for-your-audio-conferencing-bridge"></a>오디오 회의 브리지에 대한 번호 획득

조직의 오디오 회의 브리지에는 조직의 모든 사용자가 PSTN 전화 번호로 모임에 참가할 수 Microsoft Teams 전화 번호가 포함됩니다. 회의 및 회의 브리지에서 조직의 오디오 회의 브리지와 연결된 전화 Teams 관리 센터에서 > **수 있습니다.**

오디오 회의 브리지의 전화 번호를 획득하기 위해 다음 단계를 수행합니다.

1. **오디오 회의 표준 구독 또는 운영자 커넥트 라이선스입니다.** 운영자 커넥트 회의 번호가 필요한 사용자는 모임에 참가하려면 오디오 회의 표준 구독 라이선스 또는 운영자 회의 라이선스가 할당된 커넥트 필요합니다. 자세한 내용은 운영자 및 회의 커넥트 [를 참조하세요.](operator-connect-conferencing-plan.md)

2. **숫자를 획득합니다.**   전화 번호를 주문하고 획득하기 위해 운영자의 웹 사이트로 이동하세요. 운영자 웹 사이트 목록은 Microsoft 365 운영자 커넥트 [로 이동하세요.](https://cloudpartners.transform.microsoft.com/practices/microsoft-365-for-operators/directory) 테넌트 ID를 제공해야 합니다. 테넌트 ID를 모르는 경우 테넌트 ID [찾기를 Microsoft 365 참조합니다.](/onedrive/find-your-office-365-tenant-id) 운영자가 주문을 완료하면 테넌트에 번호를 업로드합니다. Voice Teams 번호로 Teams 관리 센터에서 숫자 및 공급자를 볼 **> 전화 있습니다.**

3. **오디오 회의 브리지에 번호를 할당합니다.** 오디오 회의 브리지에 숫자를 할당할 수 있습니다. Teams 회의 > 관리 센터에서 > **있습니다.** 자세한 내용은 오디오 회의 브리지의 전화 번호 [변경을 참조하세요.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md)

>[!NOTE]
>연산자 커넥트 번호는 브리지의 기본 번호로 할당할 수 없습니다. 전화 번호가 오디오 회의 브리지에 할당된 후 전화 번호는  오디오 회의 라이선스 또는 운영자 회의 라이선스가 있는 조직의 사용자의 모임 초대에 포함된 로컬 번호 찾기 페이지에 커넥트 표시됩니다.
>
>연산자를 통해 아웃바운드 [**호출을**](#sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator) 라우팅하는 Teams 모임에서 아웃바운드 호출 보내기 섹션을 참조하세요.

## <a name="change-the-default-phone-numbers-that-are-included-in-the-meeting-invites-of-users"></a>사용자의 모임 초대에 포함된 기본 전화 번호 변경

 이 단계는 선택 사항입니다.

사용자의 기본 전화 번호는 모임을 예약할 때 모임 초대에 포함된 전화 번호입니다. 사용자 관리 에서 사용자 관리 Teams 사용자 모임 초대에 포함된 > **수 있습니다.** 사용자의 모임 초대에 포함된 전화 번호를 업데이트하려면 사용자를 선택하고  오디오 회의 섹션에서 편집을 **선택합니다.**

변경 내용이 적용된 후 이끌이의 새 모임 초대에는 새 기본 전화 번호가 포함됩니다. 그러나 변경 전에 예약된 기존 모임 초대는 원래 기본 번호를 유지하게 됩니다.

## <a name="sending-outbound-calls-from-microsoft-teams-meetings-through-an-operator"></a>운영자 Microsoft Teams 모임에서 아웃바운드 호출 보내기

Microsoft 오디오 회의 표준 구독 또는 운영자 커넥트 회의 라이선스가 있는 경우 오디오 회의 라우팅 정책을 설정하여 Teams 모임에서 아웃바운드 호출의 전체 또는 집합을 라우팅하도록 오디오 회의 서비스를 구성할 수 있습니다.

>[!NOTE]
>운영자 커넥트 회의 라이선스를 사용하여 아웃바운드 호출은 연산자를 통해서만 진행할 수 있습니다. 운영자 회의 라이선스가 커넥트 있는 경우 아래 설명된 바와 같이 서비스를 구성하여 모임에서 전화 Teams 아웃바운드 호출을 사용하도록 설정해야 합니다.

사용자 수준에서 오디오 회의 라우팅 정책을 적용할 수 있습니다. 즉, 운영자는 연결된 정책을 사용하여 사용자가 구성한 Teams 아웃바운드 호출만 라우팅합니다. 이러한 정책을 전역 수준에서 적용할 수도 있습니다. 즉, 운영자는 조직의 모든 사용자가 구성한 Teams 아웃바운드 호출을 라우팅합니다.

PowerShell을 사용하여 조직의 새 오디오 회의 라우팅 정책을 만들 수 있습니다. 운영자 를 모임에서 아웃바운드 호출의 기본 경로로 지정 Teams PowerShell 명령을 사용하여 아래 단계를 따릅니다.

1. [1단계: 온라인 PSTN 사용 정책에 새 문자열 추가](#step-1-add-a-new-string-to-the-online-pstn-usage-policy)
2. [2단계: 새 온라인 음성 경로 정책 만들기](#step-2-create-a-new-online-voice-route-policy)
3. [3단계: 새 온라인 오디오 회의 라우팅 정책 만들기](#step-3-create-a-new-online-audio-conferencing-routing-policy)
4. [4단계: 사용자에게 새 정책 할당](#step-4-assign-the-new-policy-to-users)

### <a name="step-1-add-a-new-string-to-the-online-pstn-usage-policy"></a>1단계: 온라인 PSTN 사용 정책에 새 문자열 추가

이 cmdlet 사용에 대한 자세한 내용은 [Set-CsOnlinePstnUsage를](/powershell/module/skype/set-csonlinepstnusage) 읽습니다.

```powershell
Set-CsOnlinePstnUsage -Identity Global -Usage @{Add="International"}
```

### <a name="step-2-create-a-new-online-voice-route-policy"></a>2단계: 새 온라인 음성 경로 정책 만들기

이 cmdlet 사용에 대한 자세한 내용은 [Set-CsOnlineVoiceRoute를](/powershell/module/skype/set-csonlinevoiceroute) 읽습니다.

```powershell
New-CsOnlineVoiceRoute -Identity "International" -NumberPattern "\d+" -OnlinePstnUsages "International" -BridgeSourcePhoneNumber <an Operator Connect Conferencing number assigned to your Audio Conferencing bridge>
```

### <a name="step-3-create-a-new-online-audio-conferencing-routing-policy"></a>3단계: 새 온라인 오디오 회의 라우팅 정책 만들기

```powershell
New-CsOnlineAudioConferencingRoutingPolicy "International Policy" -OnlinePstnUsages "International"
```

### <a name="step-4-assign-the-new-policy-to-users"></a>4단계: 사용자에게 새 정책 할당

```powershell
Grant-CsOnlineAudioConferencingRoutingPolicy -Identity <identity of the organizer of the meeting> -PolicyName "International Policy”
```

>[!NOTE]
>오디오 회의 라우팅 정책을 전역으로 설정하고 조직의 모든 사용자에게 적용하기 위해 매개 변수 대신 매개 변수를 사용할 ``-Global`` 수 ``-Identity`` 있습니다. 예를 ``Grant-CsOnlineAudioConferencingRoutingPolicy -Global -PolicyName "International Policy”`` 들어.

오디오 회의 라우팅 정책을 만들고 사용자에게 적용하면 매개 변수 경로에 지정된 전화 번호를 제공하는 Teams ``BridgeSourcePhoneNumber`` PSTN 전화 번호로 아웃바운드 호출합니다. 또한 매개 변수는 PSTN 전화 번호에 대한 아웃바운드 호출의 전화 번호로 사용할 전화 번호를 ``BridgeSourcePhoneNumber`` 지정합니다.

에 지정된 패턴은 regex 형식입니다. 연산자를 통해 라우팅할 ``NumberPattern`` 호출을 지정합니다. 위의 예제의 패턴은 모든 아웃바운드 호출과 Teams ``"\d+"`` 일치합니다. NumberPattern 매개 변수를 으로 설정할 수 있습니다. 이는  ``“^\+1(425|206)(\d{7})$”`` +1 425 XXX 또는 +1 206 XXX 또는 ``“^\+1(\d{10})$”`` +1 425 XXX XX 형식과 일치하는 전화 번호와 일치합니다.

사용자에게 오디오 회의 라우팅 정책을 할당하면 해당 모임에서 운영자를 통해 오디오 회의 라우팅 정책 경로에 지정된 regex와 일치하는 전화 번호로 모든 통화(다른  사용자 초대를 통해 시작된  통화 및 전화 걸기 또는 번호 모임 옵션 전화 걸기)

## <a name="manage-your-operators"></a>운영자 관리

내 연산자 **탭에서** 연산자, 해당 상태를 보고 선택 내용을 변경할   수 있습니다.

- 국가에 의해 운영자 서비스 관리
- 연산자 일시 중단
- 연산자 제거

>[!NOTE]
>조직 또는 국가에서 연산자를 제거하기 전에 사용자 및 오디오 회의 브리지에 할당된 모든 전화 번호를 제거한 다음 운영자에게 문의하여 번호를 해제해야 합니다.

## <a name="release-numbers-from-your-audio-conferencing-bridge"></a>오디오 회의 브리지에서 릴리스 번호

오디오 회의 브리지에서 전화 번호를 Teams 관리 센터에서 전화 번호를  해제하려면 오디오 회의 브리지의 전화 번호 변경에서 회의 브리지에 대한 서비스 전화 번호를 할당하지 않는 경우 단계를 [참조하세요.](change-the-phone-numbers-on-your-audio-conferencing-bridge.md#steps-when-you-are-unassigning-a-service-phone-number-for-a-conferencing-bridge)

## <a name="additional-information-on-managing-microsoft-audio-conferencing"></a>Microsoft 오디오 회의 관리에 대한 추가 정보

조직의 Microsoft 오디오 회의를 관리하는 방법에 대한 자세한 내용은 다음 문서를 참조하세요.

- 조직의 Microsoft 오디오 회의 서비스 설정 [관리:](manage-the-audio-conferencing-settings-for-my-organization-in-teams.md) 조직의 오디오 회의 설정 관리 Microsoft Teams

- 조직의 사용자의 Microsoft 오디오 회의 서비스 설정 [관리:](manage-the-audio-conferencing-settings-for-a-user-in-teams.md) 사용자에 대한 오디오 회의 설정 Microsoft Teams

- 오디오 회의 전화 번호의 자동 참석 언어 [변경:](set-auto-attendant-languages-for-audio-conferencing-in-teams.md) 오디오 회의에 대한 자동 참석 언어 Microsoft Teams
