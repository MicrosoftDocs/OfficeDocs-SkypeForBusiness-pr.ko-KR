---
title: 인스턴트 모임을 시작하고 모임을 예약할 수 있는 사용자 관리
author: mkbond007
ms.author: mabond
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: nej, brgussin
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- CSH
ms.custom: ''
description: Teams 모임 정책 설정을 사용하여 인스턴트 모임을 시작하고 모임을 예약할 수 있는 사용자를 제어하는 방법을 알아봅니다.
ms.openlocfilehash: 6736ecd20ef4b0e9eb082e83bd8212597da5f7ab
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466296"
---
# <a name="manage-who-can-start-instant-meetings-and-schedule-meetings"></a>인스턴트 모임을 시작하고 모임을 예약할 수 있는 사용자 관리

관리자는 Teams에서 인스턴트 모임을 시작하고 모임을 예약할 수 있는 사용자를 제한할 수 있습니다. 이는 특정 사용자가 모임을 설정하지 않으려는 개인 정보 보호 및 보안상의 이유로 특히 유용할 수 있습니다.

모임 정책 설정은 기본적으로 켜져 있습니다. 이러한 설정은 모임 **모임 정책** 아래의 Teams 관리 센터에서 찾을 수 **있습니다** > .

- **채널에서 지금 모임: 사용자가 채널에서** 인스턴트 모임을 시작할 수 있는지 여부를 제어합니다.
- **채널 모임 일정**: 사용자가 채널에서 모임을 예약할 수 있는지 여부를 제어합니다.
- **비공개 모임 예약**: 사용자가 Teams에서 비공개 모임을 예약할 수 있는지 여부를 제어합니다. 모임이 팀의 채널에 게시되지 않은 경우 비공개 모임에 해당합니다.
- **Outlook 추가** 기능: 사용자가 Outlook에서 비공개 모임을 예약할 수 있는지 여부를 제어합니다. 모임이 팀의 채널에 게시되지 않은 경우 비공개 모임에 해당합니다.
- **비공개 모임에서 지금 모임**: 사용자가 인스턴트 비공개 모임을 시작할 수 있는지 여부를 제어합니다.

> [!NOTE]
> 관리자와 같은 다른 사람을 대신하여 모임 초대를 보낼 수 있는 권한이 부여된 대리인이 모임을 보낸 경우 모임 정책 설정은 사용 권한(관리자)에게 적용됩니다.

## <a name="channel-meetings"></a>채널 모임

특정 사용자만 인스턴트 채널 모임을 시작하고 채널 모임을 예약하도록 규정 준수 요구 사항이 있는 경우 모임 정책을 만들거나 업데이트하여 이러한 설정을 제한할 수 있습니다. 그런 다음, 인스턴트 채널 모임을 시작하고 채널 모임을 예약하려는 사용자에 대한 별도의 정책을 만들 수 있습니다.

1. Teams 관리 센터에서 **모임 모임** > **정책** 으로 이동하여 업데이트할 정책을 선택합니다. 새 정책을 만들려면 **추가** 를 클릭합니다.
1. **일반** 아래에서 다음을 토글합니다.
    1. 채널에서 인스턴트 모임을 시작할 수 있는 사용자를 제한하려면 이제 **채널에서 모임** 을 **끄** 기로 전환합니다.
    1. 채널에서 모임을 예약할 수 있는 사용자를 제한하려면 **채널 모임 일정을** **해제** 로 전환합니다.
1. 페이지 아래쪽에서 **저장** 을 누릅니다.

## <a name="private-meetings"></a>비공개 모임

특정 사용자만 인스턴트 비공개 모임을 시작하고 비공개 모임을 예약하도록 규정 준수 요구 사항이 있는 경우 모임 정책을 만들거나 업데이트하여 이러한 설정을 제한할 수 있습니다. 그런 다음 인스턴트 모임을 시작하고 비공개 모임을 예약하려는 사용자에게 귀속되는 별도의 정책을 만들 수 있습니다.

1. Teams 관리 센터에서 **모임 모임** > **정책** 으로 이동하여 업데이트할 정책을 선택합니다. 새 정책을 만들려면 **추가** 를 클릭합니다.
1. **일반** 아래에서 다음을 토글합니다.
    1. 인스턴트 비공개 모임을 시작할 수 있는 사용자를 제한하려면 **비공개 모임에서 모임을** **해제** 로 전환합니다.
    1. 채널에서 비공개 모임을 예약할 수 있는 사용자를 제한하려면 **비공개 모임 일정** 과 **Outlook 추가** 기능을 모두 **해제** 로 전환합니다.
1. 페이지 아래쪽에서 **저장** 을 누릅니다.

## <a name="turning-off-meeting-policy-settings"></a>모임 정책 설정 끄기

이러한 모임 정책 설정을 해제한 후에는 정책에 할당된 모든 사용자가 해당 유형의 모임을 시작하거나 예약할 수 없습니다. 사용자가 이전에 시작했거나 예약한 모든 유형의 기존 모임에 대한 모임 참가 링크 및 회의 ID가 작동하지 않습니다. (대화, 파일, 화이트보드, 녹음/ 녹화, 대화 내용 및 모임과 관련된 기타 콘텐츠는 보존되며 사용자는 계속 액세스할 수 있습니다.)

모임 정책 설정이 해제된 후 사용자에 대해 다시 켜지면 사용자가 구성한 이전에 예약된 모든 모임이 활성화되고 사용자가 모임 참가 링크 또는 전화로 참가할 수 있습니다.

## <a name="related-topics"></a>관련 주제

[모임 만료 날짜 변경 - 최종 사용자 컨트롤](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[Teams에서의 모임 정책 관리](meeting-policies-overview.md)

[Teams에서 사용자에게 정책 할당](policy-assignment-overview.md)

[Teams PowerShell 개요](teams-powershell-overview.md)

[Microsoft Teams의 제한 사항 및 사양](/microsoftteams/limits-specifications-teams)
