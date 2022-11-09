---
title: 실행 가능한 활동 전자 메일 관리
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams 대화의 실행 가능한 활동 전자 메일을 사용하도록 설정하고 사용하지 않도록 설정하는 방법에 대해 알아봅니다.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43435c436685c53e0ad077887a9fe9d991cf2d61
ms.sourcegitcommit: f5480d0ca34b3160980a4b46b5afa34271293a26
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2022
ms.locfileid: "68899692"
---
# <a name="manage-actionable-activity-emails"></a>실행 가능한 활동 전자 메일 관리

실행 가능한 활동 이메일은 기본적으로 사용하도록 설정되며 Microsoft Teams에서 누락된 대화를 조직 내 사용자에게 알립니다.

누락된 활동 전자 메일은 누락된 메시지 후에 보낸 메시지를 포함하여 대화에 대한 최신 회신을 보여줍니다. 이 기능을 사용하면 사용자가 **회신** 을 선택하여 Outlook에서 직접 회신할 수 있습니다.

## <a name="disable-actionability-in-missed-activity-emails"></a>누락된 활동 전자 메일에서 실행 가능성 사용 안 함

이 기능은 기본적으로 사용하도록 설정되어 있지만 다음 명령을 실행하여 조직 전체의 활동 전자 메일에서 실행 가능성을 해제할 수 있습니다.

```Powershell
Set-OrganizationConfig -SmtpActionableMessagesEnabled $false
```

기능을 사용하지 않도록 설정하면 **회신** 옵션이 **Teams의 회신** 으로 대체되어 누락된 활동 전자 메일이 더 이상 실행 가능하지 않은 것으로 간주됩니다. 사용자는 더 이상 Outlook에서 직접 응답할 수 없으며 Teams에서 대화를 계속하도록 지시됩니다.

> [!NOTE]
> 이 기능은 Mac용 Outlook 또는 일부 이전 버전의 Windows용 Outlook에서는 지원되지 않습니다. 자세한 내용은 [Outlook 및 Office 365 그룹의 실행 가능한 메시지를 참조하세요](/outlook/actionable-messages/).

## <a name="related-topics"></a>관련 주제

[Outlook에서 누락된 활동 전자 메일에 회신합니다](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381).

[Outlook 및 Office 365 그룹의 실행 가능한 메시지입니다](/outlook/actionable-messages/).
