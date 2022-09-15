---
title: 'Microsoft Teams의 통화 정책: 통화 및 착신 전환 기능'
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Microsoft Teams의 사용자 지정 통화 정책 및 다양한 통화 정책 설정에 사용자를 만들고, 수정하고, 추가하는 방법을 알아봅니다.
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
ms.openlocfilehash: 6c785a6860c1ea45200253e9d2530a80e9dd28f6
ms.sourcegitcommit: 424b14534aa269bb408c97c368102a193b481656
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/14/2022
ms.locfileid: "67708306"
---
# <a name="calling-and-call-forwarding-in-teams"></a>Teams에서 통화 및 착신 전환

Microsoft Teams에서 통화 정책은 사용자가 사용할 수 있는 통화 및 착신 전환 기능을 제어합니다. 통화 정책은 사용자가 개인 통화를 할 수 있는지, 다른 사용자 또는 외부 전화 번호로 통화 전달 또는 동시 벨소리를 사용할 수 있는지, 음성 메일로 통화를 라우팅하고, 통화 그룹에 전화를 걸고, 인바운드 및 아웃바운드 통화에 위임을 사용할 수 있는지 여부를 결정합니다.

자동으로 만들어지는 전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.

## <a name="create-a-custom-calling-policy"></a>사용자 지정 통화 정책 만들기

다음 단계에 따라 사용자 지정 호출 정책을 만듭니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** > **통화 정책** 으로 이동합니다.
2. **추가** 를 선택합니다.
3. 통화 정책에서 사용하려는 기능을 켜거나 끕니다.
4. 사용자가 인바운드 통화를 음성 메일로 라우팅할 수 있는지 여부를 제어하려면 **사용** 또는 **사용자 제어를** 선택합니다. 음성 메일에 대한 라우팅을 방지하려면 **[사용 안 함**]을 선택합니다.
5. **저장** 을 선택합니다.

## <a name="edit-a-calling-policy"></a>통화 정책 편집

기존 통화 정책을 편집하려면 다음 단계를 수행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** > **통화 정책을** 선택합니다.
2. 수정할 정책 옆을 클릭한 다음 **편집** 을 선택합니다.
3. 원하는 대로 변경한 다음 **저장** 을 클릭합니다.

## <a name="assign-a-custom-calling-policy-to-users"></a>사용자에게 사용자 지정 통화 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>통화 정책 설정

다음은 통화 정책에 대해 구성할 수 있는 설정입니다.

### <a name="make-private-calls"></a>개인 전화 걸기

이 설정은 Teams의 모든 통화 기능을 제어합니다. Teams의 모든 통화 기능을 해제하려면 이 기능을 해제합니다.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>조직 내 사용자에게 착신 전환 및 동시 울리기

이 설정은 수신 전화를 다른 사용자에게 전달할 수 있는지 또는 다른 사람에게 동시에 전화를 걸 수 있는지 여부를 제어합니다.

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>외부 전화 번호로 착신 전환 및 동시 울림

이 설정은 들어오는 호출을 외부 번호로 전달할 수 있는지 또는 외부 번호를 동시에 울릴 수 있는지 여부를 제어합니다.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>음성 메일은 인바운드 통화 라우팅에 사용할 수 있습니다.

이 설정을 사용하면 인바운드 통화를 음성 메일로 보낼 수 있습니다. 유효한 옵션은 다음과 같습니다.

- **사용** 음성 메일은 항상 인바운드 통화에 사용할 수 있습니다.
- **비활성화**  인바운드 통화에는 음성 메일을 사용할 수 없습니다.
- **사용자 제어** 사용자는 음성 메일을 사용할 수 있도록 할지 여부를 확인할 수 있습니다.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>인바운드 호출을 호출 그룹으로 라우팅할 수 있습니다.

이 설정은 들어오는 호출을 호출 그룹으로 전달할 수 있는지 여부를 제어합니다.

### <a name="delegation-for-inbound-and-outbound-calls"></a>인바운드 및 아웃바운드 호출에 대한 위임

이 설정을 사용하면 대리자가 위임된 권한을 가진 사용자를 대신하여 아웃바운드 호출을 수행할 수 있도록 인바운드 호출을 대리자로 라우팅할 수 있습니다. 자세한 내용은 [대리인과 전화선 공유를](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8) 참조하세요.

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>수신자 우회 방지 및 PSTN을 통한 통화 보내기

이를 **On** 으로 설정하면 네트워크를 통해 전화를 보내고 통행료를 우회하는 대신 PSTN을 통해 전화를 보내고 요금이 발생합니다.

### <a name="busy-on-busy-is-available-when-in-a-call"></a>통화 중일 때 사용 중일 수 있음

사용 중(사용 중 옵션)을 사용하면 사용자가 이미 통화 또는 회의에 있거나 통화가 보류된 경우 수신 통화가 처리되는 방법을 구성할 수 있습니다. 신규 또는 수신 호출은 사용 중인 신호로 거부되거나 사용자의 응답하지 않는 설정에 따라 라우팅될 수 있습니다. 테넌트 수준 또는 사용자 수준에서 사용 중인 옵션을 사용하도록 설정할 수 있습니다. 사용 중인 옵션이 구성된 방식에 관계없이 통화 또는 회의의 사용자 또는 통화가 보류된 사용자는 새 통화 또는 회의를 시작할 수 없습니다. 이 설정은 기본적으로 사용하지 않도록 설정됩니다.

### <a name="web-pstn-calling"></a>웹 PSTN 호출

이 설정을 사용하면 사용자가 Teams 웹 클라이언트를 사용하여 PSTN 번호를 호출할 수 있습니다.

### <a name="automatically-answer-incoming-meeting-invites"></a>들어오는 모임 초대에 자동으로 응답

이 설정은 들어오는 모임 초대가 자동으로 응답되는지 여부를 제어합니다. 이는 기본적으로 해제되어 있습니다. 이 설정은 들어오는 모임 초대에만 적용됩니다. 다른 유형의 호출에는 적용되지 않습니다.

### <a name="allow-music-on-hold"></a>보류 중인 음악 허용

이 설정을 사용하면 PSTN 호출자가 대기 중일 때 음악을 켜거나 끌 수 있습니다. 기본적으로 켜져 있습니다. 이 설정은 호출 공원 및 보스 대리자 기능에는 적용되지 않습니다.

### <a name="allow-sip-devices-calling"></a>SIP 디바이스 호출 허용

이 설정을 사용하면 사용자가 SIP 디바이스를 사용하여 전화를 걸고 받을 수 있습니다.

### <a name="spam-filtering"></a>스팸 필터링

이 설정을 사용하면 들어오는 호출에서 사용할 수 있는 스팸 필터링 유형을 제어할 수 있습니다.

### <a name="call-recording-live-captions-and-transcription"></a>통화 녹음, 라이브 캡션 및 전사

이러한 설정을 사용하면 통화 기록, 라이브 캡션 및 전사를 사용자가 사용할 수 있는지 여부를 제어할 수 있습니다.

## <a name="related-articles"></a>관련 기사

[New-CsTeamsCallingPolicy](/powershell/module/skype/new-csteamscallingpolicy)

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

[Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy)

[Remove-CsTeamsCallingPolicy](/powershell/module/skype/remove-csteamscallingpolicy)

[Teams에서 사용자에게 정책 할당](policy-assignment-overview.md)
