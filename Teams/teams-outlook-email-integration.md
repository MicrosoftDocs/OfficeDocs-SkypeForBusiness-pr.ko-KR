---
title: Teams 및 Outlook 전자 메일 통합
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: 사용자가 Outlook의 전자 메일과 Teams의 채팅 또는 채널 대화 간에 정보를 공유할 수 있는 기능을 포함하여 Teams 및 Outlook 전자 메일 통합 기능에 대해 자세히 배워 보세요.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6e260148cfcdb45c516958bae03ecfadc1bbd64
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802398"
---
# <a name="teams-and-outlook-email-integration"></a>Teams 및 Outlook 전자 메일 통합

Microsoft Teams에는 조직의 사용자가 Outlook의 전자 메일과 Teams의 채팅 또는 채널 대화 간에 정보를 쉽게 공유하고 부재 중 대화를 관리할 수 있는 기능이 포함되어 있습니다. 이 문서에서는 이러한 기능 및 적용되는 관리 컨트롤에 대한 개요를 제공합니다.

## <a name="share-to-outlook"></a>Outlook에 공유

**Outlook과 공유를** 사용하면 Teams를 나가지 않고도 Outlook에서 Teams 대화의 복사본을 전자 메일에 공유할 수 있습니다. 이 기능은 사용자가 직접 팀 외부 또는 조직 외부의 사용자와 대화 또는 상태 업데이트를 공유해야 하는 경우 매우 편리한 기능입니다. Teams에서 대화 맨 위로 이동하여 다른 옵션 ̇ ̇ ̇ 선택한 다음 **Outlook에 공유를 선택합니다.**   자세한 내용은 [Teams에서 Outlook으로 공유를 참조합니다.](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)

![Teams에서 Outlook에 공유 기능을 보여주는 스크린샷](media/share-to-outlook.png)

이 기능을 사용하려면 웹용 Outlook이 사용자에 대해 켜져 있어야 합니다. 웹용 Outlook이 꺼져 있는 경우 사용자의 Teams에 **Outlook에** 공유 옵션이 표시되지 않습니다. 웹용 Outlook을 설정하고 해제하는 방법에 대한 단계는 사서함에 대해 웹용 Outlook 사용 또는 사용 안 [을 참조하세요.](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)

## <a name="actionable-activity-emails"></a>실행 가능한 활동 전자 메일

사용자는 Teams에서 부재 중 대화를 추적하는 데 도움이 되는 실행 가능한 부재 중 활동 전자 메일을 자동으로 수신합니다. 부재 중 활동 전자 메일에는 부재 중 메시지 이후에 전송된 메시지를 포함하여 대화의 최신  회신이 표시될 수 있으며, 사용자는 회신을 클릭하여 Outlook 내에서 직접 응답할 수 있습니다. 자세한 내용은 Outlook에서 부재 중 활동 전자 [메일에 회신을 참조하세요.](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381) 

> [!NOTE]
> 이 기능은 Mac용 Outlook 또는 일부 이전 버전의 Windows용 Outlook에서 지원되지 않습니다. 자세한 내용은 Outlook 및 [Office 365](https://docs.microsoft.com/outlook/actionable-messages/)그룹에서 실행 가능한 메시지를 참조하세요.

![부재 중 활동 전자 메일을 보여주는 스크린샷](media/missed-activity-email.png)

![부재 중 활동 전자 메일에 회신하는 방법을 보여주는 스크린샷](media/missed-activity-email-reply.png)

[Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) cmdlet을 **SmtpActionableMessagesEnabled** 매개 변수와 함께 사용하여 실행 가능한 전자 메일을 해제할 수 있습니다. 기본적으로 **SmtpActionableMessagesEnabled** 매개 변수는 **true로 설정됩니다.** 매개 변수를 **false로** 설정하면 Office 365에서 실행 가능한 전자 메일 메시지가 해제됩니다. Teams 사용자의 경우 Outlook에서  직접 응답하는 회신 옵션은 부재 중 활동 전자 메일에서 사용할 수 없습니다. 대신, 부재 중 활동 전자 메일에는 **사용자가 Teams에서** 회신할 수 있는 Teams의 회신 옵션이 포함됩니다.
