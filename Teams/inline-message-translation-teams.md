---
title: Microsoft 팀에서 인라인 메시지 번역 켜기
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
localization_priority: Normal
search.appverid: MET150
description: Microsoft 팀에서 인라인 번역을 사용 하는 방법에 대해 알아봅니다.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1926f574977f65181f12ddbb9f0239ad1547d1e5
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836638"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a>Microsoft 팀에서 인라인 메시지 번역 켜기 
=================================================

인라인 메시지 번역은 사용자가 팀 메시지를 Office 365의 개인 언어 설정에서 지정한 [언어로](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) 번역할 수 있는 새로운 Microsoft 팀 기능입니다.

조직에 대해 기본적으로 인라인 메시지 번역이 롤아웃 됩니다. 사용자가 팀 클라이언트 내에서이 기능을 사용할 수 있도록 허용 하려면이 설정을 켜야 합니다.

> [!NOTE]
>이 출시는 Office 365 정부 커뮤니티 클라우드 및 Office 365 독일 환경의 Office 365 구독에서 제외 됩니다.

## <a name="use-powershell-to-turn-on-inline-message-translation"></a>PowerShell을 사용 하 여 인라인 메시지 번역 설정

메시징 정책을 사용 하 여 인라인 메시지 번역을 설정할 수 있습니다.

[Set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) cmdlet을 사용 하 여 정책을 설정 합니다. 정책이 적용 되기까지 몇 분이 소요 됩니다. 사용자는 로그 아웃 하 고 팀에 다시 로그인 해야 할 수 있습니다.

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a>Microsoft 팀 관리 센터를 사용 하 여 인라인 메시지 번역 설정

**Microsoft 팀 관리 센터**의 왼쪽 탐색에서 **메시징 정책을** 선택한 다음 새 정책을 만들거나 기존 정책을 편집 하 고 **사용자가 메시지를 번역할 수 있음** 옵션을 **On**으로 설정 합니다.

> [!NOTE]
> 서비스는 번역을 수행 하 고 규정 준수 레코드에서 캡처한 내용에 영향을 주지 않고이를 클라이언트에 전달 합니다. 번역에 대해 자세히 알아보려면 [Microsoft Translator 란?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)을 참조 하세요.