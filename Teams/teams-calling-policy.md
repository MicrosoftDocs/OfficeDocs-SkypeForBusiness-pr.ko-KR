---
title: Microsoft 팀의 정책 호출
author: LolaJacobsen
ms.author: tonysmit
manager: serdars
ms.date: 05/06/2019
ms.topic: conceptual
ms.service: msteams
ms.reviewer: jastark
audience: admin
search.appverid: MET150
description: Microsoft 팀의 정책 설정 호출에 대해 자세히 알아보세요.
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
f1keywords:
- ms.teamsadmincenter.callingpolicies.overview
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2e97f16097a30172a2ea56eb7fc9808042055f0e
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483687"
---
<a name="calling-policies-in-microsoft-teams"></a>Microsoft 팀의 정책 호출
===================================

Microsoft 팀에서 호출 정책은 사용자가 사용할 수 있는 통화 전달 기능을 제어 합니다. 호출 정책에 따라 사용자가 비공개 통화를 하거나, 착신 전환 또는 동시에 다른 사용자 또는 외부 전화 번호로 전화를 걸고, 음성 메일로 통화를 라우팅하고, 통화를 보낼 때 통화를 보내거나, 인바운드 및 아웃 바운드 통화에 대 한 위임을 사용할 수 있습니다. 기본 전역 정책은 자동으로 만들어지지만 관리자는 사용자 지정 전화 정책을 만들고 할당할 수도 있습니다.

## <a name="create-a-custom-calling-policy"></a>사용자 지정 호출 정책 만들기

사용자 지정 호출 정책을 만들려면 다음 단계를 따르세요.

1. Microsoft 팀 관리 센터에서 **음성** > **통화 정책을**선택 합니다.
2. **새 정책을**선택 합니다.
3. 통화 정책에 사용할 기능을 설정 합니다. 모든 선택은 기본적으로 **해제** 되어 있습니다.
4. 사용자가 음성 메일로 인바운드 통화를 라우팅할 수 있는지 여부를 제어 하려면 **항상 사용** 또는 **사용자 제어**를 선택 합니다. 음성 메일로 라우팅이 안 되는 것을 방지 하려면 **항상 사용 안 함**을 선택 합니다.
5. **저장**을 선택 합니다.

## <a name="modify-an-existing-calling-policy"></a>기존 통화 정책 수정

기존 통화 정책을 수정 하려면 다음 단계를 따르세요.

1. Microsoft 팀 관리 센터에서 **음성** > **통화 정책을**선택 합니다.
2. 수정할 정책 옆에 있는을 클릭 한 다음 **편집**을 선택 합니다.
3. 통화 정책에 사용할 기능을 설정 합니다. 모든 선택은 기본적으로 **해제** 되어 있습니다.
4. 사용자가 음성 메일로 인바운드 통화를 라우팅할 수 있는지 여부를 제어 하려면 **항상 사용** 또는 **사용자 제어**를 선택 합니다. 음성 메일로 라우팅이 안 되는 것을 방지 하려면 **항상 사용 안 함**을 선택 합니다.
5. **저장**을 선택 합니다.

## <a name="assign-a-calling-policy-to-a-user"></a>사용자에 게 호출 정책 할당

사용자에 게 사용자 지정 호출 정책을 할당 하려면 다음 단계를 따르세요.

1. Microsoft 팀 관리 센터에서 **음성** > **통화 정책을**선택 합니다.
2. 정책 이름 옆에 있는을 클릭 하 여 선택 하 고 **사용자 관리**를 선택 합니다.
3. **사용자 관리** 창에서 사용자 이름을 검색 합니다. (3 개 이상의 문자를 입력 해야 합니다.)
4. 사용자 이름을 선택한 다음 **추가**를 선택 합니다.
5. **저장**을 선택 합니다.

## <a name="calling-policy-settings"></a>호출 정책 설정

사용자 지정 호출 정책을 만들려면 다음 설정을 사용 합니다.

### <a name="user-can-make-private-calls"></a>사용자가 비공개 통화를 할 수 있음

이 설정은 팀의 모든 통화 기능을 제어 합니다. 이 기능을 해제 하 여 팀의 모든 통화를 해제 합니다.

### <a name="call-forwarding-and-simultaneous-ringing-to-other-users"></a>착신 전환 및 다른 사용자에 게 동시 신호음 울림

이 설정은 수신 전화를 다른 사용자에 게 전달 하거나 동시에 다른 사람에 게 연결할 수 있는지 여부를 제어 합니다. 

### <a name="call-forwarding-and-simultaneous-ringing-to-external-phone-numbers"></a>착신 전환 및 외부 전화 번호로의 동시 벨 울림

이 설정은 수신 전화를 외부 번호로 착신 전환할 수 있는지 여부 또는 동시에 외부 번호를 연결 하는 것을 제어 합니다.

### <a name="voicemail-is-available-for-routing-inbound-calls-to-users"></a>음성 메일을 사용 하 여 사용자에 게 들어오는 인바운드 전화 라우팅

이 설정은 인바운드 전화를 음성 메일로 보낼 수 있도록 합니다. 유효한 옵션은 다음과 같습니다.

   - **항상 사용** 음성 메일은 항상 인바운드 통화에 사용할 수 있습니다. 
   - **항상 사용 안 함**  음성 메일을 인바운드 전화에 사용할 수 없습니다. 
   - **사용자 제어** 사용자는 보이스 메일을 사용할 수 있도록 할지 여부를 결정할 수 있습니다.

### <a name="inbound-calls-can-be-routed-to-call-groups"></a>호출 그룹에 대 한 인바운드 통화 라우팅 가능 

> [!Include [feature preview](includes/preview-feature.md)]

이 설정은 걸려오는 전화를 통화 그룹에 착신 전환할 수 있는지 여부를 제어 합니다.

### <a name="allow-delegation-for-inbound-and-outbound-calls"></a>인바운드 및 아웃 바운드 통화에 대 한 위임 허용

> [!Include [feature preview](includes/preview-feature.md)]

이 설정을 사용 하면 들어오는 권한이 있는 사용자를 대신 하 여 대리인에 게 아웃 바운드 호출을 수행할 수 있도록 하는 인바운드 호출이 대리인에 게 전달 됩니다. 자세한 내용은 [대리인과 전화 회선 공유](https://support.office.com/article/share-a-phone-line-with-a-delegate-16307929-a51f-43fc-8323-3b1bf115e5a8)를 참조 하세요.


### <a name="prevent-toll-bypass-and-send-calls-through-the-pstn"></a>PSTN을 통한 무료 바이패스 및 전송 통화 방지 

이로 설정 **** 하면 PSTN을 통해 전화를 보내고, 네트워크를 통해 tolls를 우회 하는 대신 요금을 부과 합니다.

### <a name="busy-on-busy-is-available-while-in-a-call"></a>통화 중에도 다른 용무 중 통화를 이용할 수 있습니다.

다른 용무 중 (다른 용무 중 옵션))은 사용자가 이미 통화 중이거나 회의에 있거나 통화 대기 상태에 있을 때 수신 통화가 처리 되는 방식을 구성할 수 있는 팀 정책에 대 한 새로운 설정입니다. 통화 중 신호를 사용 하 여 신규 또는 수신 전화를 거부할 수 있습니다. 테 넌 트 수준 또는 사용자 수준에서 약속 있음/없음 옵션을 사용 하도록 설정할 수 있습니다. 약속 있음/없음 옵션이 구성 되는 방법에 관계 없이 통화 또는 컨퍼런스 사용자 또는 통화 중 전화를 사용 하는 경우에는 새 통화 또는 회의를 시작 하는 것을 막을 수 없습니다. 이 설정은 기본적으로 사용 되지 않습니다.

## <a name="see-also"></a>참고 항목

[Set-CSTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)