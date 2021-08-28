---
title: 인라인 메시지 번역 켜기
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: salilda
ms.localizationpriority: medium
search.appverid: MET150
description: 관리 센터 또는 PowerShell을 사용하여 Microsoft Teams 인라인 번역을 Microsoft Teams 방법에 대해 자세히 알아보습니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4bfaa03ff8fa8654fca48fbd2bd31d8d6518e2de
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593082"
---
# <a name="turn-off-inline-message-translation-in-microsoft-teams"></a>인라인 메시지 번역을 Microsoft Teams

인라인 메시지 번역은 사용자가 Microsoft Teams 설정에서 지정한 언어로 Teams [](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) 번역할 수 있는 기능입니다.

인라인 메시지 번역은 기본적으로 조직에 대해 롤아웃됩니다. 사용자가 이 기능을 클라이언트 내에서 사용할 수 있도록 허용하려면 변경할 Teams 없습니다.

> [!NOTE]
>이 롤아웃은 Office 365 클라우드 및 독일 환경의 Office 365 Government Community 구독에서 Office 365 제외됩니다.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>PowerShell을 사용하여 인라인 메시지 번역을 해제합니다.

메시징 정책을 사용하여 인라인 메시지 번역을 해제할 수 있습니다.

[Set-CsTeamsMessagingPolicy](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet을 사용하여 정책을 해제합니다. 정책이 적용되는 데 몇 분 정도 걸립니다. 사용자는 로그인하고 로그인하여 로그인해야 할 Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Microsoft Teams 관리 센터를 사용하여 인라인 메시지 번역을 해제합니다.

Microsoft Teams 관리 센터에서 왼쪽 탐색에서 메시징 정책을 선택한 다음 새 정책을 만들거나 기존 정책을 편집하고  메시지 변환 옵션을 해제로 **설정합니다.** 

> [!NOTE]
> 서비스는 번역을 실행하고 규정 준수 레코드에 캡처된 콘텐츠에 영향을주지 않는 클라이언트에 전달합니다. 번역에 대한 자세한 내용은 [번역의 Microsoft 번역기.](/azure/cognitive-services/translator/translator-info-overview)