---
title: SharePoint Online 사이트 또는 페이지에서 Teams '인트라넷 포털 앱' 만들기
author: LanaChin
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
ms.openlocfilehash: 4777b744d76415f45718cb274f402556e1e28240
ms.sourcegitcommit: b381d8f0b9fc45133d52175fa85901b66e744abd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "44326585"
---
# <a name="create-a-teams-intranet-portal-app-from-a-sharepoint-online-site-or-page"></a><span data-ttu-id="4765a-103">SharePoint Online 사이트 또는 페이지에서 Teams '인트라넷 포털 앱' 만들기</span><span class="sxs-lookup"><span data-stu-id="4765a-103">Create a Teams 'Intranet Portal app' from a SharePoint Online site or page</span></span>

<span data-ttu-id="4765a-104">이 문서의 단계를 사용하여 Teams 안에 조직의 인트라넷 사이트로 연결되는 독립 실행형 정적 앱을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-104">Use the steps in this article to create a standalone and static app inside of Teams that links to the intranet site for your org.</span></span>

<span data-ttu-id="4765a-105">SharePoint 인트라넷 사이트의 *Teams 개인 앱*이 만들어져 Teams 내에서 탭으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-105">A *Teams Personal App* of your SharePoint intranet site is created, and will appear as a tab inside of Teams.</span></span> <span data-ttu-id="4765a-106">이 탭에는 모든 Teams 사용자에게 중요한 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-106">This tab can contain information important to all your Teams users.</span></span> <span data-ttu-id="4765a-107">이런 식으로 Teams 사용자는 단지 탭을 클릭하여 빠르고 간편하게 업데이트에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-107">It is a quick and convenient way for Teams users to access updates just a tab click away.</span></span>

<span data-ttu-id="4765a-108">표시된 프로세스가 제대로 작동하려면 *최신* SharePoint 사이트 또는 페이지를 **사용해야** 합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-108">Be aware that the process shown **must use** a *modern* SharePoint site or page to work.</span></span> <span data-ttu-id="4765a-109">이 프로세스는 *대표* 사이트나 페이지에서는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-109">This process is not available for *classical* sites or pages.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4765a-110">테넌트에 Teams 앱의 테스트용 로드가 사용 설정되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-110">Make certain that side-loading of Teams apps is enabled for your tenant.</span></span> <span data-ttu-id="4765a-111">Teams 관리 포털의 마이그레이션 프로세스 내 현재 단계를 기준으로 Teams > 관리자, 또는 이전 버전의 포털에서는 관리자 > 설정 > 서비스 및 추가 기능 > Microsoft Teams > 앱 > 외부 앱에서 이 기능을 사용하도록 설정할 필요가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-111">Depending on where you are in the migration process of the Teams Admin portal, you might need to enable it either under Teams > Admin, or under Admin > Settings > Services and Add-ins > Microsoft Teams > Apps > External Apps, in the previous version of the portal!</span></span>

## <a name="use-app-studio-to-create-your-standalone-sharepoint-online-app"></a><span data-ttu-id="4765a-112">App Studio를 사용해 독립 실행형 SharePoint Online 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="4765a-112">Use App Studio to create your standalone SharePoint Online app</span></span>

<span data-ttu-id="4765a-113">시작하기 전에 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-113">Before you begin:</span></span>

1. <span data-ttu-id="4765a-114">SharePoint Online의 최신 커뮤니케이션이나 Team 사이트 또는 페이지의 URL을 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-114">You'll need to know the URL of a SharePoint Online modern Communication or Team site, or page.</span></span>
    - <span data-ttu-id="4765a-115">이런 사이트의 경로에는 항상 */teams/* 또는 */sites/* 가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-115">These sites will always have either */teams/* or */sites/* in their paths.</span></span>

2. <span data-ttu-id="4765a-116">테넌트의 하위 도메인을 알아야 하며, **{{subdomain}}** 자리 표시자에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-116">You'll need to know your tenant's subdomain, which will be used in the placeholder **{{subdomain}}**.</span></span>

3. <span data-ttu-id="4765a-117">이 문서에서는 **{{siteUrl}}** 을(를) 사용자가 선택한 사이트 또는 페이지의 *URL*에 대한 자리 표시자로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-117">This article will use **{{siteUrl}}** as a placeholder for the *URL* of the site or page you chose.</span></span>
    - <span data-ttu-id="4765a-118">*URL* 예:   https://contoso.sharepoint.com/teams/Contoso   *또는* https://contoso.sharepoint.com/sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="4765a-118">Example *URLs*:   https://contoso.sharepoint.com/teams/Contoso   *or* https://contoso.sharepoint.com/sites/Contoso</span></span>
4. <span data-ttu-id="4765a-119">또한, **{{sitePath}}** 는 URL의 *경로*(예: /teams/Contoso)를 표시하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-119">Also, **{{sitePath}}** will be used to denote the *path* of the URL (ex: /teams/Contoso).</span></span>
    - <span data-ttu-id="4765a-120">*경로* 예:   /teams/Contoso   *또는* /sites/Contoso</span><span class="sxs-lookup"><span data-stu-id="4765a-120">Example *paths*:   /teams/Contoso   *or* /sites/Contoso</span></span>

<span data-ttu-id="4765a-121">아래 단계에 따라 시작하세요.</span><span class="sxs-lookup"><span data-stu-id="4765a-121">Begin by following the steps below:</span></span>

1. <span data-ttu-id="4765a-122">Teams 스토어로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-122">Go to the Teams Store.</span></span>

2. <span data-ttu-id="4765a-123">App Studio를 설치하거나 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-123">Install or open App Studio.</span></span>

3. <span data-ttu-id="4765a-124">앱 옵션 옆의 **열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-124">Click **Open**, next to the App option.</span></span>

4. <span data-ttu-id="4765a-125">App Studio를 연 상태에서 **매니페스트 편집기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-125">With App Studio open, click on **Manifest Editor**.</span></span>

5. <span data-ttu-id="4765a-126">**새 앱을 만듭니다**.</span><span class="sxs-lookup"><span data-stu-id="4765a-126">**Create a new app**.</span></span>

6. <span data-ttu-id="4765a-127">**앱 세부 정보**를 모두 기입합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-127">Fill in all **App Details**.</span></span>

7. <span data-ttu-id="4765a-128">기능의 **탭**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-128">Click on **Tabs** under Capabilities.</span></span>

8. <span data-ttu-id="4765a-129">개인 탭에서 **추가**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-129">Click **Add** under Personal Tab.</span></span>

9. <span data-ttu-id="4765a-130">**이름**을 입력하고 **새 고유 엔터티 ID**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-130">Fill in the **Name** and choose **a new unique Entity ID**.</span></span>

10. <span data-ttu-id="4765a-131">**contentURL 및 웹 사이트 URL**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-131">Fill in the **contentURL and Website URL**.</span></span>

- <span data-ttu-id="4765a-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span><span class="sxs-lookup"><span data-stu-id="4765a-132">**contentUrl**: {{siteUrl}}/_layouts/15/teamslogon.aspx?SPFX=true&dest={{sitePath}}</span></span>  
- <span data-ttu-id="4765a-133">**websiteUrl**: {{siteUrl}}</span><span class="sxs-lookup"><span data-stu-id="4765a-133">**websiteUrl**: {{siteUrl}}</span></span>

    <span data-ttu-id="4765a-134">**contentURL** 예: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span><span class="sxs-lookup"><span data-stu-id="4765a-134">Example **contentURL**: https://contoso.sharepoint.com/sites/ContosoHub/_layouts/15/teamslogon.aspx?SPFX=true&dest=/sites/ContosoHub</span></span>

11. <span data-ttu-id="4765a-135">**도메인 및 사용 권한**으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-135">Navigate to **Domains and Permissions**.</span></span> <span data-ttu-id="4765a-136">유효한 도메인 섹션에 SharePoint Online 도메인 이름이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-136">Make sure the valid domains section contains your SharePoint online domain name.</span></span>

    <span data-ttu-id="4765a-137">예: contoso.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="4765a-137">Example: contoso.sharepoint.com</span></span>

12. <span data-ttu-id="4765a-138">다음 웹 앱 **single sign-on** 속성을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-138">Add the following web app **single sign-on** properties:</span></span>

     <span data-ttu-id="4765a-139">예: **AAD 응용 프로그램 ID**: 00000003-0000-0ff1-ce00-000000000000  **리소스 Url**: {{subdomain}}.sharepoint.com</span><span class="sxs-lookup"><span data-stu-id="4765a-139">Example:  **AAD application ID**: 00000003-0000-0ff1-ce00-000000000000  **Resource Url**: {{subdomain}}.sharepoint.com</span></span>

    ![ID와 URL을 사용한 웹 앱 single sign-on입니다.](media/personal-app.png)

13. <span data-ttu-id="4765a-141">이러한 속성을 **저장**한 다음 **테스트 및 배포**로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-141">**Save** these properties and then navigate to **Test and distribute**.</span></span>

14. <span data-ttu-id="4765a-142">앱을 설치하여 응용 프로그램을 개인적으로 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-142">Install the app to test the application personally.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4765a-143">Teams App Studio를 사용하고 있지 않은 경우에는 방금 만든 manifest.JSON 파일을 .zip으로 압축하고, Teams에서 앱 스토어로 이동해 앱 스토어의 오른쪽 아래에 있는 **사용자 지정 앱 업로드** 링크를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-143">If you aren't using Teams App Studio, you will have to .zip the manifest.JSON file you just created, navigate to the App Store in Teams, and click  **upload custom app** link (at the bottom right of the App Store).</span></span> <span data-ttu-id="4765a-144">이러면 앱을 사용할 수 있게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-144">This will make the app available to you.</span></span>

15. <span data-ttu-id="4765a-145">이제 Teams에서 앱을 로드하여 정적 탭으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-145">Now the app is available as a static tab for you to load and view in Teams.</span></span>

## <a name="test-and-view-your-new-static-tab"></a><span data-ttu-id="4765a-146">새 정적 탭 테스트 및 보기</span><span class="sxs-lookup"><span data-stu-id="4765a-146">Test and view your new static tab</span></span>

<span data-ttu-id="4765a-147">Teams 데스크톱에서 새 탭을 보려면 앱 표시줄 왼쪽에 있는 줄임표(**...**)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-147">To view the new tab on the Teams desktop, navigate to the ellipses (**…**) in the left-hand side of your app bar.</span></span> <span data-ttu-id="4765a-148">Teams에서 새 앱을 찾아 로드하고 독립 실행형 응용 프로그램을 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-148">Find your new app, load it, and test your standalone application in Teams.</span></span>

<span data-ttu-id="4765a-149">새 앱을 왼쪽 메뉴의 더 높은 위치에서 표시되도록 하려면 이에 대한 앱 정책 설정을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-149">If you want to make the new app available in the left menu at a higher position, you must use an app policy setting for this.</span></span> <span data-ttu-id="4765a-150">이 설정은 Teams 관리 섹션 > 앱 정책 > 고정 응용 프로그램 추가에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-150">This setting can be found under the Team admin section > app policy > add a pinned application.</span></span> <span data-ttu-id="4765a-151">테스트용으로 사용자에게 정책을 할당하면 변경 내용이 몇 시간 후에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-151">When you assign the policy to a user for testing, the change will appear a few hours later.</span></span> <span data-ttu-id="4765a-152">이 점을 염두에 두고 앱이 지연되는 것을 방지하도록 사용자의 편의를 위해 가능한 빨리 앱이 표시되어야 하는 위치를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-152">With this in mind, please decide where the app should appear at your earliest convenience to help avoid delays.</span></span>

<span data-ttu-id="4765a-153">모바일 장치에서 새 앱을 보고 테스트하려면 화면 아래쪽 근처에 있는 탭 모음 위에 있는 갈매기형 수장(**^**)을 탭하여 앱 서랍을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-153">To view and test the new app on a mobile device, open the app drawer by tapping on the chevron (**^**) above the tab bar near the bottom of your screen.</span></span> <span data-ttu-id="4765a-154">모바일 장치에서 앱을 찾아 해당 앱으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-154">Find your app and navigate to it on your mobile device.</span></span>

> [!CAUTION]
> <span data-ttu-id="4765a-155">모바일 지원은 현재 개발자 미리 보기에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-155">Mobile support is currently in Developer Preview.</span></span> <span data-ttu-id="4765a-156">개발자 미리 보기를 사용하도록 설정하려면 설정 > 정보로 이동한 다음 개발자 미리 보기 모드를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-156">To enable Developer Preview, navigate to Settings > About and then enable Developer Preview mode.</span></span>

## <a name="a-sample-manifestjson-file"></a><span data-ttu-id="4765a-157">샘플 Manifest.JSON 파일</span><span class="sxs-lookup"><span data-stu-id="4765a-157">A Sample Manifest.JSON file</span></span>

<span data-ttu-id="4765a-158">사용자가 생성하는 JSO        파일이 아래와 같이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4765a-158">The JSO        file you generate will look something like the one below.</span></span>

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
