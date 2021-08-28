---
title: '통화 정책의 Microsoft Teams: 통화 및 통화 전달 기능'
author: SerdarSoysal
ms.author: tonysmit
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: 다양한 호출 정책 설정뿐만 아니라 사용자 지정 호출 정책에 사용자를 Microsoft Teams 방법을 알아보고, 수정합니다.
ms.localizationpriority: medium
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
ms.openlocfilehash: 88e4da290fe19f852d18687227768535d405ebd1
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58636752"
---
#  <a name="calling-and-call-forwarding-in-teams"></a>통화 및 통화 Teams

이 Microsoft Teams 호출 정책 제어에서는 사용자가 사용할 수 있는 통화 및 통화 전달 기능을 제어할 수 있습니다. 통화 정책은 사용자가 비공개 통화를 할 수 있는지, 다른 사용자 또는 외부 전화 번호로 통화 전달 또는 외부 전화 번호 동시 벨소리를 사용할 수 있는지 여부를 결정하며, 음성 메일로 통화를 라우팅하고, 통화 그룹에 전화를 보내고, 인바운드 및 아웃바운드 통화에 위임 사용 등입니다.

자동으로 생성된 전역(Org-wide default) 정책을 사용하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.

## <a name="create-a-custom-calling-policy"></a>사용자 지정 호출 정책 만들기

다음 단계에 따라 사용자 지정 호출 정책을 만들 수 있습니다.

1. 관리 센터의 왼쪽 Microsoft Teams 음성 통화 정책으로   >  **이동하세요.**
2. **추가** 를 선택합니다.
3. 통화 정책에서 사용할 기능을 켜거나 해제합니다.
4. 사용자가 음성메일에 인바운드 호출을  라우팅할 수 있는지 여부를 제어하려면 사용 가능 또는 **사용자 제어 를 선택합니다.** 음성메일로 라우팅을 방지하려면 사용 안 을 **선택합니다.**
5. **저장** 을 선택합니다.

## <a name="edit-a-calling-policy"></a>통화 정책 편집

다음 단계를 수행하여 기존 호출 정책을 편집합니다.

1. 관리 센터의 왼쪽 Microsoft Teams 음성 통화 정책을   >  **선택합니다.**
2. 수정할 정책 옆을 클릭한 다음 **편집을 선택합니다.**
3. 원하는 내용을 변경한 다음 저장을 **클릭합니다.**

## <a name="assign-a-custom-calling-policy-to-users"></a>사용자에게 사용자 지정 호출 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>정책 설정 호출

다음은 호출 정책을 구성할 수 있는 설정입니다.

### <a name="make-private-calls"></a>개인 전화 걸기

이 설정은 모든 호출 기능을 Teams. 이 기능을 해제하여 모든 호출 기능을 Teams.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>조직의 사용자에 대한 전달 및 동시 벨소리 호출

이 설정은 들어오는 호출을 다른 사용자에게 전달할 수 있는지 또는 동시에 다른 사람을 호출할 수 있는지 여부를 제어합니다. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>외부 전화 번호로 전달 및 동시 벨소리

이 설정은 들어오는 호출을 외부 번호로 전달할 수 있는지 아니면 외부 번호를 동시에 울 수 있는지 여부를 제어합니다.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>음성메일은 인바운드 호출 라우팅에 사용할 수 있습니다.

이 설정을 사용하면 인바운드 호출을 음성 메일로 보낼 수 있습니다. 유효한 옵션은 다음과 같습니다.

- **사용 가능** 음성메일은 인바운드 통화에 항상 사용할 수 있습니다.
- **사용하지 않도록 설정**  인바운드 통화에는 음성메일을 사용할 수 없습니다.
- **사용자 제어** 사용자는 음성메일을 사용할 수 있는지 여부를 결정할 수 있습니다.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>인바운드 호출을 호출 그룹으로 라우팅할 수 있습니다.

이 설정은 들어오는 호출을 호출 그룹에 전달할 수 있는지 여부를 제어합니다.

### <a name="delegation-for-inbound-and-outbound-calls"></a>인바운드 및 아웃바운드 호출에 대한 위임

이 설정을 사용하면 인바운드 호출을 대리인으로 라우팅할 수 있습니다. 위임된 권한을 위임한 사용자를 대신하여 아웃바운드 호출을 할 수 있습니다. 자세한 내용은 대리인과 전화선 [공유를 참조하세요.](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>PSTN을 통해 수신자 우회 및 통화 보내기 방지 

이 설정을 **On으로 설정하면** PSTN을 통해 호출을 보내고 네트워크를 통해 요금을 보내고 요금을 우회하는 대신 요금이 부과됩니다.

### <a name="busy-on-busy-is-available-when-in-a-call"></a>통화 중 사용 중일 때 사용할 수 있습니다.

사용 중(사용 중 옵션)을 사용하면 사용자가 이미 통화 또는 회의에 참석 중이거나 통화가 보류된 경우 수신 통화가 처리되는 방법을 구성할 수 있습니다. 새 또는 들어오는 호출은 사용 중 신호로 거부될 수 있습니다. 또는 사용자의 응답이 없는 설정에 따라 라우팅될 수 있습니다. 테넌트 수준에서 또는 사용자 수준에서 사용 중 옵션을 사용하도록 설정할 수 있습니다. 사용 중 옵션을 구성하는 방법에 관계없이 통화 또는 회의에 있는 사용자 또는 통화가 보류된 사용자는 새 통화 또는 회의를 시작할 수 없습니다. 이 설정은 기본적으로 비활성화됩니다.

### <a name="web-pstn-calling"></a>웹 PSTN 호출

이 설정을 사용하면 사용자가 웹 클라이언트를 사용하여 PSTN Teams 수 있습니다.

### <a name="incoming-meeting-invites-are-automatically-answered"></a>들어오는 모임 초대에 자동으로 응답됩니다.

이 설정은 들어오는 모임 초대에 자동으로 응답하는지 여부를 제어합니다. 이는 기본적으로 해제되어 있습니다. 이 설정은 들어오는 모임 초대에만 적용됩니다. 다른 유형의 호출에는 적용되지 않습니다.

### <a name="allow-music-on-hold"></a>음악 보류 허용

이 설정을 사용하면 PSTN 호출자에 보류 중일 때 음악을 켜거나 해제할 수 있습니다. 기본적으로 켜져 있습니다. 이 설정은 통화 공원 및 보스 대리인 기능에 적용되지 않습니다. 현재 PowerShell을 통해만 사용할 수 있습니다.

## <a name="related-articles"></a>관련 문서

[Set-CSTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Teams에서 사용자에게 정책 할당](assign-policies.md)
