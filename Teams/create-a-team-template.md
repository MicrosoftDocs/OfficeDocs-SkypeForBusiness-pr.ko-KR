---
title: 사용자 지정 팀 템플릿을 Microsoft Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: aaglick
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 사용자 지정 팀 템플릿을 만드는 방법을 Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1fa114e6bc15ff8aeb6d0e75dcb6c0c45871b436
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62399552"
---
# <a name="create-a-custom-team-template-in-microsoft-teams"></a>사용자 지정 팀 템플릿을 Microsoft Teams

**사용자 지정 템플릿은 아직 EDU 고객에게 지원되지 않습니다.**

사용자 지정 팀 템플릿은 채널, 탭 및 앱 집합이 있는 미리 정의된 팀 구조입니다. 올바른 공동 작업 공간을 빠르게 만드는 데 도움이 되는 템플릿을 개발할 수 있습니다. 사용자 지정 팀 템플릿은 기본 설정을 사용합니다.  

<br>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4P5rx]


시작:

1. Teams 관리 센터에 로그인합니다.

2. 왼쪽 탐색 **에서 Teams** >  **템플릿을 확장합니다**.

3. **추가** 를 선택합니다.

    ![강조 표시된 추가가 있는 Team 템플릿 대화 상자의 이미지입니다.](media/team-templates-new.png)

4. 팀 템플릿 **섹션** 에서 새 템플릿 **만들기를 선택합니다**.

5. 템플릿 **설정 섹션** 에서 다음 필드를 완료한 다음 다음을 **선택합니다**.
    - 템플릿 이름
    - 서식 파일 짧고 긴 설명
    - 로컬 표시  

    ![팀 템플릿 설정 이름 대화 상자의 이미지입니다.](media/template-add-a-name.png)

6. 채널 **, 탭 및 앱 섹션** 에서 팀에 필요한 모든 채널 및 앱을 추가합니다.

    1. 채널 **섹션에서** 추가를 **선택합니다**.
    2. 추가 **대화 상자에서** 채널 이름을 지정합니다.
    3. 설명을 추가합니다.
    4. 채널을 기본적으로 표시해야 하는지 여부를 결정합니다.
    5. 채널에 추가할 앱 이름을 검색합니다.
    6. 완료 **시 적용** 을 선택합니다.

    ![Team 템플릿 채널, 탭 및 앱 화면의 이미지입니다.](media/template-channels-tabs-apps.png)

8. 완료 **시 제출** 을 선택합니다.

새 템플릿이 Team 템플릿 목록에 **표시됩니다** . 템플릿을 사용하여 팀을 만들 수 Teams.

> [!Note]
> 팀 사용자가 갤러리에서 사용자 지정 템플릿 변경을 보는 데 최대 24시간이 걸릴 수 있습니다.

## <a name="customizing-website-tab-apps"></a>웹 사이트 탭 앱 사용자 지정

> [!Note]
> 이 기능은 초기 미리 보기 상태입니다.

사용자 지정 팀 템플릿의 채널에 대한 웹 사이트 탭에 대한 URL을 지정할 수 있습니다. 템플릿을 사용하여 팀을 만드는 최종 사용자에게는 지정된 사이트 URL에 미리 설정된 웹 사이트 탭이 있습니다.

시작:

1. 새 팀 템플릿을 만들거나 기존 팀 템플릿을 편집합니다.

2. 채널 섹션에서 새 채널을 추가하거나 기존 채널을 선택하고 편집 **을 선택합니다**.

3. 이 템플릿 **에 대한 앱** 추가 섹션에서 웹 사이트 앱을 추가합니다.

    ![이 템플릿 옵션에 대한 앱을 추가합니다.](media/add-an-app-template.png)

4. 편집 아이콘을 선택하고 원하는 URL을 입력합니다.

    ![앱 URL을 추가합니다.](media/add-url-app-template.png)

5. 탭 **앱** 편집에 대해 저장을 선택한 다음 적용을 선택하여  변경 내용을 저장합니다.

## <a name="known-issues"></a>알려진 문제

**문제**: 추가 사용자 지정 탭이 포함된 사용자 지정 템플릿에서 팀을 만든 경우 사용자 지정 탭 앱 대신 빈 탭이 표시될 수 있습니다. 기본 탭(예: **게시물****, 파일** 및 **위키**)이 예상대로 표시됩니다.

**해결** 방법: 이 문제를 해결하려면 사용자 지정 탭을 제거하고 동일한 앱으로 새 탭을 추가합니다. 사용자 지정 탭을 제거하고 새 탭을 추가할 권한이 없는 경우 팀 소유자에게 문의하여 도움을 요청하세요.

현재 사용자 지정 템플릿에서 만든 향후 팀에 대한 수정 작업을 진행 중입니다.

**문제**: 브라우저에서 Teams 경우 일부 웹 사이트는 웹 사이트 탭 내에서 렌더링되는 것을 Teams 없습니다.

![브라우저 오류 메시지입니다.](media/browser-error-message.png)

**해결** 방법: 웹 사이트 탭의 내용을 보는 데 문제가 있는 경우 웹 사이트 탭 앱을 보기 위해 데스크톱 앱에서 탭을 열거나 데스크톱 앱에서 탭을 Teams 리디렉션됩니다.

## <a name="related-topics"></a>관련 항목

- [관리 센터에서 팀 템플릿 시작](get-started-with-teams-templates-in-the-admin-console.md)
- [기존 팀에서 템플릿 만들기](create-template-from-existing-team.md)
- [기존 팀 템플릿에서 팀 템플릿 만들기](create-template-from-existing-template.md)
