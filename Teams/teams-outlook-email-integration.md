---
title: 팀 및 Outlook 전자 메일 통합
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: 사용자가 Outlook의 전자 메일과 팀의 채팅 또는 채널 대화에서 정보를 공유할 수 있는 기능을 비롯 한 팀 및 Outlook 전자 메일 통합 기능에 대해 알아봅니다.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 675834cd36c4e86d34d179e91fe66905e3860b32
ms.sourcegitcommit: 0ad2fb145496210b728034d291a456b4caabdbf9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429444"
---
# <a name="teams-and-outlook-email-integration"></a>팀 및 Outlook 전자 메일 통합

Microsoft 팀에는 조직의 사용자가 Outlook에서 전자 메일 간에 정보를 쉽게 공유할 수 있도록 하는 기능이 포함 되어 있으며, 팀의 채팅 또는 채널 대화에서 부재 중 대화에 대 한 통신을 유지 합니다. 이 문서에서는 이러한 기능과 적용 되는 관리 컨트롤에 대해 간략하게 설명 합니다.

## <a name="share-to-outlook"></a>Outlook에 공유

**Outlook으로 공유** -팀에서 나갈 필요 없이 사용자가 outlook의 전자 메일에 팀 대화 복사본을 공유할 수 있습니다. 이 기능은 사용자가 직접 팀 또는 조직에 속하지 않는 사용자와 대화 또는 상태 업데이트를 공유 해야 하는 경우 편리 합니다. 팀에서 대화의 맨 위로 이동 하 고 **̇ ̇ ̇ 추가 옵션**을 선택한 다음 **Outlook에 공유**를 선택 합니다.  자세히 알아보려면 [팀에서 Outlook으로 공유](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)를 참고 하세요.

![팀의 Outlook과 공유 기능을 보여 주는 스크린샷](media/share-to-outlook.png)

이 기능을 사용 하려면 웹용 Outlook이 사용자에 게 설정 되어 있어야 합니다. 웹용 Outlook이 해제 된 경우 **outlook으로 공유** 옵션이 사용자의 팀에 표시 되지 않습니다. 웹용 Outlook을 설정 하 고 해제 하는 방법에 대 한 단계는 [사서함에 대 한 웹용 Outlook 사용 또는 사용 안 함을](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)참조 하세요.

## <a name="actionable-activity-emails"></a>작업 가능 활동 전자 메일

사용자가 팀에서 부재 중 대화에 대 한 작업을 처리 하는 데 도움이 되는 조치 되지 않은 부재 중 활동 전자 메일을 자동 부재 중 활동 전자 메일에는 부재 중 메시지 후에 전송 된 메시지를 포함 하 여 대화의 최신 회신이 표시 되며, 사용자는 **회신** 을 클릭 하 여 Outlook 내에서 바로 응답할 수 있습니다. 자세한 내용은 [Outlook에서 부재 중 활동 전자 메일에 회신](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381)을 참조 하세요. 

> [!NOTE]
> 이 기능은 Mac 용 Outlook 또는 Windows 용 Outlook의 일부 이전 버전에서 지원 되지 않습니다. 자세한 내용은 [Outlook 및 Office 365 그룹의](https://docs.microsoft.com/outlook/actionable-messages/)실행 가능 메시지를 참조 하세요.

![부재 중 활동 전자 메일을 보여 주는 스크린샷](media/missed-activity-email.png)

![부재 중 활동 전자 메일에 회신 하는 방법을 보여 주는 스크린샷](media/missed-activity-email-reply.png)

[Set-get-organizationconfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) Cmdlet을 **SmtpActionableMessagesEnabled** 매개 변수와 함께 사용 하 여 실행 가능한 전자 메일을 해제할 수 있습니다. 기본적으로 **SmtpActionableMessagesEnabled** 매개 변수는 **true**로 설정 됩니다. 매개 변수를 **false** 로 설정 하면 Office 365에서 실행 가능한 전자 메일 메시지를 끕니다. 팀 사용자의 경우 부재 중 활동 전자 메일에서 Outlook에 직접 응답 하는 **회신** 옵션을 사용할 수 없음을 의미 합니다. 대신, 부재 중 활동 전자 메일에 팀에서 회신할 수 있는 **팀에서 회신** 옵션이 포함 되어 있습니다.
