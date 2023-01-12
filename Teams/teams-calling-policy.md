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
description: Microsoft Teams의 사용자 지정 통화 정책뿐만 아니라 다양한 통화 정책 설정에 사용자를 만들고 수정하고 추가하는 방법을 알아봅니다.
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
ms.openlocfilehash: a478e203ed973ff2199b4ad500de0441e200918d
ms.sourcegitcommit: 387141880842c93ecf4a936aaa26342a3f996259
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2023
ms.locfileid: "69781469"
---
# <a name="calling-policies-calling-and-call-forwarding-features-in-teams"></a>통화 정책: Teams의 통화 및 착신 전환 기능

Microsoft Teams에서 통화 정책은 사용자가 사용할 수 있는 통화 및 착신 전환 기능을 제어합니다. 통화 정책은 사용자가 비공개 통화를 할 수 있는지, 다른 사용자 또는 외부 전화 번호로의 통화 전달 또는 동시 벨소리를 사용할 수 있는지, 음성 메일로 통화를 라우팅하고, 통화 그룹에 전화를 걸고, 인바운드 및 아웃바운드 통화에 위임을 사용할 수 있는지 여부를 결정합니다.

자동으로 생성되는 전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들고 할당할 수 있습니다.

## <a name="create-a-custom-calling-policy"></a>사용자 지정 통화 정책 만들기

다음 단계에 따라 사용자 지정 통화 정책을 만듭니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** > **통화 정책** 으로 이동합니다.
2. **추가** 를 선택합니다.
3. 통화 정책에서 사용하려는 기능을 켜거나 끕니다.
    - 예를 들어 사용자가 인바운드 통화를 음성 메일로 라우팅할 수 있는지 여부를 제어하려면 **사용** 또는 **사용자 제어를** 선택합니다. 음성 메일에 대한 라우팅을 방지하려면 **사용 안 됨을** 선택합니다.
4. **저장** 을 선택합니다.

## <a name="edit-a-calling-policy"></a>통화 정책 편집

기존 통화 정책을 편집하려면 다음 단계를 수행합니다.

1. Microsoft Teams 관리 센터의 왼쪽 탐색 영역에서 **음성** > **통화 정책을** 선택합니다.
2. 수정하려는 정책 옆을 클릭한 다음 **편집** 을 선택합니다.
3. 원하는 대로 변경한 다음 **저장** 을 클릭합니다.

## <a name="assign-a-custom-calling-policy-to-users"></a>사용자에게 사용자 지정 통화 정책 할당

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="calling-policy-settings"></a>통화 정책 설정

통화 정책에 대해 구성할 수 있는 설정은 다음과 같습니다.

### <a name="make-private-calls"></a>개인 전화 걸기

이 설정은 Teams의 모든 통화 기능을 제어합니다. Teams의 모든 통화 기능을 끄려면 이 설정을 끕니다.

### <a name="cloud-recording-for-calling"></a>통화용 클라우드 기록

이 설정은 사용자가 통화를 기록할 수 있는지 여부를 제어합니다. 이 설정은 기본적으로 꺼져 있습니다.

### <a name="transcription"></a>전사

이 설정은 사용자가 통화 기록을 사용할 수 있는지 여부를 제어합니다. 이 설정은 기본적으로 꺼져 있습니다.

### <a name="call-forwarding-and-simultaneous-ringing-to-people-in-your-organization"></a>조직의 사용자에게 착신 전환 및 동시 울림

이 설정은 들어오는 전화를 다른 사용자에게 전달할 수 있는지 또는 조직의 다른 사람에게 동시에 전화를 걸 수 있는지 여부를 제어합니다. 이 설정은 기본적으로 설정됩니다.

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>외부 전화 번호로 착신 전환 및 동시 벨소리

이 설정은 들어오는 호출을 외부 번호로 전달할 수 있는지 또는 동시에 외부 번호를 울릴 수 있는지 여부를 제어합니다. 이 설정은 기본적으로 설정됩니다.

### <a name="voicemail-is-available-for-routing-inbound-calls"></a>음성 메일은 인바운드 통화 라우팅에 사용할 수 있습니다.

이 설정을 사용하면 인바운드 호출을 음성 메일로 보낼 수 있습니다. 기본 설정은 **사용자 제어입니다**. 유효한 옵션은 다음과 같습니다.

- **사용** 음성 메일은 항상 인바운드 통화에 사용할 수 있습니다.
- **사용하도록 설정되지 않음**  인바운드 통화에는 음성 메일을 사용할 수 없습니다.
- **사용자 제어** 사용자는 음성 메일을 사용할 수 있도록 할지 여부를 결정할 수 있습니다.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>인바운드 호출을 호출 그룹으로 라우팅할 수 있습니다.

이 설정은 들어오는 호출을 호출 그룹으로 전달할 수 있는지 여부를 제어합니다. 이 설정은 기본적으로 켜져 있습니다.

### <a name="delegation-for-inbound-and-outbound-calls"></a>인바운드 및 아웃바운드 호출에 대한 위임

이 설정을 사용하면 대리인에게 인바운드 호출을 라우팅할 수 있으므로 대리자는 위임된 권한이 있는 사용자를 대신하여 아웃바운드 호출을 수행할 수 있습니다. 이 설정은 기본적으로 켜져 있습니다. 자세한 내용은 [대리인과 전화선 공유를 참조하세요](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8).

### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>PSTN을 통한 수신자 우회 및 통화 보내기 방지

이 설정을 켜면 PSTN을 통해 전화를 보내고 네트워크를 통해 전화를 보내고 통행료를 우회하는 대신 요금이 발생합니다. 이 설정은 기본적으로 꺼져 있습니다.

### <a name="music-on-hold-for-pstn-calls"></a>PSTN 통화에 대한 음악 보류 중

이 설정을 사용하면 PSTN 호출자가 대기 중일 때 음악을 켜거나 끌 수 있습니다. 기본적으로 켜져 있습니다. 이 설정은 호출 파크 및 보스 대리자 기능에는 적용되지 않습니다. [사용자 지정 음악을 구성하는](music-on-hold.md) 방법에 대해 자세히 알아보세요.

### <a name="busy-on-busy-when-in-a-call"></a>통화 중일 때 사용 중

통화 중일 때 사용 중("사용 중 옵션"이라고도 함)을 사용하면 사용자가 이미 통화 또는 회의에 있거나 통화가 보류 중일 때 수신 통화가 처리되는 방식을 구성할 수 있습니다. 새 호출 또는 수신 호출은 사용 중인 신호로 거부되거나 사용자의 응답되지 않은 설정에 따라 라우팅될 수 있습니다. 사용 중인 옵션을 구성하는 방법에 관계없이 통화 또는 회의의 사용자 또는 통화가 보류된 사용자는 새 통화 또는 회의를 시작할 수 없습니다. 이 설정은 기본적으로 **사용하도록 설정되지 않음** 으로 설정됩니다.

- **사용하도록 설정되지 않음** 사용 중 옵션을 사용할 수 없으며 사용자가 이미 전화를 받고 있는 동안 신규 또는 들어오는 호출이 사용자에게 계속 전달될 수 있습니다.
- **사용** 새 호출 또는 들어오는 호출은 사용 중인 신호와 함께 거부됩니다.
- **답** 사용자의 응답이 없는 설정(예: 음성 메일로 라우팅 또는 다른 사용자에게 전달)이 사용됩니다.
- **사용자 제어** 이 옵션은 현재 작동하지 않습니다. 설정하면 값을 **사용 안** 됨으로 설정으로 읽습니다.

### <a name="web-pstn-calling"></a>웹 PSTN 호출

이 설정을 사용하면 사용자가 Teams 웹 클라이언트를 사용하여 PSTN 번호를 호출할 수 있습니다. 이 설정은 기본적으로 설정됩니다.

### <a name="real-time-captions-in-teams-calls"></a>Teams 통화의 실시간 캡션

이 설정은 Teams 통화의 실시간 캡션을 사용자가 사용할 수 있는지 여부를 제어합니다. 이 설정은 기본적으로 켜져 있습니다.

### <a name="automatically-answer-incoming-meeting-invites"></a>들어오는 모임 초대에 자동으로 응답

이 설정은 들어오는 모임 초대가 자동으로 응답되는지 여부를 제어합니다. 이는 기본적으로 해제되어 있습니다. 이 설정은 들어오는 모임 초대에만 적용됩니다. 다른 유형의 호출에는 적용되지 않습니다.

### <a name="spam-filtering"></a>스팸 필터링

이 설정을 사용하면 들어오는 호출에서 사용할 수 있는 스팸 필터링 유형을 제어할 수 있습니다. 기본 및 IVR(Captcha Interactive Voice) 검사를 모두 수행할 수 있습니다. 이 설정은 기본적으로 켜져 있습니다.

### <a name="sip-devices-can-be-used-for-calls"></a>SIP 디바이스를 호출에 사용할 수 있습니다.

이 설정을 사용하면 사용자가 SIP 디바이스를 사용하여 전화를 걸고 받을 수 있습니다. 이 설정은 기본적으로 꺼져 있습니다.

### <a name="open-apps-in-browser-for-incoming-pstn-calls"></a>들어오는 PSTN 호출에 대한 브라우저에서 앱 열기

이 설정은 사용자에게 들어오는 PSTN 호출을 위해 브라우저에서 앱이 자동으로 열리는지 여부를 제어합니다. 이는 인바운드 발신자의 전화 번호를 앱에 전달하여 통화가 진행되는 동안 연결된 고객 레코드를 찾는 데 사용할 수 있습니다. 이 설정은 기본적으로 꺼져 있습니다.

켜진 경우 **들어오는 PSTN 호출 상자의 브라우저에서 앱을 열려면 URL에 앱에 대한** 링크를 제공해야 합니다. {phone} 자리 표시자를 사용하여 전화 번호(E.164 형식)를 제공된 URL에 전달할 수 있습니다. 또는 자리 표시자 없이 제네릭 URL을 제공할 수 있습니다. 그러면 나열된 URL만 시작됩니다.

![들어오는 PSTN 통화 정책 설정에 대한 브라우저에서 앱 열기 스크린샷](media/teams-open-apps-in-browser-pstn.png)

## <a name="related-articles"></a>관련 기사

[Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

[Teams에서 사용자에게 정책 할당](policy-assignment-overview.md)

[PSTN 연결 옵션](pstn-connectivity.md)

[사용자에 대한 통화 설정 구성](user-call-settings.md)
