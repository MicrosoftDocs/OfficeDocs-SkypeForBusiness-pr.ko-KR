---
title: SharePoint Online 사이트 또는 페이지에서 Teams '인트라넷 포털 앱' 만들기
author: cichur
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
- remotework
ms.reviewer: vinbel
search.appverid: MET150
description: 기존 SharePoint Online 사이트 또는 페이지를 이용해 조직의 인트라넷 포털로 사용할 수 있는 독립 실행형 정적 탭을 만듭니다.
localization_priority: Priority
ms.openlocfilehash: 1b89a17f81024fba05a1be9fb1dc4d59b1aceafd
ms.sourcegitcommit: 67782296062528bbeade5cb9074143fee0536646
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/24/2020
ms.locfileid: "49731116"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a>SharePoint Online 사이트 또는 페이지에서 Teams '인트라넷 포털 앱' 만들기

이 문서의 단계를 사용하여 Teams 안에 조직의 인트라넷 사이트로 연결되는 독립 실행형 정적 앱을 만듭니다.

SharePoint 인트라넷 사이트의 *Teams 개인 앱* 이 만들어져 Teams 내에서 탭으로 표시됩니다. 이 탭에는 모든 Teams 사용자에게 중요한 정보를 포함할 수 있습니다. 이런 식으로 Teams 사용자는 단지 탭을 클릭하여 빠르고 간편하게 업데이트에 액세스합니다.

표시된 프로세스가 제대로 작동하려면 *최신* SharePoint 사이트 또는 페이지를 **사용해야** 합니다. 이 프로세스는 *대표* 사이트나 페이지에서는 사용할 수 없습니다.

> [!IMPORTANT]
> 테넌트에 Teams 앱의 테스트용 로드가 사용 설정되어 있는지 확인합니다. Teams 관리 포털의 마이그레이션 프로세스 내 현재 단계를 기준으로 Teams > 관리자, 또는 이전 버전의 포털에서는 관리자 > 설정 > 서비스 및 추가 기능 > Microsoft Teams > 앱 > 외부 앱에서 이 기능을 사용하도록 설정할 필요가 있을 수 있습니다.

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a>App Studio를 사용해 독립 실행형 SharePoint Online 앱 만들기

시작하기 전에 다음을 수행해야 합니다.

1. SharePoint Online의 최신 커뮤니케이션이나 Team 사이트 또는 페이지의 URL을 알아야 합니다.
    - 이런 사이트의 경로에는 항상 */teams/* 또는 */sites/* 가 있습니다.

2. 테넌트의 하위 도메인을 알아야 하며, **{{subdomain}}** 자리 표시자에 사용됩니다.

3. 이 문서에서는 **{{siteUrl}}** 을(를) 사용자가 선택한 사이트 또는 페이지의 *URL* 에 대한 자리 표시자로 사용합니다.
    - *URL* 예: `https://contoso.sharepoint.com/teams/Contoso`
        *또는* `https://contoso.sharepoint.com/sites/Contoso`
4. 또한, **{{sitePath}}** 는 URL의 *경로*(예: /teams/Contoso)를 표시하는 데 사용됩니다.
    - *경로* 예:   /teams/Contoso   *또는* /sites/Contoso

아래 단계에 따라 시작하세요.

1. Teams 스토어로 이동합니다.

2. App Studio를 설치하거나 엽니다.

3. 앱 옵션 옆의 **열기** 를 클릭합니다.

4. App Studio를 연 상태에서 **매니페스트 편집기** 를 클릭합니다.

5. **새 앱을 만듭니다**.

6. **앱 세부 정보** 를 모두 기입합니다.

7. 기능의 **탭** 을 클릭합니다.

8. 개인 탭에서 **추가** 를 클릭합니다.

9. **이름** 을 입력하고 **새 고유 엔터티 ID** 를 선택합니다.

10. **contentURL 및 웹 사이트 URL** 을 입력합니다.

- **contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}  
- **websiteUrl**: {{siteUrl}}

    **contentURL** 예: `https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub`

11. **도메인 및 사용 권한** 으로 이동합니다. 유효한 도메인 섹션에 SharePoint Online 도메인 이름이 있는지 확인합니다.

    예: `contoso.sharepoint.com`

12. 다음 웹 앱 **single sign-on** 속성을 추가합니다.

     예: **AAD 응용 프로그램 ID**: 00000003-0000-0ff1-ce00-000000000000  **리소스 Url**: {{subdomain}}.sharepoint.com

    ![ID와 URL을 사용한 웹 앱 single sign-on입니다.](media/personal-app.png)

13. 이러한 속성을 **저장** 한 다음 **테스트 및 배포** 로 이동합니다.

14. 앱을 설치하여 응용 프로그램을 개인적으로 테스트합니다.

> [!IMPORTANT]
> Teams App Studio를 사용하고 있지 않은 경우에는 방금 만든 manifest.JSON 파일을 .zip으로 압축하고, Teams에서 앱 스토어로 이동해 앱 스토어의 오른쪽 아래에 있는 **사용자 지정 앱 업로드** 링크를 클릭합니다. 이러면 앱을 사용할 수 있게 됩니다.

15. 이제 Teams에서 앱을 로드하여 정적 탭으로 볼 수 있습니다.

## <a name="test-and-view-your-new-static-tab"></a>새 정적 탭 테스트 및 보기

Teams 데스크톱에서 새 탭을 보려면 앱 표시줄 왼쪽에 있는 줄임표(**...**)로 이동합니다. Teams에서 새 앱을 찾아 로드하고 독립 실행형 응용 프로그램을 테스트합니다.

새 앱을 왼쪽 메뉴의 더 높은 위치에서 표시되도록 하려면 이에 대한 앱 정책 설정을 사용해야 합니다. 이 설정은 Teams 관리 섹션 > 앱 정책 > 고정 응용 프로그램 추가에 있습니다. 테스트용으로 사용자에게 정책을 할당하면 변경 내용이 몇 시간 후에 나타납니다. 이 점을 염두에 두고 앱이 지연되는 것을 방지하도록 사용자의 편의를 위해 가능한 빨리 앱이 표시되어야 하는 위치를 결정합니다.

모바일 장치에서 새 앱을 보고 테스트하려면 화면 아래쪽 근처에 있는 탭 모음 위에 있는 갈매기형 수장(**^**)을 탭하여 앱 서랍을 엽니다. 모바일 장치에서 앱을 찾아 해당 앱으로 이동합니다.

> [!CAUTION]
> 모바일 지원은 현재 개발자 미리 보기에 있습니다. 개발자 미리 보기를 사용하도록 설정하려면 설정 > 정보로 이동한 다음 개발자 미리 보기 모드를 사용하도록 설정합니다.

## <a name="a-sample-manifestjson-file"></a>샘플 Manifest.JSON 파일

사용자가 생성하는 JSON 파일이 아래와 같이 표시됩니다.

```JSON'
{

    "$schema": "https://developer.microsoft.com/en-us/json-schemas/teams/v1.5/MicrosoftTeams.schema.json",

    "manifestVersion": "1.5",

    "version": "1.0.0",

    "id": "33ebded3-931c-4333-b0c5-b51dd8738873",

    "packageName": "com.contoso.teams.devapp",

    "developer": {

        "name": "Contoso", ''

        "websiteUrl": "https://www.contoso.com",

        "privacyUrl": "https://www.contoso.com/privacy",

        "termsOfUseUrl": "https://www.contoso.com/terms"

    },

    "icons": {

        "color": "color.png",

        "outline": "outline.png"

    },

    "name": {

        "short": "Contoso Intranet", '

        "full": "Intranet Portal for Contoso"

    },

    "des    ription": {

        "short": "Intranet portal for Contoso",

        "full": "This app is to demonstrate the capabilities of hosting a SharePoint communication and team site as a standalone app in Teams"

    },

    "accentColor": "#FFFFFF",

    "staticTabs": [

        {

                     "       nti        Id":       "com    unicat    onSi    eTab",

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
