---
title: Teams 및 Outlook 전자 메일 통합
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: 사용자가 Outlook의 전자 메일과 Teams의 채팅 또는 채널 대화 간에 정보를 공유할 수 있는 기능을 포함하여 Teams 및 Outlook 전자 메일 통합 기능에 대해 알아봅니다.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76a2ecf05a8769b51ffcb9827c0fe6ff75df7b18
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606237"
---
# <a name="teams-and-outlook-email-integration"></a>Teams 및 Outlook 전자 메일 통합

Microsoft Teams에는 조직의 사용자가 Outlook의 전자 메일과 Teams의 채팅 또는 채널 대화 간에 정보를 쉽게 공유하고 누락된 대화를 계속 유지할 수 있는 기능이 포함되어 있습니다. 이 문서에서는 이러한 기능 및 적용되는 관리자 컨트롤에 대한 개요를 제공합니다.

## <a name="share-to-outlook"></a>Outlook에 공유

**Outlook에 공유하면** Teams를 종료하지 않고도 Outlook의 전자 메일에 Teams 대화 복사본을 공유할 수 있습니다. 이 기능은 사용자가 직접 팀 또는 조직 외부의 사용자와 대화 또는 상태 업데이트를 공유해야 하는 경우에 편리합니다. Teams에서 대화의 맨 위로 이동하여 **... 추가 옵션을** 선택한 다음 **Outlook에 공유를** 선택합니다.  자세한 내용은 [Teams에서 Outlook으로 공유를 참조하세요](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d).

![Teams에서 Outlook으로 공유 기능을 보여 주는 스크린샷](media/share-to-outlook.png)

이 기능을 사용하려면 사용자에 대해 웹용 Outlook 설정해야 합니다. 웹용 Outlook 해제된 경우 **사용자에 대한 Outlook 공유** 옵션이 Teams에 표시되지 않습니다. 웹용 Outlook 켜고 끄는 방법에 대한 단계는 [사서함에 웹용 Outlook 사용하거나 사용하지 않도록 설정하는](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app) 방법을 참조하세요.

## <a name="actionable-activity-emails"></a>실행 가능한 활동 전자 메일

사용자는 Teams에서 누락된 대화를 파악하는 데 도움이 되는 실행 가능한 누락된 활동 이메일을 자동으로 받습니다. 누락된 활동 전자 메일은 부재 중 메시지 후에 전송된 메시지를 포함하여 대화의 최신 회신을 표시하며, 사용자는 **[회신]** 을 클릭하여 Outlook 내에서 직접 응답할 수 있습니다. 자세한 내용은 [Outlook에서 누락된 활동 전자 메일에 대한 회신을](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381) 참조하세요. 

> [!NOTE]
> 이 기능은 Mac용 Outlook 또는 일부 이전 버전의 Windows용 Outlook에서는 지원되지 않습니다. 자세한 내용은 [Outlook 및 Office 365 그룹의 실행 가능 메시지를 참조하세요](/outlook/actionable-messages/).

![누락된 활동 전자 메일을 보여 주는 스크린샷](media/missed-activity-email.png)

![누락된 활동 전자 메일에 회신하는 방법을 보여 주는 스크린샷](media/missed-activity-email-reply.png)

[Set-OrganizationConfig](/powershell/module/exchange/organization/set-organizationconfig) cmdlet을 **SmtpActionableMessagesEnabled** 매개 변수와 함께 사용하여 실행 가능한 전자 메일을 끌 수 있습니다. 기본적으로 **SmtpActionableMessagesEnabled** 매개 변수는 **true** 로 설정됩니다. 매개 변수를 **false** 로 설정하면 Office 365 실행 가능한 전자 메일 메시지가 해제됩니다. Teams 사용자의 경우 Outlook에서 직접 응답하는 **회신** 옵션을 누락된 활동 전자 메일에서 사용할 수 없음을 의미합니다. 대신 누락된 활동 전자 메일에는 사용자가 **Teams에서 회신** 할 수 있는 Teams의 회신 옵션이 포함됩니다.

[Outlook 및 Office 365 그룹에서 실행 가능한 메시지](/outlook/actionable-messages/)도 참조하세요.
