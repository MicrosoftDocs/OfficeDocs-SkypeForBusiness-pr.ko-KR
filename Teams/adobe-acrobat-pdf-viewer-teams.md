---
title: Teams의 기본 PDF 뷰어인 Adobe Acrobat
author: guptaashish
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
audience: admin
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
ms.openlocfilehash: fd74ece7ba59b437fcd8b47bd184cdcfd150438d
ms.sourcegitcommit: 4708fc1c2b8523e1074aed06b1dd6950c039f200
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/25/2022
ms.locfileid: "67002345"
---
# <a name="adobe-acrobat-as-a-default-pdf-viewer-in-teams"></a>Teams의 기본 PDF 뷰어인 Adobe Acrobat

> [!NOTE]
> Teams의 기본 PDF 환경인 Adobe Acrobat은 현재 공개 미리 보기에서만 사용할 수 있습니다. 이 기능을 사용하기 전에 테넌트에 [대해 공개 미리 보기를 사용하도록 설정합니다](public-preview-doc-updates.md#enable-public-preview). 최종 사용자가 Teams 클라이언트 버전을 공개 미리 보기로 변경하여 Teams에서 Adobe Acrobat을 PDF 뷰어로 경험할 수 있는지 확인합니다.

관리자는 Adobe Acrobat을 Microsoft Teams에서 PDF 파일을 보고 편집하는 기본 앱으로 설정할 수 있습니다. 최종 사용자는 PDF 파일을 보고, 검색하고, 주석을 달고, 주석을 달기 위해 Adobe Acrobat 구독 또는 Adobe ID가 필요하지 않습니다.

## <a name="set-up-adobe-acrobat-app"></a>Adobe Acrobat 앱 설정

ADOBE Acrobat을 PDF 파일을 볼 수 있는 기본 앱으로 설정하려면 다음 단계를 수행합니다.

1. Teams 관리 센터에 로그인하고 **Teams 앱****[관리](https://admin.teams.microsoft.com/policies/manage-apps)** 앱  >  으로 이동합니다.

1. Adobe Acrobat 앱을 검색하고 **Adobe Acrobat** 앱을 선택합니다.

   > [!NOTE]
   >
   > * Adobe Acrobat 앱 상태가 **허용됨** 으로 설정되어 있는지 확인합니다. 그렇지 않으면 **허용된** 토글을 사용하도록 설정합니다.
   > * 앱 사용 권한 정책 또는 앱을 차단한 조직 전체 앱 설정에 기존 관리자 설정이 있는 경우 [앱 사용 권한 정책](teams-app-permission-policies.md) 또는 [조직 전체 앱 설정에서 앱을](teams-app-permission-policies.md) 허용하는지 확인합니다.

1. **사용 권한** 탭에서 **검토 권한을** 선택합니다.

1. **수락** 을 선택합니다.

   :::image type="content" source="media/permission-policy.png" alt-text="Teams 관리 센터의 앱 사용 권한 스크린샷" lightbox="media/teams-app-adobe-acrobat-permission.png":::

## <a name="install-adobe-acrobat-app-for-all-users"></a>모든 사용자에 대한 Adobe Acrobat 앱 설치

전역(조직 전체 기본값) 정책을 사용하여 모든 사용자가 Adobe Acrobat 앱을 할당하고 사용할 수 있도록 할 수 있습니다. 이 단계에서는 Teams에서 신호를 트리거하여 앱을 PDF 파일의 기본 파일 처리기로 설정합니다. 모든 사용자에 대해 Adobe Acrobat 앱을 할당하려면 다음 단계를 수행합니다.

1. Teams 관리 센터에서 **Teams 앱** > [**설정 정책**](https://admin.teams.microsoft.com/policies/app-setup)으로 이동합니다.

1. **정책 관리** 탭에서 **전역(조직 전체 기본값)** 을 선택한 다음 **편집** 을 선택합니다.

   :::image type="content" source="media/setup-policies.png" alt-text="Teams 관리 센터의 Adobe Acrobat 앱에 대한 설정 정책 스크린샷":::

1. 설치된 앱에서 앱 **추가** 를 선택합니다.

1. **Adobe Acrobat** 을 검색하고 앱 이름 옆에 **추가** 를 선택한 다음 **추가** 를 선택합니다.

   :::image type="content" source="media/add-adobe-acrobat.png" alt-text="모든 사용자에 대해 Adobe Acrobat 앱을 추가하는 방법을 보여 주는 스크린샷" lightbox="media/add-adobe-acrobat-app.png":::

1. **저장** 을 선택합니다.

저장을 선택하면 Adobe Acrobat 앱이 Teams로 구성되어 채팅, 채널 또는 파일 앱에서 Adobe Acrobat 앱의 PDF 파일을 엽니다.

일부 특정 개인 또는 그룹에 대해 Adobe Acrobat 앱을 선택적으로 허용하려는 경우 [사용자 지정 앱 사용 권한 정책을](teams-app-permission-policies.md) 할당할 수 있습니다.

이 기능에 대한 다음 정보를 알아봅니다.

* 정책을 설정한 후에는 일반적으로 사용자가 앱을 사용할 수 있는 데 [몇 시간이](teams-app-setup-policies.md) 걸립니다.
정책이 설정되면 몇 시간 후에 설치된 앱을 사용자가 사용할 수 있습니다.
* 채널에 탭으로 고정된 PDF 파일 보기 및 과제 앱에서 PDF 파일 보기는 네이티브 Teams 환경을 통해 계속 제공됩니다.
* Teams의 기본 PDF 뷰어인 Adobe Acrobat은 데스크톱 및 웹 클라이언트에서만 작동합니다. 모바일 클라이언트에서는 지원되지 않습니다.
* 사용자는 PDF 내보내기, 페이지 구성, 파일 결합, PDF 압축 및 PDF 보호와 같은 프리미엄 도구를 사용하려면 Adobe Acrobat 계획이 필요합니다.

> [!NOTE]
> Teams 데스크톱 클라이언트에서 Adobe Acrobat 앱에 로그인하는 동안 문제가 발생하는 경우 브라우저에서 Teams를 열고 로그인할 수 있습니다. 이는 알려진 문제이며 2022년 9월까지 해결될 예정입니다.

## <a name="faqs"></a>Faq

* Teams 클라이언트에서 Adobe Acrobat 앱을 제거하는 방법
  
  최종 사용자는 Teams 클라이언트에서 앱을 제거할 수 있으며 관리자는 설치 정책에서 Adobe Acrobat 앱을 제거할 수 있습니다.

* 관리자가 Adobe Acrobat 앱이 기본 처리기로 설정되면 차단할 수 있나요?
  
  예, 하지만 관리자가 앱을 차단하기 전에 설치 정책을 제거하여 최종 사용자가 Teams 기본 환경으로 안전하게 다시 돌아오도록 합니다.
