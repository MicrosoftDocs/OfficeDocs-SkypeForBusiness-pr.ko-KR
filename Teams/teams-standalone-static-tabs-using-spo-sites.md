---
title: SharePoint Online 사이트 또는 페이지에서 팀의 인트라넷 포털 앱을 만듭니다.
author: LanaChin
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
description: 기존 SharePoint Online 사이트 또는 페이지를 사용 하 고 조직의 인트라넷 포털로 사용할 수 있는 독립 실행형 정적 탭을 만듭니다.
localization_priority: Normal
ms.openlocfilehash: 772063a7444e9c31d2740ac48635dc0f2e367435
ms.sourcegitcommit: aaae9df142ebb844a1fea27d3ae3b95130903d6a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2020
ms.locfileid: "43100366"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a>SharePoint Online 사이트 또는 페이지에서 팀의 인트라넷 포털 앱을 만듭니다.

이 문서의 단계를 사용 하 여 조직의 인트라넷 사이트로 연결 되는 팀 내에서 독립 실행형 및 정적 앱을 만들 수 있습니다.

SharePoint 인트라넷 사이트의 *팀 개인 앱* 이 만들어지고 팀 내에서 탭으로 표시 됩니다. 이 탭에는 모든 팀 사용자에 게 중요 한 정보가 포함 될 수 있습니다. 팀 사용자가 탭을 클릭 하는 것 만으로 업데이트에 액세스할 수 있는 빠르고 편리한 방법입니다.

표시 된 프로세스는 *최신* SharePoint 사이트 또는 페이지를 사용 하 여 작업 **해야** 한다는 점에 유의 하세요. *클래식* 사이트 또는 페이지에서는이 프로세스를 사용할 수 없습니다.

> [!IMPORTANT]
> 테 넌 트에 대해 팀 앱에 대 한 사용자의 부하를 허용 하는지 확인 합니다. 팀 관리자 포털의 마이그레이션 프로세스 위치에 따라 팀 > 관리자 또는 관리 > 설정에서 서비스 및 추가 기능 >의 이전 버전 포털에서 Microsoft 팀 > 앱 > 외부 앱을 > 수 있습니다. 

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a>앱 Studio를 사용 하 여 독립 실행형 SharePoint Online 앱 만들기

시작 하기 전에:
1. SharePoint Online 최신 통신 또는 팀 사이트 또는 페이지의 URL을 알고 있어야 합니다.
    - 이러한 사이트의 경로에는 항상 */teams/* 또는 */sites/* 이 있습니다.

2. 자리 표시자 **{{하위 도메인}}** 에 사용 되는 테 넌 트의 하위 도메인을 알고 있어야 합니다.

3. 이 문서는 **{{siteUrl}}** 자리 표시자를 사용 하 여 사용자가 선택한 사이트 또는 페이지의 *URL* 입니다.
    - 예제 *url*: https://contoso.sharepoint.com/teams/Contoso *또는*   https://contoso.sharepoint.com/sites/Contoso 
4. 또한 **{{Sitepath}}** 는 URL의 *경로* 를 나타내는 데 사용 됩니다 (예:/teams/Contoso).
    - *경로*예:/Teams/Contoso *또는* /sites/Contoso 

다음 단계를 따라 시작 합니다.

1. 팀 스토어로 이동 합니다.

2. App Studio를 설치 하거나 엽니다.

3. **열기**를 클릭 하 고 앱 옵션 옆에 있습니다.

4. 앱 Studio를 열고 **매니페스트 편집기**를 클릭 합니다.

5. **새 앱을 만듭니다**.

6. 모든 **앱 세부 정보**를 입력 합니다.

7. 기능에서 **탭** 을 클릭 합니다.

8. 개인 탭에서 **추가** 를 클릭 합니다.

9. **이름을** 입력 하 고 **새 고유 엔터티 ID를**선택 합니다.

10. **콘텐츠 url 및 웹 사이트 url**을 입력 합니다. 

- **Contenturl**: {{siteUrl}}/_layouts/15/teamslogon.aspx? SPFX = true&dest = {{sitePath}}  
- **websiteUrl**: {{siteUrl}} 

    예제 **Contenturl**:https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub 

11. **도메인 및 사용 권한**으로 이동 합니다. 유효한 domains (도메인) 섹션에 SharePoint online 도메인 이름이 있는지 확인 합니다.

    예: contoso.sharepoint.com

12. 다음 웹 앱 **single sign-on** 속성을 추가 합니다. 
     
     예: **AAD APPLICATION ID**: 00000003-0000-0ff1-ce00-000000000000 **리소스 Url**: {{하위 도메인}}. h t m

    ![ID 및 URL이 있는 웹 앱 single sign-on입니다.](media/personal-app.png)

13. 이러한 속성을 **저장** 한 다음 **테스트 및 배포**로 이동 합니다. 

14. 앱을 설치 하 여 응용 프로그램을 개별적으로 테스트 합니다.

> [!IMPORTANT]
> 팀 앱 Studio를 사용 하지 않는 경우 매니페스트에 .zip. 방금 만든 JSON 파일에서 팀의 App Store로 이동 하 고 **사용자 지정 앱 업로드** 링크 (App Store 오른쪽 아래)를 클릭 합니다. 이렇게 하면 앱을 사용할 수 있게 됩니다.

15. 이제 앱을 정적 탭으로 사용 하 여 팀에서 로드 하 고 볼 수 있습니다.

## <a name="test-and-view-your-new-static-tab"></a>새 정적 탭 테스트 및 보기

팀 바탕 화면에서 새 탭을 보려면 앱 표시줄의 왼쪽에 있는 줄임표 (**...**)로 이동 합니다. 팀에서 새 앱을 찾아 로드 하 고 독립 실행형 응용 프로그램을 테스트 합니다.

왼쪽 메뉴에서 새 앱을 더 높은 위치에 사용할 수 있도록 하려면 앱 정책 설정을 사용 해야 합니다. 이 설정은 팀 관리 섹션 > 앱 정책 > 고정 된 응용 프로그램 추가를 통해 찾을 수 있습니다. 테스트를 위해 사용자에 게 정책을 할당 하면 변경 내용이 24 시간 후에 표시 됩니다. 이 점에 유의 하 여 지연을 방지 하는 데 도움이 되는 앱이 가장 빠른 시간에 나타날 위치를 결정 하세요.

모바일 장치에서 새 앱을 보고 테스트 하려면 화면 아래쪽 근처에 있는 탭 표시줄 위의 갈매기형 수장 (**^**)을 눌러 앱 서랍을 엽니다. 모바일 장치에서 앱을 찾아 탐색 합니다.

> [!CAUTION]
> 모바일 지원은 현재 개발자 미리 보기 상태입니다. 개발자 미리 보기를 사용 하도록 설정 하려면 개발자 미리 보기 모드에 대 한 > 설정을 탐색 하 고 사용 하도록 설정 합니다.

## <a name="a-sample-manifestjson-file"></a>샘플 매니페스트. JSON 파일

생성 되는 JSON 파일은 아래와 유사 하 게 표시 됩니다.

```JSON
{ 

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json", 

    "manifestVersion": "1.5", 

    "version": "1.0.0", 

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873", 

    "packageName": "com.contoso.teams.devapp", 

    "developer": { 

        "name": "Contoso", 

        "websiteUrl": "https://www.contoso.com", 

        "privacyUrl": "https://www.contoso.com/privacy", 

        "termsOfUseUrl": "https://www.contoso.com/terms" 

    }, 

    "icons": { 

        "color": "color.png", 

        "outline": "outline.png" 

    }, 

    "name": { 

        "short": "Contoso Intranet", 

        "full": "Intranet Portal for Contoso" 

    }, 

    "description": { 

        "short": "Intranet portal for Contoso", 

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams" 

    }, 

    "accentColor": "#FFFFFF", 

    "staticTabs": [ 

        { 

            "entityId": "communicationSiteTab", 

            "name": "Contoso Net", 

            "contentUrl": "https://contoso.sharepoint.com/sites/ContosoNet/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoNet/", 

            "websiteUrl": "https://contoso.sharepoint.com/sites/ContosoNet", 

            "scopes": [ 

                "personal" 

            ] 

        }, 

        { 

            "entityId": "teamSiteTab", 

            "name": "Team Contoso", 

            "contentUrl": "https://contoso.sharepoint.com/teams/TeamContoso/_layouts/15/teamslogon.aspx?SPFX=true&dest=/teams/TeamContoso/", 

            "websiteUrl": "https://contoso.sharepoint.com/teams/TeamContoso", 

            "scopes": [ 

                "personal" 

            ] 

        } 

    ], 

    "permissions": [ 

        "identity", 

        "messageTeamMembers" 

    ], 

    "validDomains": [ 

        "contoso.sharepoint.com" 

    ], 

    "webApplicationInfo": { 

        "id": "00000003-0000-0ff1-ce00-000000000000", 

        "resource": "https://contoso.sharepoint.com" 

    } 

}
```