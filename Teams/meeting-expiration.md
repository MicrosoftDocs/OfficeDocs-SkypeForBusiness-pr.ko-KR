---
title: 모임 정책 및 모임 Microsoft Teams
author: KarliStites
ms.author: kastites
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
description: 모임 정책 설정을 사용하여 모임 만료를 제어하는 Microsoft Teams.
ms.openlocfilehash: 8c8a5603aea6ac65a2cd35b12eca9250debc7c51
ms.sourcegitcommit: 909b0a709983d21fa6f2b547a78cc6a1222188df
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/30/2022
ms.locfileid: "62279175"
---
# <a name="meeting-policies-and-meeting-expiration-in-microsoft-teams"></a>모임 정책 및 모임 Microsoft Teams

[Microsoft Teams](meeting-policies-overview.md) 모임 정책은 조직의 사용자가 모임을 시작하고 예약할 수 있는지 여부를 제어하고 사용자가 예약한 모임에 대해 모임 참가자에게 사용할 수 있는 기능을 제어하는 데 사용됩니다. 전역(조직 전체 기본값) 정책을 사용하거나 사용자 지정 정책을 만들어 사용자에게 할당할 수 있습니다. 관리 센터에서 모임 Microsoft Teams [Get,](/powershell/module/skype/get-csteamsmeetingpolicy) [New](/powershell/module/skype/new-csteamsmeetingpolicy), [Set](/powershell/module/skype/set-csteamsmeetingpolicy), [Remove](/powershell/module/skype/remove-csteamsmeetingpolicy), [Grant](/powershell/module/skype/grant-csteamsmeetingpolicy) -CsTeamsMeetingPolicy PowerShell cmdlet을 사용하여 모임 정책을 관리합니다.

사용자가 모임을 시작하고 예약할 수 있는지 여부를 제어하고 사용자가 예약한 모임의 만료를 제어하는 모임 정책 설정입니다. 모임에 대한 모임 참가 링크 및 회의 ID가 만료되면 아무도 모임에 참가할 수 없습니다. 다음 모임 정책 설정은 사용자가 모임을 시작하고 예약할 수 있는지 여부를 Teams. 이 문서에서 모임 설정을 논의합니다.

- [채널에서 지금 만나기](meeting-policies-in-teams-general.md#meet-now-in-channels): 사용자가 채널에서 즉순 모임을 시작할 수 있는지 여부를 제어합니다.
- [채널 모임 일정](meeting-policies-in-teams-general.md#channel-meeting-scheduling): 사용자가 채널에서 모임을 예약할 수 있는지 여부를 제어합니다.
- [개인 모임 일정](meeting-policies-in-teams-general.md#private-meeting-scheduling): 사용자가 비공개 모임을 예약할 수 있는지 Teams. 모임이 팀의 채널에 게시되지 않은 경우 비공개 모임에 해당합니다.
- [Outlook 추가](meeting-policies-in-teams-general.md#outlook-add-in): 사용자가 사용자로부터 비공개 모임을 예약할 수 있는지 여부를 Outlook. 모임이 팀의 채널에 게시되지 않은 경우 비공개 모임에 해당합니다.
- [비공개 모임](meeting-policies-in-teams-general.md#meet-now-in-private-meetings)에서 지금 모임: 사용자가 즉사적으로 비공개 모임을 시작할 수 있는지 여부를 제어합니다.

기본적으로 이러한 설정은 설정되어 있습니다. 이러한 설정이 해제된 경우 정책을 할당한 사용자는 해당 유형의 새 모임을 시작하거나 예약할 수 없습니다. 동시에 모임 참가는 사용자가 이전에 시작하거나 예약한 해당 유형의 모든 기존 모임의 연결 및 회의 ID를 연결합니다.

예를 들어 사용자가 이러한 모임 정책 설정이 **켜** 진 모임 정책을 할당한 다음 채널 설정에서 지금 모임 허용을 해제하면 해당 사용자가 더 이상  채널에서 즉시 모임을 시작할 수 없습니다. 이제 채널 모임에 사용자가 이전에 만든 링크가 만료되었습니다. 사용자는 다른 모임 유형을 시작하고 예약하고 다른 사용자가 구성한 모임에 참가할 수 있습니다.

## <a name="what-happens-when-the-meeting-join-link-and-conference-id-expire"></a>모임 조인 링크 및 회의 ID가 만료되면 어떻게 됩니까?

모임에 대한 모임 참가 링크 및 회의 ID가 만료되면 아무도 모임에 참가할 수 없습니다. 사용자가 링크 또는 전화를 통해 모임에 참가할 때 모임을 더 이상 사용할 수 없음을 밝히는 메시지가 표시됩니다. 모임과 관련된 대화, 파일, 화이트보드, 녹음/ 녹취 파일 및 기타 콘텐츠는 보존되고 사용자는 여전히 액세스할 수 있습니다.

## <a name="what-happens-when-you-turn-on-and-turn-off-a-meeting-policy-setting"></a>모임 정책 설정을 켜고 끄면 어떻게 하나요?

### <a name="switch-a-meeting-policy-setting-from-on-to-off"></a>모임 정책 설정을 켜기에서 해제로 전환

모임 정책 설정이 **On** 으로 설정되어 있는 경우 정책이 할당된 사용자는 해당 유형의 모임을 시작하거나 예약할 수 있으며 모든 사용자가 참가할 수 있습니다. 모임 정책 설정을 **해제** 로 전환하면 정책이 할당된 사용자는 해당 유형의 새 모임을 시작하거나 예약할 수 없습니다. 사용자가 이전에 예약한 기존 모임의 연결 및 회의 ID가 만료됩니다.

사용자가 다른 사용자가 구성한 모임에 참가할 수 있습니다.

### <a name="switch-a-meeting-policy-setting-from-off-to-on"></a>모임 정책 설정을 끄기에서 켜기로 전환

모임 정책 설정을 **Off** 에서 **켜** 기로 전환하면 정책이 할당된 사용자는 해당 유형의 모임을 시작하거나 예약할 수 있습니다. 모임 정책 설정이 해제된 다음 사용자에 대해 다시 켜져 있는 경우 사용자가 구성한 이전에 예약된(및 만료된) 모임이 모두 활성화되고 사용자가 모임 참가 링크 또는 전화로 모임에 참가할 수 있습니다.  

## <a name="meeting-expiration-scenarios"></a>모임 만료 시나리오

다음은 이 문서에서 설명하는 각 모임 정책 설정에 대해 모임 만료가 작동하는 방법에 대한 요약입니다.

|원하는 경우...&nbsp;&nbsp; |이 작업을&nbsp;&nbsp;&nbsp;&nbsp;  |모임 조인 동작&nbsp;&nbsp;&nbsp;&nbsp;  |
|---------------------------|---------------------|---------|
|사용자가 시작한 비공개 모임 만료&nbsp;&nbsp;|비공개 모임 **에서 지금 모임을 해제합니다**.&nbsp;&nbsp;|이제 사용자가 시작한 비공개 **모임** 에 참가할 수 없습니다.|
|사용자가 예약한 비공개 모임 만료&nbsp;&nbsp;|비공개 **모임의**  모임을 끄고 추가 Outlook **끄기.** &nbsp;&nbsp;|사용자가 예약한 개인 모임에 참가할 수 없습니다. 이렇게 하면 사용자가 다음 모임에 참가할 수 없습니다.<ul><li>과거에 발생한 비공개 모임입니다.</li><li>향후에 예정된 비공개 모임 및 아직 발생하지 않은 비공개 모임입니다.</li><li>향후 개인 모임의 재발하는 인스턴스입니다.</li></ul><br>개인 **모임** 일정 및 Outlook 추가 기능을 모두 해제  해야 사용자가 예약한 비공개 모임이 만료됩니다. 한 설정이 해제되고 다른 설정이 설정 중이면 기존 모임의 모임 참가 링크 및 회의 신분은 활성 상태로 유지되고 만료되지 않습니다.|
|사용자가 **시작한** 채널 모임 만료&nbsp;&nbsp;|채널에서 **지금 모임**  을 끄고 채널 모임일정을 **해제합니다**.&nbsp;&nbsp;|이제 사용자가 시작한 채널 **모임** 에 참가할 수 없습니다.|
|사용자가 예약한 채널 모임 만료&nbsp;&nbsp;|채널 모임일 **정을 해제합니다**.&nbsp;&nbsp;|사용자가 예약한 채널 모임에 참가할 수 없습니다. 이렇게 하면 사용자가 다음 모임에 참가할 수 없습니다.<ul><li>과거에 발생한 채널 모임입니다.</li><li>향후에 예정된 채널 모임과 아직 발생하지 않은 채널 모임입니다.</li><li>향후 채널 모임의 인스턴스입니다.</li></ul>|

사용자가 이전에 예약했거나 특정 사용자가 시작한 모임에 액세스하려는 경우 다음을 할 수 있습니다.

- 해당 사용자의 모임 정책 설정을  설정합니다.
- 해당 사용자의 모임 정책 설정을 해제하고 정책 설정을 사용하도록 설정된 다른 사용자가 만료된 모임을 대체할 새 모임을 만들게 합니다.

> [!NOTE]
> 관리자와 같은 다른 사람을 대신하여 모임 초대를 보낼 수 있는 권한이 부여된 대리인이 모임을 보낸 경우 모임 정책 설정은 권한을 부여한 사용자(관리자)에게 적용됩니다.

## <a name="changes-to-meeting-expiration"></a>모임 만료 변경

> [!IMPORTANT]
> 테넌트에 Teams 만료를 사용하도록 설정하려면 Microsoft Teams 만료 초기 채택[자 프로그램에 적용합니다](https://forms.office.com/pages/responsepage.aspx?id=v4j5cvGGr0GRqy180BHbR8YMDA0A9INMv_DZ8yW5uG1URDc3U1VVMklPTzVMS0RLR0pUQTlWU1BEVC4u).

새로 만든 Teams TMRs(모임 녹화)는 기본 만료일이 60일입니다. 기본적으로 모든 테넌트에 대해 설정됩니다. 즉, 기본적으로 이 기능을 켜고 나서 만든 모든  TMRS는 생성 날짜 이후 60일 후에 삭제됩니다. 관리자는 모임을 자동으로 만료하지 못 **하게 설정할 수도 있습니다**. OneDrive 및 SharePoint 시스템은 모든 TMRs에서 설정된 만료 날짜를 모니터링하고 만료 날짜에 자동으로 TMRs를 재활용 쓰레기통으로 이동합니다.

자동 모임 만료는 이전 TMRs에서 생성한 저장소를 줄이기 위한 간단한 관리 메커니즘입니다. 평균적으로 모든 고객에서 TMRS의 96%는 60일 후에 시청되지 않습니다. 99%는 110일 후에 시청되지 않습니다. 거의 모든 고객이 60일 후에도 다시 시청되지 않는 기록을 제거하여 테넌트의 저장소 부하가 줄어든 혜택을 받을 수 있을 것으로 생각됩니다. 기본적으로 모든 고객에게 최대한 깨끗한 환경을 제공하는 것이 목표입니다.

모임 만료를 사용하여 OneDrive SharePoint 모임 레코드에 의해 구동되는 클라우드 저장소 Teams 제한합니다. 일반적인 모임 녹화는 녹음 시간당 약 400MB를 소비합니다.

> [!NOTE]
> A1 사용자의 최대 기본 만료 날짜는 30일입니다.

### <a name="expiration-date"></a>만료 날짜

- 만료 날짜는 만든 날짜로 계산  됩니다. 관리자에 의해 Teams 설정된 기본 일수 **입니다**.
- 재생은 만료 날짜에 영향을주지 않습니다.

### <a name="change-the-default-expiration-date"></a>기본 만료 날짜 변경

관리자는 PowerShell 또는 관리자 센터의 기본 만료 Teams 수 있습니다. 변경 내용은 해당 시점부터 새로 *만든 TMRS* 에만 적용됩니다. 이 날짜 전에 만든 모든 녹음에는 영향을주지 않습니다. 관리자는 기존 TMRs의 만료 날짜를 변경할 수 없습니다. 이는 TMR을 소유한 사용자의 결정을 보호하기 위해 수행됩니다. 이 설정에서 모임 및 통화를 모두 제어할 수 있습니다.

만료 날짜 값은 다음과 같이 설정할 수 있습니다.

- 최소값: **1일**
- 최대 값: **99,999일**
- 기록이 만료되지 않을 수 있도록 만료 날짜를 **-1** 로 설정할 수도 있습니다.

예제 PowerShell 명령:

```powershell
Set-CsTeamsMeetingPolicy -Identity Global -NewMeetingRecordingExpirationDays 50
```

모임 정책에 따라 Teams 관리 센터에서 만료 날짜를 설정할 **수 있습니다.** 모임이 자동으로 만료  되면 기록 만료를 설정하는 옵션이 제공됩니다.

![모임 만료 정책의 관리 센터 스크린샷입니다.](media/meeting-expiration-policy.jpg)

### <a name="security-and-compliance"></a>보안 및 규정 준수

#### <a name="should-i-rely-on-this-feature-for-strict-security-and-compliance-adherence"></a>엄격한 보안 및 규정 준수를 위해 이 기능을 사용해야 하나요?

아니요, 최종 사용자가 제어하는 모든 녹음 파일의 만료 날짜를 수정할 수 있습니다.

#### <a name="will-a-retention-andor-deletion-policy-ive-set-in-the-security--compliance-center-override-the-teams-meeting-recording-expiration-setting"></a>보안 준수 센터에서 설정한 보존 및/또는 삭제 정책이 & 모임 기록 만료 Teams 재지정하나요?

예, 규정 준수 센터에서 설정한 모든 정책이 우선 순위가 적용됩니다.

예를 들면 다음과 같습니다.

- 사이트의 모든 파일을 100일 동안 보존해야 며, 모임 기록의 만료 설정이 30일인 Teams 정책이 있는 경우 기록은 전체 100일 동안 유지됩니다.
- 모든 모임 Teams 삭제되고 30일의 모임 녹화에 대한 만료 Teams 설정이 있는 경우 5일 후에 기록이 삭제됩니다.

### <a name="will-this-feature-enforce-file-retention"></a>이 기능으로 파일 보존이 시행되나요?

아니요, 이 기능 또는 해당 설정으로 인해 파일이 유지되지 않습니다. 삭제 권한이 있는 사용자가 만기 설정이 있는 TMR을 삭제하려고 하면 해당 사용자의 삭제 조치가 실행됩니다.

### <a name="what-skus-are-required-for-this-feature"></a>이 기능에 필요한 SKU는 무엇인가요?

- 모든 SKU에는 기본적으로 이 기능이 있습니다.
- A1 사용자는 최대 30일 만료 기간으로 기본값이 지정되지만, 필요한 경우 만료 날짜를 변경할 수 있습니다.

### <a name="what-if-i-want-the-admin-to-have-full-control-over-the-lifecycle-of-meeting-recordings-and-dont-want-to-give-end-users-the-ability-to-override-the-expiration-date"></a>관리자가 모임 녹음의 수명 주기를 모두 제어하고 최종 사용자에게 만료 날짜를 다시 정하는 기능을 제공하지 못하게 하려는 경우 어떻게 하나요?

보안 및 규정 준수 유지 및/또는 정책을 삭제하는 것이 좋습니다. 이 제품은 복잡한 정책 및 SLA 중심의 행정적 법적 문제를 해결하기 위한 것입니다.

자동 만료 기능은 전적으로 이전 모임 녹화에서 생성된 저장소의 Teams 메커니즘으로만 사용할 수 있습니다.

### <a name="will-future-tmrs-migrated-from-classic-stream-after-this-feature-is-released-have-auto-expiration-applied-to-them-too"></a>이 기능이 출시된 후 기본 스트림에서 마이그레이션된 향후 TMR에도 자동 만료가 적용되나요?

아니오, 마이그레이션된 TMR에는 그에 대해 설정된 만기 날짜가 함께 제공되지 않습니다. 대신 관리자가 보유하려는 TMR만 마이그레이션하도록 권장합니다. 자세한 내용은 마이그레이션 문서에서 제공됩니다.

### <a name="how-is-this-feature-different-from-the-expiration-message-i-see-when-a-tmr-upload-to-onedrive-and-sharepoint-fails"></a>TMR 업로드가 실패하고 실패할 때 TMR이 OneDrive SharePoint 어떻게 다른가요?

기록이 OneDrive SharePoint 업로드하지 못하면 Teams 서버에서 영구적으로 삭제되기 전에 사용자가 TMR을 다운로드할 수 있는 최대 21일이 있는 메시지를 채팅에 Teams. 실패한 TMR 업로드로 인한 이 기존 만료 환경은 도움말 문서에서 OneDrive SharePoint 자동 만료 기능과 관련이 없습니다.

## <a name="related-topics"></a>관련 항목

[모임 만료 날짜 변경 - 최종 사용자 컨트롤](https://support.microsoft.com/office/record-a-meeting-in-teams-34dfbe7f-b07d-4a27-b4c6-de62f1348c24#bkmk_view_change_expiration_date)

[Teams에서의 모임 정책 관리](meeting-policies-overview.md)

[Teams에서 사용자에게 정책 할당](policy-assignment-overview.md)

[Teams PowerShell 개요](teams-powershell-overview.md)


