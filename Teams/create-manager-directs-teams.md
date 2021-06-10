---
title: 사용자 관리자 팀을 Microsoft Teams
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: PowerShell 스크립트를 사용하여 팀 구성원으로 지시를 사용하여 각 관리자에 대한 팀을 만드는 방법에 대해 자세히 알아보습니다.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fa7c82ec584791107e5d269ee40bccba272d20b4
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094414"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="65b95-103">사용자 관리자 팀을 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="65b95-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="65b95-104">"빈 Microsoft Teams"(팀 또는 채널 없음)을 시작하지 않고 롤아웃할 때 팀 및 채널의 기본 프레임워크를 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="65b95-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="65b95-105">이렇게 하면 사용자가 기존 팀에서 채널을 만들어야 할 때 사용자가 수많은 팀을 만드는 "팀 스프라우"를 방지하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="65b95-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="65b95-106">잘 디자인된 팀 및 채널 구조를 시작할 수 있도록 각 관리자의 직접 보고서를 팀 구성원으로 사용하여 첫 번째 및 두 번째 줄의 각 관리자에 대한 팀을 만드는 PowerShell 스크립트를 만들어 졌습니다.</span><span class="sxs-lookup"><span data-stu-id="65b95-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="65b95-107">이 스크립트는 "지점 시간" 스크립트입니다(조직에서 사용자가 추가되거나 제거될 때 팀 또는 채널을 자동으로 업데이트하지 않습니다).</span><span class="sxs-lookup"><span data-stu-id="65b95-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="65b95-108">그러나 이 도구는 시작부터 Teams 순서를 부과하는 데 사용할 수 있는 유용한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="65b95-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="65b95-109">이 스크립트는 Azure AD를 읽고 관리자 목록과 해당 직접 보고서를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="65b95-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="65b95-110">이 목록을 사용하여 사용자 관리자당 하나의 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65b95-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="65b95-111">PowerShell 스크립트를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="65b95-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="65b95-112">먼저 [내보내기](scripts/powershell-script-create-teams-from-managers-export-managers.md) 관리자 및 해당 지시 스크립트를 실행합니다(이미 [커넥트-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) 및 [커넥트-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell 모듈을 실행했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="65b95-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="65b95-113">*내보내기* 관리자 및 해당 지시 스크립트는 모든 관리자를 직접 보고서로 나열하는 탭 ExportedManagerDirects.txt 파일(ExportedManagerDirects.txt)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65b95-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="65b95-114">그런 다음 새 사용자 관리자 [팀 만들기 스크립트 를 실행합니다.](scripts/powershell-script-create-teams-from-managers-new-teams.md)</span><span class="sxs-lookup"><span data-stu-id="65b95-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="65b95-115">이 스크립트는 ExportedManagerDirects.txt 각 관리자에 대한 팀을 만들고 해당 관리자의 직접 보고서를 구성원으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65b95-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="65b95-116">관리자 또는 직접이 Teams 경우 스크립트가 건너뛰고 팀을 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="65b95-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="65b95-117">(보고서를 검토한 다음, 필요한 모든 사용자에 대해 Teams 설정한 후 스크립트를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="65b95-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="65b95-118">스크립트는 이미 팀을 만든 관리자에 대해 두 번째 팀을 만들지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="65b95-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="65b95-119">각 팀에 대해 스크립트는 일반 및 "그냥 재미"채널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="65b95-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="65b95-120">모범 사례</span><span class="sxs-lookup"><span data-stu-id="65b95-120">Best practices</span></span>

- <span data-ttu-id="65b95-121">각 사용자 관리자에게 조직의 위기 통신 웹 사이트를 각 팀의 일반 채널에 탭으로 추가해 보세요.</span><span class="sxs-lookup"><span data-stu-id="65b95-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="65b95-122">이 2020년 3월 8일 블로그 게시물: Microsoft Teams + Power Platform을 사용하여 위기 [통신을 조정하여](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)새 위기 통신 앱을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="65b95-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="65b95-123">관련 항목</span><span class="sxs-lookup"><span data-stu-id="65b95-123">Related topics</span></span>

[<span data-ttu-id="65b95-124">팀 구성에 대한 모범 사례</span><span class="sxs-lookup"><span data-stu-id="65b95-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="65b95-125">Teams에서 조직 전체 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="65b95-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)