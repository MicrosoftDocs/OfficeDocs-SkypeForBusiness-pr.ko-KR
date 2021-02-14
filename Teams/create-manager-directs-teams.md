---
title: Microsoft Teams에서 사용자 관리자 팀 만들기
ms.reviewer: pbethi
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: PowerShell 스크립트를 사용하여 팀 구성원으로 직접 각 관리자에 대한 팀을 만드는 방법을 배워야 합니다.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: fe57656eec61747dd0a43d475444e65d8600e222
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583677"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="2a0dc-103">Microsoft Teams에서 사용자 관리자 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="2a0dc-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="2a0dc-104">"빈 슬레이트"(팀 또는 채널 없음)로 시작하지 않고 Microsoft Teams를 출시할 때 팀 및 채널의 기본 프레임워크를 설정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2a0dc-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="2a0dc-105">이렇게 하면 사용자가 기존 팀에서 채널을 만들어야 할 때 많은 팀을 만드는 "팀 스플로브"를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a0dc-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="2a0dc-106">잘 디자인된 팀 및 채널 구조를 시작할 수 있도록 각 관리자의 직접 보고서를 팀 구성원으로 사용하여 1줄 및 2줄 사람 관리자 각각에 대한 팀을 만드는 PowerShell 스크립트를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a0dc-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="2a0dc-107">"시점" 스크립트입니다(조직에서 사용자가 추가되거나 제거될 때 팀 또는 채널이 자동으로 업데이트되지는 않습니다).</span><span class="sxs-lookup"><span data-stu-id="2a0dc-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="2a0dc-108">하지만 이 도구는 Teams 구조에 순서를 설정하는 데 사용할 수 있는 유용한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="2a0dc-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="2a0dc-109">이 스크립트는 Azure AD를 읽고 관리자 및 해당 직접 보고서 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0dc-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="2a0dc-110">이 목록을 사용하여 사용자 관리자당 하나의 팀을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2a0dc-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="2a0dc-111">PowerShell 스크립트를 사용하는 방법</span><span class="sxs-lookup"><span data-stu-id="2a0dc-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="2a0dc-112">먼저 [내보내기](scripts/powershell-script-create-teams-from-managers-export-managers.md) 관리자 및 해당 직접 스크립트를 실행합니다(Connect-AzureAd 및 [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell 모듈을 이미 실행했다고 가정). [](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0)</span><span class="sxs-lookup"><span data-stu-id="2a0dc-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="2a0dc-113">내보내기 관리자 및 해당 *직접* 스크립트는 직접 보고서가 있는 모든 관리자를 나열하는 탭으로 ExportedManagerDirects.txt 파일(ExportedManagerDirects.txt)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2a0dc-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="2a0dc-114">그런 다음 새 사용자 관리자 [팀 만들기 스크립트를 실행합니다.](scripts/powershell-script-create-teams-from-managers-new-teams.md)</span><span class="sxs-lookup"><span data-stu-id="2a0dc-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="2a0dc-115">이 스크립트는 ExportedManagerDirects.txt 파일에서 읽고 해당 관리자의 직접 보고서를 구성원으로 사용하여 각 관리자에 대한 팀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2a0dc-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="2a0dc-116">Teams에 대해 관리자나 직접을 사용하도록 설정하지 않은 경우 스크립트에서 해당 관리자를 건너뛰고 팀을 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2a0dc-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="2a0dc-117">(보고서를 검토한 다음 필요한 모든 사용자에 대해 Teams를 설정한 후 스크립트를 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0dc-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="2a0dc-118">스크립트는 이미 팀을 만든 관리자를 위한 두 번째 팀을 만들지 않습니다.)</span><span class="sxs-lookup"><span data-stu-id="2a0dc-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="2a0dc-119">각 팀에 대해 스크립트는 일반 및 "재미를 위해" 채널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2a0dc-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="2a0dc-120">모범 사례</span><span class="sxs-lookup"><span data-stu-id="2a0dc-120">Best practices</span></span>

- <span data-ttu-id="2a0dc-121">각 팀의 일반 채널에 대한 탭으로 조직의 위기 통신 웹 사이트를 추가해달고 각 사용자 관리자에게 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="2a0dc-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="2a0dc-122">2020년 3월 8일 블로그 게시물: Microsoft Teams + Power Platform을 사용하여 위기 통신 조정 게시물을 읽어 새로운 Crisis Communications [앱을 확인해 읽습니다.](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)</span><span class="sxs-lookup"><span data-stu-id="2a0dc-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2a0dc-123">관련 항목</span><span class="sxs-lookup"><span data-stu-id="2a0dc-123">Related topics</span></span>

[<span data-ttu-id="2a0dc-124">팀 구성 모범 사례</span><span class="sxs-lookup"><span data-stu-id="2a0dc-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="2a0dc-125">Teams에서 조직 전체 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="2a0dc-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)
