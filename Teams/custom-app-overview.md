---
title: 사용자 지정 및 테스트용으로 로드된 앱 관리
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.subservice: teams-apps
audience: Admin
ms.date: 09/25/2022
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Microsoft Teams에서 사용자 지정 앱 및 테스트용으로 로드된 앱이 무엇인지 이해하고 앱의 동작, 롤아웃 및 사용 권한을 제어하는 앱을 관리합니다.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: 42c970f3b354ac1f5b490359f0df9bcc01e97019
ms.sourcegitcommit: d6e180791134426445a35fd485dcca18bde2006b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2022
ms.locfileid: "68494771"
---
# <a name="understand-and-manage-custom-and-sideloaded-apps"></a>사용자 지정 및 테스트용으로 로드된 앱 이해 및 관리

Microsoft Teams를 사용하면 조직 내 개발자가 조직의 내부 사용자를 위한 사용자 지정 앱을 빌드, 테스트 및 배포할 수 있습니다. 이러한 앱을 사용자 지정 앱 또는 기간 업무 앱이라고 합니다. 조직에서 조직 관련 요구 사항에 맞는 사용자 지정 앱 생성을 의뢰할 수도 있습니다. 관리자는 다양한 설정 및 정책을 사용하여 사용자 지정 앱의 롤아웃 및 권한을 제어합니다.

:::image type="content" source="media/custom-app-orgwide-setting-trimmed.png" alt-text="조직 전체 설정 패널에서 조직에 사용자 지정 앱을 허용하는 방법을 보여 주는 스크린샷" lightbox="media/custom-app-orgwide-setting.png":::

사용자 지정 앱을 사용하도록 허용한 후 최종 사용자는 Teams 스토어의 왼쪽 탐색 영역에서 **조직용으로 빌드** 를 선택하여 찾을 수 있습니다.

:::image type="content" source="media/built-for-your-org1.png" alt-text="Teams 데스크톱 앱의 Teams 스토어에 있는 사용자 지정 앱 스크린샷" lightbox="media/built-for-your-org2.png":::

## <a name="understand-sideloading-of-custom-apps"></a>사용자 지정 앱의 테스트용 로드 이해

사용자 지정 앱을 개발하고 최종 사용자에게 해당 앱을 배포하기 전에 개발자는 테스트할 Teams 스토어에 앱을 추가하여 앱을 테스트합니다. 개발자는 자체 또는 지정된 사용자 그룹을 사용하여 테스트할 수 있지만 스토어를 통해 조직의 다른 최종 사용자가 앱을 사용할 수 없습니다. 이 메서드는 앱의 테스트용 로드라고 하며 사용자 지정 앱에만 적용됩니다.

개발자는 일반적으로 개발 중인 앱을 테스트하기 위해 특정 팀의 구성원이 사용할 수 있도록 앱을 사이드로드할 수 있습니다. 이러한 방식으로 앱을 사용하면 앱 개발자에게만 사용이 제한되며 관리자가 Teams에서 테스트용 로드를 허용하는 한 관리자 승인이 필요하지 않습니다.

개발자는 사이드로드된 앱을 Teams 앱 카탈로그에 제출하지 않고 특정 팀과 공유할 수 있습니다. 테스트용으로 로드된 사용자 지정 앱을 제한된 최종 사용자 그룹에서 사용할 수 있지만 모든 최종 사용자에 대해서는 조직의 앱 스토어에서 사용할 수 없습니다.

관리자는 모든 개발자의 앱 사이드로드를 허용하지 않을 수 있습니다. 사이드로드를 허용하지 않는 경우 개발자는 [별도의 테스트 테넌트를 생성](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant)하여 앱을 계속 테스트할 수 있습니다. 사용자 지정 앱 개발이 완료되면 개발자는 관리자에게 최종 사용자에게 사용자 지정 앱을 배포하도록 요청합니다. 자세한 내용은 [사용자 지정 앱을 게시하는 방법](/microsoftteams/upload-custom-apps)을 참조하세요. 관리자는 모든 사용자 또는 특정 사용자에 대해 사용자 지정 앱을 사용하도록 허용하거나 차단합니다.

## <a name="allow-developers-to-upload-custom-apps"></a>개발자가 사용자 지정 앱을 업로드할 수 있도록 허용

앱 설정 정책에서 사용자 지정 정책을 만들거나 전역 정책을 편집하여 사용자 지정 앱 업로드를 허용할 수 있습니다. 사용자 지정 정책을 만들고 특정 사용자에게 적용하려면 다음 단계를 수행합니다.

1. Teams 관리 센터에 로그인하고 **Teams 앱** > **[정책 설정](https://admin.teams.microsoft.com/policies/app-setup)** 에 액세스합니다.
1. **추가** 를 선택합니다.
1. 정책의 이름과 설명을 제공합니다.
1. **사용자 지정 앱 업로드** 를 켜거나 끕니다.
1. 사용자 지정 앱을 개발하고 해당 앱을 업로드할 수 있는 [사용자에게 정책을 적용](assign-policies-users-and-groups.md#assign-a-policy-to-individual-users)합니다.

> [!NOTE]
> 이 설정을 변경하려면 [조직 전체 앱 설정](manage-apps.md#manage-org-wide-app-settings)에서 사용자 지정 앱을 허용합니다.

## <a name="related-articles"></a>관련 기사

* [사용자 지정 앱에 대한 정책 및 설정 관리](teams-custom-app-policies-and-settings.md)
* [앱을 관리하는 정책 이해](app-policies.md)
* [타사 앱 이해](overview-third-party-apps.md)
