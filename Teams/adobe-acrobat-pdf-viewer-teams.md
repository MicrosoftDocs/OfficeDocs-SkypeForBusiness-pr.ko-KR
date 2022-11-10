---
title: Teams의 기본 PDF 뷰어로 Adobe Acrobat 사용하기
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
ms.subservice: teams-apps
ms.date: 09/25/2022
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: ''
search.appverid: ''
f1keywords: ''
description: Adobe Acrobat을 기본 PDF 뷰어로 설정하여 Microsoft Teams에서 PDF 파일을 보고 편집하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 546328ade88864f1412a2da6f94caf2d1f44aef8
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912827"
---
# <a name="set-adobe-acrobat-as-the-default-pdf-viewer-in-microsoft-teams"></a>Microsoft Teams에서 Adobe Acrobat을 기본 PDF 뷰어로 설정

> [!NOTE]
> Microsoft Teams의 기본 PDF 환경으로 Adobe Acrobat을 사용하는 기능은 현재 공개 미리 보기로만 제공됩니다. 이 기능을 사용하려면 관리자가 테넌트에서 [공개 미리 보기를 사용하도록 설정](public-preview-doc-updates.md#enable-public-preview)하고 최종 사용자가 Teams 클라이언트 버전을 공개 미리 보기로 변경해야 합니다.

관리자는 Adobe Acrobat을 Microsoft Teams에서 PDF 파일을 보고 편집하는 기본 앱으로 설정할 수 있습니다. 최종 사용자는 Adobe Acrobat 구독 또는 Adobe ID 없이 PDF 파일을 보고, 검색하고, 주석을 달 수 있습니다.

Adobe Acrobat 앱을 테넌트의 PDF 파일 기본 핸들러로 구성하려면 다음 단계를 사전에 완료해야 합니다.

* [Adobe Acrobat 앱을 허용합니다](#allow-adobe-acrobat-app-in-your-tenant).
* [Adobe Acrobat 앱을 설치합니다](#install-adobe-acrobat-app-for-all-users).

## <a name="allow-adobe-acrobat-app-in-your-tenant"></a>테넌트에서 Adobe Acrobat 앱 허용

앱을 설정하기 전에 테넌트에서 앱을 사용할 수 있도록 허용해야 합니다. 구체적으로 Adobe Acrobat 앱을 허용하고 앱 권한 정책에서 Adobe Acrobat 앱을 허용하도록 설정하세요. Adobe Acrobat을 PDF 파일의 기본 앱으로 설정하려면 다음 단계를 수행합니다.

1. Teams 관리 센터에 로그인하고 **Teams 앱****[앱 관리](https://admin.teams.microsoft.com/policies/manage-apps)** 에  >  액세스합니다.

1. Adobe Acrobat 앱을 검색하고 선택합니다. 앱 세부 정보 페이지가 열립니다.

1. **사용 권한 탭을** 선택한 다음 **, 권한 검토를** 선택합니다.

   :::image type="content" source="media/permission-policy.png" alt-text="Teams 관리 센터의 앱 사용 권한 스크린샷" lightbox="media/teams-app-adobe-acrobat-permission.png":::

1. **허용** 을 선택합니다.

## <a name="install-adobe-acrobat-app-for-all-users"></a>모든 사용자를 위한 Adobe Acrobat 앱 설치

할당을 통해 모든 사용자가 Adobe Acrobat 앱을 사용할 수 있도록 하려면 다음 단계를 수행합니다.

1. Teams 관리 센터에서 **Teams 앱** > [**정책 설정**](https://admin.teams.microsoft.com/policies/app-setup)으로 이동합니다.

1. **정책 관리** 탭에서 **전역(조직 전체 기본값)** 을 선택한 다음 **편집** 을 선택합니다.

   :::image type="content" source="media/setup-policies.png" alt-text="Teams 관리 센터의 Adobe Acrobat 앱에 대한 정책 설정 스크린샷":::

1. 설치된 앱에서 **앱 추가** 를 선택합니다.

1. **Adobe Acrobat** 을 검색하고 앱 이름 옆에 있는 **추가** 를 선택한 다음 **추가** 를 선택합니다.

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="모든 사용자를 위해 Adobe Acrobat 앱을 추가하는 방법을 보여 주는 스크린샷" lightbox="media/add-adobe-acrobat-app.png":::

1. **저장** 을 선택합니다.

저장을 선택하면 Teams에서 Adobe Acrobat 앱을 PDF 파일의 기본 파일 핸들러로 사용합니다.

일부 개인 또는 그룹에 대해 Adobe Acrobat 앱을 선택적으로 허용하려는 경우 [앱 권한에 대한 사용자 지정 정책을](teams-app-permission-policies.md) 할당할 수 있습니다.

## <a name="considerations-and-limitations"></a>고려 사항 및 제한 사항

이 기능에 대한 다음 정보를 숙지하세요.

* 정책을 설정한 후에는 일반적으로 사용자가 앱을 사용할 수 있는 [데 몇 시간이 걸립니다](teams-app-setup-policies.md#considerations-and-limitations) .
* 채널에 탭으로 고정된 PDF 파일을 보고 과제 앱에서 PDF 파일을 보는 기능은 네이티브 Teams 환경을 통해 계속 제공됩니다.
* Teams에서 기본 PDF 뷰어로 Adobe Acrobat을 사용하는 기능은 데스크톱 및 웹 클라이언트에서만 작동합니다. 모바일 클라이언트에서는 지원되지 않습니다.
* PDF 내보내기, 페이지 구성, 파일 결합, PDF 압축, PDF 보호와 같은 프리미엄 도구를 사용하려면 Adobe Acrobat 플랜이 필요합니다.
* 앱을 제거하고자 하는 경우 최종 사용자가 Teams 클라이언트에서 앱을 제거할 수 있습니다. 관리자는 정책 설정을 사용하여 Adobe Acrobat 앱을 제거할 수 있습니다.
* Adobe Acrobat 앱을 차단하는 경우 설치 정책에서 앱을 제거합니다. 이렇게 하면 최종 사용자 환경이 네이티브 PDF 파일 뷰어를 사용하는 환경으로 되돌아갑니다.
* Teams 데스크톱 클라이언트에서 Adobe Acrobat 앱에 로그인하는 동안 문제가 발생하는 경우 [브라우저에서 Teams](https://teams.microsoft.com/) 를 사용하여 로그인합니다.
