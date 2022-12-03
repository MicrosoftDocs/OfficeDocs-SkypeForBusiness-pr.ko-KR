---
title: 앱 관리 이벤트에 대한 감사 로그 검색
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 12/02/2022
ms.collection:
- M365-collaboration
search.appverid: MET150
f1keywords: ''
description: 조직 내 사용자 및 관리자의 Teams 앱 활동을 감사하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 5aee5bf00d486586b4bc8e9583504be5e4a9b922
ms.sourcegitcommit: 54c691bd34980a47a5ebf58555529a618a8cada7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2022
ms.locfileid: "69251881"
---
# <a name="search-audit-logs-for-app-management-activities-and-events"></a>앱 관리 활동 및 이벤트에 대한 감사 로그 검색

Microsoft 365 Microsoft Purview Audit(표준)를 사용하면 최종 사용자 및 관리자가 다양한 Microsoft 365 서비스에서 수행한 활동에 대한 감사 레코드를 검색할 수 있습니다.

감사 레코드를 검색하려면 다음 필수 조건을 완료해야 합니다.

* [조직의 구독 및 사용자 라이선스를 가져옵니다](/microsoft-365/compliance/set-up-basic-audit).
* [Microsoft Purview 규정 준수 포털에서 감사 켜기](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
* [감사 로그를 검색할 수 있도록 권한 할당](/microsoft-365/compliance/set-up-basic-audit).

## <a name="search-the-audit-logs-for-app-events-in-teams"></a>Teams에서 앱 이벤트에 대한 감사 로그 검색

Teams의 앱 이벤트에 대한 감사 로그는 관리자가 앱 관리와 관련된 특정 작업을 조사하는 데 도움이 됩니다. 로그에서 광범위한 작업을 검색할 수 있지만 다음 표에는 기록된 몇 가지 작업이 나와 있습니다.

| Teams 앱 작업 | 포털의 활동 이름 | 설명  |
|-------|-------|:-------|
| **앱 설치됨**                 | `AppInstalled`               | 앱이 설치되거나 Teams 클라이언트에 추가됩니다. |
| **앱을 업그레이드함**                  | `AppUpgraded`                | 카탈로그에서 앱이 최신 버전으로 업그레이드됩니다. |
| **앱을 제거함**               | `AppUninstalled`             | 앱이 Teams 클라이언트에서 제거되거나 제거됩니다.                                   |
| **앱을 게시함**                 | `AppPublishedToCatalog`      | 앱이 카탈로그에 추가됩니다.                          |
| **앱을 업데이트함**                   | `AppUpdatedInCatalog`        | 앱이 카탈로그에서 업데이트됩니다.                        |
| **앱이 삭제됨**                   | `AppDeletedFromCatalog`      | 앱이 카탈로그에서 삭제됩니다.                      |
| **모든 조직 앱을 삭제함** | `DeletedAllOrganizationApps` | 카탈로그에서 모든 조직 앱을 삭제했습니다.          |

<!--- organization apps = custom or 3p --->

감사된 Teams 활동의 전체 목록은 [Teams 활동](audit-log-events.md#teams-activities) 및 [Teams의 교대 근무 활동](audit-log-events.md#shifts-in-teams-activities)을 참조하세요.

> [!NOTE]
> 비공개 채널의 앱 이벤트는 Teams 및 표준 채널에서 해당 이벤트가 수행될 때 기록됩니다.

Teams 앱 활동의 감사 로그를 검색하려면 다음 단계를 수행합니다.

1. Microsoft Purview 규정 준수 포털에 로그인하고 **솔루션** > **[감사](https://compliance.microsoft.com/auditlogsearch)** 로 이동합니다.
1. **감사** 페이지에서 필요에 따라 다음 필드를 업데이트합니다.

   * **날짜 및 시간 범위**: 감사 로그를 확인할 기간의 시작 및 종료 날짜를 선택합니다.
   * **활동**: Microsoft Teams 활동을 입력합니다. 목록에서 하나 이상의 앱 활동을 선택합니다. Teams 활동을 빠르게 찾으려면 **활동** 검색 필드에서 `Teams activities` 단어를 검색합니다.
   * **파일, 폴더 또는 사이트**: 파일 이름, URL 또는 그 일부를 입력합니다.
   * **사용자**: 검색하려는 감사 로그의 사용자를 추가합니다.

1. **검색** 을 선택합니다.

   :::image type="content" source="media/compliance-search-teams-activities-trimmed.png" alt-text="Teams 이벤트를 감사하기 위해 Microsoft Purview 규정 준수 포털에서 Teams 활동에 대해 검색합니다." lightbox="media/compliance-search-teams-activities.png":::

검색된 감사 레코드를 CSV 파일로 내보낼 수 있습니다. 자세한 내용은 [감사 로그 내보내기, 구성 및 보기](/microsoft-365/compliance/export-view-audit-log-records)를 참조하세요.

> [!NOTE]
> 위의 활동 중 하나가 사용자 또는 관리자에 의해 수행되면 Teams는 감사 레코드를 생성하고 저장합니다. 감사(표준)에서는 레코드가 90일 동안 유지되므로 지난 3개월 동안 발생한 활동을 검색할 수 있습니다.

> [!TIP]
> 관리자로서 사용자가 봇을 차단하거나 음소거했는지 확인하기 위해 사용자별 보고서를 만들려면 [봇을 차단, 음소거 또는 제거한 사용자 이해를 참조하세요](/microsoftteams/platform/bots/how-to/conversations/send-proactive-messages?#understand-who-blocked-muted-or-uninstalled-a-bot).

## <a name="related-articles"></a>관련 기사

* [Microsoft Power Platform 설치 작업 조사를 위해 감사 로그 사용](manage-power-platform-apps.md#use-audit-logs-to-investigate-microsoft-power-platform-installation-activity)
* [규정 준수 포털에서 감사 로그 검색](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).
* [Microsoft Purview 감사 프리미엄의 개요](/microsoft-365/compliance/advanced-audit).
* [감사 켜기 또는 끄기](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
