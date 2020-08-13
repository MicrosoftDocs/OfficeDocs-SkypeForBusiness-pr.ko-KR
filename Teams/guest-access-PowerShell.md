---
title: PowerShell을 사용하여 팀에 대한 액세스 권한 제어
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
f1.keywords:
- NOCSH
description: PowerShell을 사용 하 여 Microsoft 팀의 모든 팀 또는 특정 팀에 대 한 게스트 액세스를 허용 하거나 차단 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b7e2833d1afedb975edf2532fb69c4fdbbdb31d4
ms.sourcegitcommit: 875c854547b5d3ad838ad10c1eada3f0cddc8e66
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/13/2020
ms.locfileid: "46655909"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="2a690-103">PowerShell을 사용하여 팀에 대한 액세스 권한 제어</span><span class="sxs-lookup"><span data-stu-id="2a690-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="2a690-104">Microsoft 365 관리 센터 및 azure AD (Active Directory) 포털을 사용 하는 것 외에도 Windows PowerShell을 사용 하 여 게스트 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a690-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="2a690-105">PowerShell을 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a690-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="2a690-106">모든 팀과 Microsoft 365 그룹에 대 한 게스트 액세스 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="2a690-106">Allow or block guest access to all teams and Microsoft 365 Groups</span></span>

- <span data-ttu-id="2a690-107">모든 팀과 Microsoft 365 그룹에 게스트를 추가할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="2a690-107">Allow guests to be added to all teams and Microsoft 365 Groups</span></span>

- <span data-ttu-id="2a690-108">특정 팀 또는 Microsoft 365 그룹의 게스트 사용자 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="2a690-108">Allow or block guest users from a specific team or Microsoft 365 group</span></span>

<span data-ttu-id="2a690-109">자세한 내용은 [Microsoft 365 그룹의 게스트 액세스 관리](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups)에서 PowerShell을 사용 하 여 게스트 액세스 제어 "를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2a690-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Microsoft 365 Groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups).</span></span>

  
<span data-ttu-id="2a690-110">PowerShell을 사용 하 여 해당 도메인에 따라 게스트 사용자를 허용 하거나 차단할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a690-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="2a690-111">예를 들어, 회사 (Contoso)에 다른 비즈니스 (Fabrikam)와의 파트너 관계가 있다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="2a690-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="2a690-112">사용자가 그룹에 해당 게스트를 추가할 수 있도록 허용 목록에 Fabrikam을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a690-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="2a690-113">자세한 내용은 [Microsoft 365 그룹에 대 한 게스트 액세스 허용/차단](https://go.microsoft.com/fwlink/?linkid=854001)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2a690-113">For more information, see [Allow/Block guest access to Microsoft 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="2a690-114">팀에서 게스트를 차단 하 고 SharePoint 사이트에 대 한 액세스를 허용 하려는 경우 Azure AD PowerShell cmdlet을 사용 하 여 SharePoint 사이트에 대해 외부 공유가 설정 되어 있다고 가정 하 고 회사 개체의 AllowGuestsToAccessGroups 매개 변수를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a690-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD PowerShell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="use-powershell-to-turn-guest-access-on-or-off"></a><span data-ttu-id="2a690-115">PowerShell을 사용하여 게스트 액세스 켜기 또는 끄기</span><span class="sxs-lookup"><span data-stu-id="2a690-115">Use PowerShell to turn guest access on or off</span></span>

1.  <span data-ttu-id="2a690-116">에서 비즈니스용 Skype Online PowerShell 모듈 다운로드https://www.microsoft.com/download/details.aspx?id=39366</span><span class="sxs-lookup"><span data-stu-id="2a690-116">Download the Skype for Business Online PowerShell module from https://www.microsoft.com/download/details.aspx?id=39366</span></span>
 
2.  <span data-ttu-id="2a690-117">비즈니스용 Skype Online 끝점에 PowerShell 세션을 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a690-117">Connect a PowerShell session to the Skype for Business Online endpoint.</span></span>

    ```powershell
    Import-Module SkypeOnlineConnector
    $Cred = Get-Credential
    $CSSession = New-CsOnlineSession -Credential $Cred
    Import-PSSession -Session $CSSession
    ```
    
3.  <span data-ttu-id="2a690-118">구성을 확인 하 고 `AllowGuestUser` `$False` , 설정 된 경우 [CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet을 사용 하 여 설정 `$True` 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a690-118">Check your configuration and if `AllowGuestUser` is `$False`, use the [Set-CsTeamsClientConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csteamsclientconfiguration?view=skype-ps) cmdlet to set it to `$True`.</span></span>

    ```powershell
    Get-CsTeamsClientConfiguration

    Identity                         : Global
    AllowEmailIntoChannel            : True
    RestrictedSenderList             :
    AllowDropBox                     : True
    AllowBox                         : True
    AllowGoogleDrive                 : True
    AllowShareFile                   : True
    AllowOrganizationTab             : True
    AllowSkypeBusinessInterop        : True
    ContentPin                       : RequiredOutsideScheduleMeeting
    AllowResourceAccountSendMessage  : True
    ResourceAccountContentAccess     : NoAccess
    AllowGuestUser                   : True
    AllowScopedPeopleSearchandAccess : False
    
    Set-CsTeamsClientConfiguration -AllowGuestUser $True -Identity Global
    ```
<span data-ttu-id="2a690-119">이제 조직의 팀에서 게스트 사용자를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a690-119">You can now have guest users in Teams for your organization.</span></span>


## <a name="guest-access-vs-external-access"></a><span data-ttu-id="2a690-120">게스트 액세스와 외부 액세스 비교</span><span class="sxs-lookup"><span data-stu-id="2a690-120">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
