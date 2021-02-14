---
title: Microsoft Teams의 통화 정책
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: 다양한 통화 정책 설정뿐만 아니라 Microsoft Teams의 사용자 지정 통화 정책에 사용자를 만들고, 수정하고, 추가하는 방법을 배워야 합니다.
localization_priority: Normal
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callingpolicies.overview
- seo-marvel-apr2020
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 03ec48de66bc5b179b3a1d8cfe006b1789d09a33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48581079"
---
<a name="calling-policies-in-microsoft-teams"></a>Microsoft Teams의 통화 정책
===================================

Microsoft Teams에서 통화 정책은 사용자가 사용할 수 있는 통화 및 통화 전달 기능을 제어합니다. 통화 정책은 사용자가 개인 통화를 걸 수 있는지, 다른 사용자 또는 외부 전화 번호로 통화 전달 또는 동시 연결, 음성 메일로 통화 라우팅, 통화 그룹으로 통화 보내기, 인바운드 및 아웃바운드 통화에 대한 위임 사용 여부를 결정할 수 있습니다.

자동으로 만들어지거나 사용자 지정 정책을 만들고 할당하는 전역(전체 기본) 정책을 사용할 수 있습니다.

## <a name="create-a-custom-calling-policy"></a>사용자 지정 호출 정책 만들기

다음 단계에 따라 사용자 지정 호출 정책을 만들 수 있습니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 **음성** 통화  >  **정책으로 이동하세요.**
2. **추가** 를 선택합니다.
3. 통화 정책에 사용하려는 기능을 설정하거나 해제합니다.
4. 사용자가 인바운드 통화를 음성으로 라우팅할 수 있는지 여부를 제어하려면 [사용] 또는 **[사용자** **제어]를 선택합니다.** 음성메일로의 라우팅을 방지하려면 사용 안 을 **선택합니다.**
5. 저장을 **선택합니다.**

## <a name="edit-a-calling-policy"></a>통화 정책 편집

다음 단계에 따라 기존 호출 정책을 편집합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 모음에서 음성 통화 **정책을**  >  **선택합니다.**
2. 수정할 정책 옆을 클릭한 다음 편집을 **선택합니다.**
3. 원하는 내용을 변경한 다음 저장을 **클릭합니다.**

## <a name="assign-a-custom-calling-policy-to-users"></a>사용자에게 사용자 지정 호출 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>정책 설정 호출

다음은 호출 정책에 대해 구성할 수 있는 설정입니다.

### <a name="make-private-calls"></a>개인 전화 걸기

이 설정은 Teams의 모든 통화 기능을 제어합니다. 이 기능을 해제하여 Teams의 모든 통화 기능을 해제합니다.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>조직의 사용자에 대한 전달 및 동시 통화

이 설정은 수신 전화를 다른 사용자에게 전달할 수 있는지 아니면 동시에 다른 사용자에게 전화를 걸 수 있는지 여부를 제어합니다. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>외부 전화 번호로의 통화 전달 및 동시 연결

이 설정은 들어오는 호출을 외부 번호로 전달할 수 있는지 아니면 외부 번호에 동시에 연결될 수 있는지를 제어합니다.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>음성메일은 인바운드 통화 라우팅에 사용할 수 있습니다.

이 설정을 사용하면 인바운드 통화를 음성 메일로 보낼 수 있습니다. 유효한 옵션은 다음과 같습니다.

- **사용** 음성메일은 인바운드 통화에 항상 사용할 수 있습니다.
- **사용 안**  음성메일은 인바운드 통화에 사용할 수 없습니다.
- **사용자가 제어** 사용자는 음성메일을 사용할 수 있는지 여부를 결정할 수 있습니다.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>인바운드 호출을 호출 그룹으로 라우팅할 수 있습니다. 

> [!Include [feature preview](includes/preview-feature.md)]

이 설정은 수신 전화를 호출 그룹으로 전달할 수 있는지 여부를 제어합니다.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>인바운드 및 아웃바운드 호출에 대한 위임 허용

> [!Include [feature preview](includes/preview-feature.md)]

이 설정을 사용하면 인바운드 호출을 대리인으로 라우팅할 수 있어 대리인이 위임된 권한을 부여한 사용자를 대신하여 아웃바운드 호출을 할 수 있습니다. 자세한 내용은 [대리인과 전화선 공유를 참조하세요.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>PSTN을 통해 수신 우회 및 통화 보내기 방지 

이를 **On으로 설정하면** PSTN을 통해 통화를 보내고 네트워크를 통해 통화를 보내고 요금을 우회하는 대신 요금이 부과됩니다.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>통화 중 사용 중 사용 가능

사용 중(사용 중 옵션)은 사용자가 이미 통화 또는 회의에 참석 중이거나 통화가 보류 중일 때 수신 전화가 처리되는 방법을 구성할 수 있는 새로운 설정입니다. 새 호출 또는 들어오는 호출은 사용 중 신호로 거부될 수 있습니다. 테넌트 수준 또는 사용자 수준에서 사용 중 옵션을 사용하도록 설정할 수 있습니다. 사용 중 옵션을 구성하는 방법에 관계없이 통화 또는 회의에 참여하는 사용자나 통화가 보류된 사용자는 새 통화나 회의를 시작할 수 없습니다. 이 설정은 기본적으로 사용하지 않도록 설정되어 있습니다.

### <a name="allow-web-pstn-calling"></a>웹 PSTN 통화 허용

이 설정을 사용하면 사용자가 Teams 웹 클라이언트를 사용하여 PSTN 번호로 전화를 걸 수 있습니다.

### <a name="allow-music-on-hold"></a>보류 중 음악 허용

이 설정을 사용하면 PSTN 호출자에 보류된 경우 음악 보류를 켜거나 해제할 수 있습니다. 기본적으로 켜져 있습니다. 이 설정은 통화 공원 및 상사 대리인 기능에는 적용되지 않습니다. 현재 PowerShell을 통해서만 사용할 수 있습니다.

## <a name="related-topics"></a>관련 항목

[Set-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

[Teams에서 사용자에게 정책 할당](assign-policies.md)
