---
title: PowerShell을 사용 하 여 팀에 대 한 게스트 액세스 제어
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 06/25/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: sbhatta
search.appverid: MET150
description: PowerShell을 사용 하 여 Microsoft 팀의 팀에 대 한 게스트 액세스를 허용 하거나 차단 합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e106dc56f56b5e26dd56384931deeecdd889305
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235880"
---
<a name="use-powershell-to-control-guest-access-to-a-team"></a><span data-ttu-id="380c8-103">PowerShell을 사용 하 여 팀에 대 한 게스트 액세스 제어</span><span class="sxs-lookup"><span data-stu-id="380c8-103">Use PowerShell to control guest access to a team</span></span>
================================================

<span data-ttu-id="380c8-104">Microsoft 365 관리 센터 및 azure AD (Active Directory) 포털을 사용 하는 것 외에도 Windows PowerShell을 사용 하 여 게스트 액세스를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="380c8-104">In addition to using the Microsoft 365 admin center and the Azure Active Directory (Azure AD) portal, you can use Windows PowerShell to control guest access.</span></span> <span data-ttu-id="380c8-105">PowerShell을 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="380c8-105">With PowerShell, you can do the following:</span></span>
  
- <span data-ttu-id="380c8-106">모든 팀 및 Office 365 그룹에 대 한 게스트 액세스 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="380c8-106">Allow or block guest access to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="380c8-107">모든 팀 및 Office 365 그룹에 게스트를 추가할 수 있도록 허용</span><span class="sxs-lookup"><span data-stu-id="380c8-107">Allow guests to be added to all teams and Office 365 Groups</span></span>

- <span data-ttu-id="380c8-108">특정 팀 또는 Office 365 그룹의 게스트 사용자 허용 또는 차단</span><span class="sxs-lookup"><span data-stu-id="380c8-108">Allow or block guest users from a specific team or Office 365 group</span></span>

<span data-ttu-id="380c8-109">자세한 내용은 [Office 365 그룹의 게스트 액세스 관리](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access)에서 PowerShell을 사용 하 여 게스트 액세스 제어 "를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="380c8-109">For details, see "Use PowerShell to control guest access" in [Manage guest access in Office 365 Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-guest-access-in-groups#use-powershell-to-control-guest-access).</span></span>
  
<span data-ttu-id="380c8-110">PowerShell을 사용 하 여 해당 도메인에 따라 게스트 사용자를 허용 하거나 차단할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="380c8-110">You can also use PowerShell to allow or block a guest user based on their domain.</span></span> <span data-ttu-id="380c8-111">예를 들어, 회사 (Contoso)에 다른 비즈니스 (Fabrikam)와의 파트너 관계가 있다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="380c8-111">For example, let's say your business (Contoso) has a partnership with another business (Fabrikam).</span></span> <span data-ttu-id="380c8-112">사용자가 그룹에 해당 게스트를 추가할 수 있도록 허용 목록에 Fabrikam을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="380c8-112">You can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span> <span data-ttu-id="380c8-113">자세한 내용은 [Office 365 그룹에 대 한 게스트 액세스 허용/차단](https://go.microsoft.com/fwlink/?linkid=854001)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="380c8-113">For more information, see [Allow/Block guest access to Office 365 Groups](https://go.microsoft.com/fwlink/?linkid=854001).</span></span>
  
<span data-ttu-id="380c8-114">팀에서 게스트를 차단 하 고 SharePoint 사이트에 대 한 액세스를 허용 하려는 경우 Azure AD Powershell cmdlet을 사용 하 여 SharePoint 사이트에 대 한 외부 공유가 설정 되어 있다고 가정 하 고 회사 개체의 AllowGuestsToAccessGroups 매개 변수를 사용 하지 않도록 설정할 수 있습니다. .</span><span class="sxs-lookup"><span data-stu-id="380c8-114">If you want to block guests in Teams and still want to allow them to access SharePoint sites, you can use Azure AD Powershell cmdlets to disable the AllowGuestsToAccessGroups parameter on the Company object, assuming external sharing is turned on for SharePoint sites.</span></span>

## <a name="guest-access-vs-external-access"></a><span data-ttu-id="380c8-115">게스트 액세스와 외부 액세스 비교</span><span class="sxs-lookup"><span data-stu-id="380c8-115">Guest access vs. external access</span></span>

[!INCLUDE [guest-vs-external-access](includes/guest-vs-external-access.md)]
