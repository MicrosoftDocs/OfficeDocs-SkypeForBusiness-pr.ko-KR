---
title: 앱 사용자 지정을 사용하여 조직의 요구 사항에 맞게 앱 브랜드 지정
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: 조직에서 더 나은 채택을 위해 앱의 메타데이터 및 모양을 변경하여 브랜드를 변경하는 방법을 알아봅니다.
ms.openlocfilehash: 0a1ae462933768e0c5a53db6c7379e5cd8b9bf05
ms.sourcegitcommit: 41a75f1ba5ceb09f8db7d468aa41b63a89ab9c30
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2022
ms.locfileid: "67647482"
---
# <a name="use-app-customization-to-update-branding-of-apps-in-your-organizations-teams-store"></a>앱 사용자 지정을 사용하여 조직의 Teams 스토어에서 앱 브랜딩 업데이트

Microsoft Teams 관리자는 일부 Teams 앱의 모양을 수정하여 조직의 최종 사용자에게 맞춤형 브랜드 환경을 제공할 수 있습니다. 이러한 수정은 최종 사용자를 위한 Teams 스토어 환경을 향상시키고 조직의 브랜딩을 준수하는 데 도움이 될 수 있습니다. 예를 들어 관리자는 조직의 최종 사용자가 앱을 더 쉽게 식별하고, 앱을 사용하고, 더 눈에 띄는지 이해할 수 있도록 앱의 설명과 아이콘을 수정할 수 있습니다. 관리자는 앱의 일부 메타데이터 또는 속성을 변경하여 이러한 변경을 합니다. 변경 내용은 조직 내에서만 사용할 수 있습니다. 이 기능을 앱 사용자 지정이라고 합니다.

관리자는 앱 개발자가 앱을 사용자 지정할 수 있는 경우에만 앱을 사용자 지정할 수 있습니다. Teams는 몇 가지 속성을 사용자 지정하는 옵션을 제공하지만 앱 개발자는 관리자가 실제로 사용자 지정할 수 있는 속성을 제어합니다.

관리자는 다음 속성을 사용자 지정할 수 있습니다.

* 짧은 이름
* 간단한 설명
* 전체 설명
* 개인정보취급방침 URL
* 웹 사이트 URL
* 사용 약관 URL
* 앱 아이콘
* 아이콘의 윤곽선 색상
* 액센트 컬러

이러한 각 메타데이터 필드에 대한 자세한 내용은 Teams 개발자 설명서의 [Teams 매니페스트 스키마](/microsoftteams/platform/resources/schema/manifest-schema) 를 참조하세요.

> [!NOTE]
> 사용자 지정 앱에는 앱 사용자 지정 기능을 사용할 수 없습니다. 관리자는 GCCH(Government Community Cloud High) 및 국방부(DoD) 환경에서 앱을 사용자 지정할 수 없습니다.

## <a name="verify-if-an-app-is-customizable"></a>앱을 사용자 지정할 수 있는지 확인

모든 앱은 사용자 지정할 수 없습니다. 앱 개발자가 앱을 사용자 지정할 수 있는 경우 앱 사용자 지정 기능을 사용하여 앱의 모양을 수정할 수 있습니다. 선택한 앱이 사용자 지정 가능한지 여부를 확인하려면 다음 단계를 수행합니다.

1. Teams 관리 센터에 로그인하고 **Teams 앱 관리 앱** > 에 액세스 **[합니다](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. 앱 이름을 사용하여 사용자 지정하려는 앱을 검색합니다. 앱 개발자가 앱을 사용자 지정할 수 있는지 여부를 **사용자 지정 가능한** 열에서 확인합니다. 열이 표시되지 않으면 열 :::image type="icon" source="media/settings-icon-16px.svg"::: 편집을 선택하고 **사용자 지정 가능** 옵션을 **켜** 기로 전환합니다.

   :::image type="content" source="media/customizable-apps-in-tac.png" alt-text="이 스크린샷은 관리 센터의 사용자 지정 가능한 열을 통해 앱을 사용자 지정할 수 있는지 여부를 확인하는 데 도움이 되는 것을 보여 줍니다.":::

Teams 스토어에서 모든 사용자 지정 가능한 앱을 찾으려면 사용자 지정 가능한 열을 정렬합니다.

## <a name="customize-the-details-of-an-app"></a>앱의 세부 정보 사용자 지정

조직의 Teams 스토어에 표시되는 앱의 모양과 느낌을 변경하려면 다음 단계를 수행합니다.

1. Teams 관리 센터에 로그인하고 **Teams 앱 관리 앱** > 에 액세스 **[합니다](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. 앱 이름을 사용하여 사용자 지정하려는 앱을 검색하고 사용자 지정할 수 있는지 확인합니다.

1. UI를 열어 개별 메타데이터 필드를 사용자 지정하려면 다음 단계 중 하나를 수행합니다.

   * 앱의 행을 선택한 다음, 앱 관리 페이지의 도구 모음에서 **사용자 지정** :::image type="icon" source="media/edit-pen-icon.png"::: 을 선택합니다.

   * 앱 이름을 선택하여 앱 세부 정보 페이지를 연 다음 **사용자 지정 가능** 아래에서 편집 아이콘 :::image type="icon" source="media/edit-pen-icon.png"::: 을 선택합니다.

   * 앱 이름을 선택하고 **작업을 선택한 다음** **사용자 지정을** 선택합니다.

     :::image type="content" source="media/customize-action-menu.png" alt-text="스크린샷은 작업 메뉴를 열고 앱 세부 정보 페이지에서 사용자 지정 옵션을 선택하여 앱을 사용자 지정하는 옵션을 보여줍니다." lightbox="media/customize-action-menu-expanded.png":::

1. 하나 이상의 사용 가능한 필드를 사용자 지정합니다. 앱 개발자는 몇 가지 메타데이터 필드만 사용자 지정할 수 있습니다. [사용자 지정 가능한 필드의 고려 사항 및 제한 사항을 참조하세요](#considerations-and-limitations-of-app-customization).

   :::image type="content" source="media/customize-settings.png" alt-text="사용자 지정 사용자 인터페이스의 이름과 설명이 스크린샷에 표시됩니다.":::

1. 앱을 사용자 지정한 후 **적용** 을 선택합니다. 변경 내용을 확인하려면 [미리 보기 앱 세부 정보를](#preview-app-details) 참조하세요. 변경 내용을 실행 취소하려면 [앱 세부 정보를 기본값으로 다시 설정하세요](#reset-app-details-to-default-values).

1. **게시** 를 선택하여 사용자 지정된 앱을 게시하고 **앱 관리** 페이지에 나열된 앱을 확인합니다.

<!---
   :::image type="content" source="media/customize-app-colors.png" alt-text="Screenshot showing the icon color options that can be customized.":::
--->

## <a name="preview-app-details"></a>앱 세부 정보 미리 보기

사용자 지정을 저장한 후 변경 내용을 보려면 앱 세부 정보 페이지를 봅니다.

1. Teams 관리 센터에 로그인하고 **Teams 앱 관리 앱** > 에 액세스 **[합니다](https://admin.teams.microsoft.com/policies/manage-apps)**.

1. 앱 세부 정보 페이지를 열려면 앱 이름을 선택합니다.

1. **게시자의 짧은** 필드 이름에서 원래 앱 이름을 포함하여 앱 세부 정보를 봅니다. 필드는 앱의 짧은 이름을 변경한 경우에만 표시됩니다.

   :::image type="content" source="media/original-app-version.png" alt-text="스크린샷은 앱의 수정된 짧은 이름을 보여줍니다.":::

Teams 사용자는 클라이언트의 Teams 스토어에서 사용자 지정된 앱을 볼 수 있습니다.

   :::image type="content" source="media/contoso-app.png" alt-text="스크린샷은 Teams 클라이언트에서 사용자 지정된 앱을 보여줍니다.":::

## <a name="considerations-and-limitations-of-app-customization"></a>앱 사용자 지정의 고려 사항 및 제한 사항

앱 사용자 지정 기능에 대한 다음 세부 정보를 고려합니다.

* 앱 기능을 사용자 지정해도 앱 복사본이 생성되지 않으므로 앱 버전은 하나만 있습니다.

* 앱 및 앱과 관련된 설명을 사용자 지정하는 경우 앱 개발자가 설명서 또는 사용 약관에 제공하는 지침을 준수해야 합니다. 타사 이미지를 사용하는 경우 저작권법을 준수합니다.

* 관리자가 제공한 사용자 지정 데이터는 가장 가까운 지역에 저장됩니다.

* 사용 약관 또는 개인 정보 취급 방침에 대한 링크가 유효한지 확인해야 합니다.

* 앱 개발자가 필드를 더 이상 사용자 지정할 수 없도록 하는 경우 더 이상 사용자 지정할 수 없는 필드에 대해 관리자에게 알리는 메시지가 앱 세부 정보 페이지에 나타납니다. 해당 필드에 대한 모든 변경 내용은 원래 값으로 되돌려집니다.

* 프로덕션 환경에서 이러한 변경을 수행하기 전에 Teams 테스트 테넌트에서 앱 사용자 지정 변경을 테스트하는 것이 좋습니다. 테스트 테넌트 가져오기는 [테스트 테넌트 만들기](/microsoftteams/platform/concepts/build-and-test/prepare-your-o365-tenant)의 지침을 따릅니다.

* 변경 내용이 모든 사용자에게 전파되려면 최대 24시간이 걸립니다.

* 앱을 사용자 지정할 수 있도록 개발자는 앱의 새 버전을 제공할 수 있습니다. 새 버전을 업로드하고 앱의 이전 버전을 제거합니다. 앱을 사용자 지정하고 게시한 경우 앱 사용자 지정 기능을 사용하여 사용자 지정된 새 앱이 현재 앱을 대체하지 않습니다.

* [앱 사용 보고서](teams-analytics-and-reports/app-usage-report.md)에는 게시자가 제공한 앱의 원래 이름이 표시됩니다.

* Microsoft Graph 권한 동의 대화 상자에는 게시자가 제공한 앱의 원래 이름이 표시됩니다. 권한을 부여하면서 앱을 정확하게 식별하는 데 도움이 됩니다.

사용자 지정 가능한 필드에 대한 제한 사항은 다음과 같습니다.

| 사용자 지정 가능한 필드 | 고려 |
|:---|:---|
| 모든 URL 필드 | 를 사용하여 유효하고 안전한 URL을 확인합니다 `https`. |
| 간단한 설명 | 짧은 설명은 80자 미만이어야 하며 전체 설명에 있는 내용을 반복하지 않아야 합니다. |
| 아이콘 | 해상도가 32x32 픽셀인 PNG 형식의 투명 윤곽선 아이콘입니다. |
| 색 아이콘 | 해상도가 192x192 픽셀인 PNG 형식의 전체 색 아이콘입니다. |
| 액센트 컬러 | 색은 아이콘 배경과 일치해야 합니다. |

## <a name="reset-app-details-to-default-values"></a>앱 세부 정보를 기본값으로 재설정

앱 세부 정보를 앱 개발자가 제공한 원래 값으로 재설정할 수 있습니다. 이 옵션은 사용자 지정하는 앱에만 사용할 수 있습니다.

1. Teams 관리 센터에서 **Teams 앱** > **[앱 관리](https://admin.teams.microsoft.com/policies/manage-apps)** 에 액세스합니다.

1. 앱 세부 정보 페이지를 열려면 앱 이름을 선택합니다.

1. **작업** 메뉴에서 **기본값으로 다시 설정을** 선택합니다.

   :::image type="content" source="media/reset-app-customization.png" alt-text="스크린샷은 사용자 지정된 앱에 대한 기본값으로 다시 설정 옵션을 보여줍니다.":::

## <a name="related-articles"></a>관련 기사

* [조직의 앱 스토어 사용자 지정](customize-your-app-store.md)
* [앱 브랜드 변경](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/rebrand-apps-to-your-own-organization-s-branding-with-app/ba-p/2376296)
