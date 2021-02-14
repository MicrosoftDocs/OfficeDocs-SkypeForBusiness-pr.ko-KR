---
title: 비즈니스용 Skype Online Connector에서 Teams PowerShell 모듈로 이동
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 비즈니스용 Skype Online Connector에서 Teams PowerShell 모듈로 이동하여 Teams를 관리하는 방법을 배워야 합니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469673"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="13efb-103">비즈니스용 Skype Online Connector에서 Teams PowerShell 모듈로 이동</span><span class="sxs-lookup"><span data-stu-id="13efb-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="13efb-104">비즈니스용 Skype Online Connector에서 Teams PowerShell 모듈로 이동하여 Teams를 관리하려면 기존 PowerShell 스크립트를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13efb-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="13efb-105">이 문서에서는 이 작업을 하는 방법을 설명하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13efb-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="13efb-106">최신 Teams PowerShell 모듈을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="13efb-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="13efb-107">단계는 Microsoft [Teams Powershell 설치를 참조하세요.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="13efb-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="13efb-108">비즈니스용 Skype Online Connector를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="13efb-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="13efb-109">이렇게하려면 제어판에서 프로그램 및 기능으로 **이동하여** **비즈니스용 Skype Online,** Windows PowerShell 모듈을 선택한 다음 **제거를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="13efb-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="13efb-110">PowerShell 스크립트에서 참조되는 모듈 이름을 ```Import-Module``` ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams``` 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="13efb-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="13efb-111">예를 들어 ```Import-Module -Name SkypeOnlineConnector``` . ```Import-Module -Name MicrosoftTeams```</span><span class="sxs-lookup"><span data-stu-id="13efb-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>

> [!NOTE]
> <span data-ttu-id="13efb-112">관리자는 비즈니스용 Skype Online cmdlet을 사용하기 전에 [New-CsOnlineSession을](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) 계속 사용하고 세션을 가져와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13efb-112">Admins should continue to use [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) and import the session before using Skype for Business Online cmdlets.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="13efb-113">관련 항목</span><span class="sxs-lookup"><span data-stu-id="13efb-113">Related topics</span></span>

[<span data-ttu-id="13efb-114">Microsoft Teams Powershell 설치</span><span class="sxs-lookup"><span data-stu-id="13efb-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="13efb-115">Teams PowerShell을 사용하여 Teams 관리</span><span class="sxs-lookup"><span data-stu-id="13efb-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="13efb-116">Teams PowerShell 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="13efb-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="13efb-117">Microsoft Teams cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="13efb-117">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="13efb-118">비즈니스용 Skype cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="13efb-118">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
