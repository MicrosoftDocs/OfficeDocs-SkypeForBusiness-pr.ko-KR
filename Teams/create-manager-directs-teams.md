---
title: Microsoft 팀에서 사람 관리자 팀 만들기
ms.reviewer: pbethi
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
description: PowerShell 스크립트를 사용 하 여 팀 구성원으로 해당 하는 각 관리자의 팀을 만드는 방법에 대해 알아봅니다.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: eb6cd6ed74bebd0cbd729b828c152b9f04d1fc1f
ms.sourcegitcommit: cfaae3ecbf853766de788b4825a86e04f68868ca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/18/2020
ms.locfileid: "42796224"
---
# <a name="create-people-manager-teams-in-microsoft-teams"></a><span data-ttu-id="68531-103">Microsoft 팀에서 사람 관리자 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="68531-103">Create people manager teams in Microsoft Teams</span></span>


<span data-ttu-id="68531-104">Microsoft 팀에 "빈 슬레이트" (팀 또는 채널 없음)를 사용 하 여 시작 하지 않고 배포 하는 경우 팀 및 채널의 기본 프레임 워크를 설정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="68531-104">When you roll out Microsoft Teams, rather than launching with a "blank slate" (no teams or channels), we strongly recommend that you set up a base framework of teams and channels.</span></span> <span data-ttu-id="68531-105">이렇게 하면 사용자가 기존 팀에서 채널을 만들 때 많은 팀을 만들 수 있는 "팀 sprawl"를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68531-105">This helps to prevent "team sprawl," where users create numerous teams when they should be creating channels in existing teams.</span></span> <span data-ttu-id="68531-106">잘 디자인 된 팀과 채널 구조를 시작 하는 데 도움이 되도록 각 관리자의 다이렉트 보고서와 팀 구성원으로 각각의 첫 번째 및 두 번째 줄 사람 관리자를 위한 팀을 만드는 PowerShell 스크립트를 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="68531-106">To help you get started with a well-designed teams and channels structure, we've created a PowerShell script that creates a team for each of your first and second line people managers, with each manager's direct reports as team members.</span></span> <span data-ttu-id="68531-107">이 스크립트는 조직에서 사용자를 추가 하거나 제거할 때 팀 또는 채널이 자동으로 업데이트 되지 않는다는 점에서 "시계열" 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="68531-107">This is a "point-in-time" script (it doesn't update your teams or channels automatically when people are added or removed from an organization).</span></span> <span data-ttu-id="68531-108">그러나 시작부터 팀 구조에 몇 가지 주문을 부과 하는 데 사용할 수 있는 유용한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="68531-108">But it's a valuable tool you can use to impose some order on your Teams structure from the start.</span></span> <span data-ttu-id="68531-109">이 스크립트는 Azure AD를 읽고 관리자 및 해당 부하 직원의 목록을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="68531-109">This script reads your Azure AD, gets a list of managers and their direct reports.</span></span> <span data-ttu-id="68531-110">이 목록을 사용 하 여 사람 관리자 한 명에 게 팀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="68531-110">It uses this list to create one team per people manager.</span></span> 

## <a name="how-to-use-the-powershell-script"></a><span data-ttu-id="68531-111">PowerShell 스크립트를 사용 하는 방법</span><span class="sxs-lookup"><span data-stu-id="68531-111">How to use the PowerShell script</span></span> 

<span data-ttu-id="68531-112">[내보내기 관리자 및 해당](scripts/powershell-script-create-teams-from-managers-export-managers.md) 하는 연결 스크립트 ( [AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) 및 [MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell 모듈을 이미 실행 했다고 가정)를 실행 하 여 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="68531-112">Start by running the [Export managers and their directs script](scripts/powershell-script-create-teams-from-managers-export-managers.md) (which assumes you've already run the [Connect-AzureAd](https://docs.microsoft.com/powershell/module/azuread/connect-azuread?view=azureadps-2.0) and [Connect-MicrosoftTeams](https://docs.microsoft.com/powershell/module/teams/connect-microsoftteams?view=teams-ps) PowerShell modules).</span></span> <span data-ttu-id="68531-113">*내보내기 관리자와 해당 하* 는 스크립트는 직접 보고서가 있는 모든 관리자를 나열 하는 탭으로 구분 된 파일 (ExportedManagerDirects)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="68531-113">The *Export managers and their directs* script creates a tab-delimited file (ExportedManagerDirects.txt) that lists all managers with their direct reports.</span></span> 

<span data-ttu-id="68531-114">그런 다음, [새 people manager 팀 만들기 스크립트](scripts/powershell-script-create-teams-from-managers-new-teams.md)를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="68531-114">Then, run the [Create new people manager teams script](scripts/powershell-script-create-teams-from-managers-new-teams.md).</span></span> <span data-ttu-id="68531-115">이 스크립트는 ExportedManagerDirects 파일을 읽고 관리자의 직접 보고서를 구성원으로 사용 하 여 각 관리자를 위한 팀을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="68531-115">This script reads in the ExportedManagerDirects.txt file and creates a team for each manager, with that manager's direct reports as members.</span></span> <span data-ttu-id="68531-116">팀에 대 한 관리자 또는 다이렉트가 활성화 되지 않은 경우 스크립트는이를 건너뛰고 팀을 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68531-116">If any manager or direct isn't enabled for Teams, the script skips them and doesn't create a team.</span></span> <span data-ttu-id="68531-117">(보고서를 검토 한 다음 필요한 모든 사용자에 대해 팀을 켠 후에 스크립트를 다시 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="68531-117">(Review the report, then rerun the script after you've turned on Teams for anybody who needs it.</span></span> <span data-ttu-id="68531-118">이 스크립트는 이미 팀을 만든 관리자를 위해 두 번째 팀을 만들지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68531-118">The script won't create a second team for any manager it's already created a team for.)</span></span>

<span data-ttu-id="68531-119">각 팀에 대해 스크립트는 일반 및 "재미 있는" 채널을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="68531-119">For each team, the script creates a General and "Just for fun" channel.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="68531-120">모범 사례</span><span class="sxs-lookup"><span data-stu-id="68531-120">Best practices</span></span>

- <span data-ttu-id="68531-121">각 사용자 관리자에 게 조직의 위기 소통 웹사이트를 각 팀의 일반 채널에 탭으로 추가 해 달라고 요청 합니다.</span><span class="sxs-lookup"><span data-stu-id="68531-121">Ask each people manager to add your organization's crisis communications website as a tab to the General channel for each team.</span></span> 

- <span data-ttu-id="68531-122">이 2020 3 월 8 일 블로그 게시물을 읽고 새 위기 소통 앱을 확인 하세요. [Microsoft 팀 + 파워 플랫폼을 사용 하 여 위기 통신을 조정](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715)합니다.</span><span class="sxs-lookup"><span data-stu-id="68531-122">Check out the new Crisis Communications app by reading this March 8, 2020 blog post: [Coordinate crisis communications using Microsoft Teams + Power Platform](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/coordinate-crisis-communications-using-microsoft-teams-power/ba-p/1216715).</span></span>

## <a name="related-topics"></a><span data-ttu-id="68531-123">관련 항목</span><span class="sxs-lookup"><span data-stu-id="68531-123">Related topics</span></span>

[<span data-ttu-id="68531-124">팀 구성 모범 사례</span><span class="sxs-lookup"><span data-stu-id="68531-124">Best practices for organizing teams</span></span>](best-practices-organizing.md)

[<span data-ttu-id="68531-125">Teams에서 조직 전체 팀 만들기</span><span class="sxs-lookup"><span data-stu-id="68531-125">Create an org-wide team in Teams</span></span>](create-an-org-wide-team.md)
