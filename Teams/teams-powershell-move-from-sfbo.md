---
title: 비즈니스용 Skype Online 커넥터에서 팀 PowerShell 모듈로 이동
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 비즈니스용 Skype Online 커넥터에서 팀 PowerShell 모듈로 이동 하 여 팀을 관리 하는 방법에 대해 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e1838540e57cd91578e898818e2ed12e7b63a78
ms.sourcegitcommit: 51d94d621e3411f35622e852b699275f526600dd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2020
ms.locfileid: "48469673"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="94b4f-103">비즈니스용 Skype Online 커넥터에서 팀 PowerShell 모듈로 이동</span><span class="sxs-lookup"><span data-stu-id="94b4f-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="94b4f-104">비즈니스용 Skype Online 커넥터를 팀 PowerShell 모듈로 이동 하 여 팀을 관리 하려면 기존 PowerShell 스크립트를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94b4f-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="94b4f-105">이 문서에서는이 작업을 수행 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="94b4f-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="94b4f-106">최신 팀 PowerShell 모듈을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="94b4f-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="94b4f-107">단계는 [Microsoft 팀 Powershell 설치](teams-powershell-install.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="94b4f-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="94b4f-108">비즈니스용 Skype Online Connector를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="94b4f-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="94b4f-109">이렇게 하려면 제어판에서 **프로그램 및 기능**으로 이동 하 여 비즈니스용 **Skype Online, Windows PowerShell 모듈**을 선택한 다음 **제거**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="94b4f-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="94b4f-110">PowerShell 스크립트에서 from 또는 to에서 참조 되는 모듈 이름을 변경 ```Import-Module``` ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams``` 합니다.</span><span class="sxs-lookup"><span data-stu-id="94b4f-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="94b4f-111">예를 들어 ```Import-Module -Name SkypeOnlineConnector``` 로 변경 ```Import-Module -Name MicrosoftTeams``` 합니다.</span><span class="sxs-lookup"><span data-stu-id="94b4f-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>

> [!NOTE]
> <span data-ttu-id="94b4f-112">비즈니스용 Skype Online cmdlet을 사용 하기 전에 관리자가 계속 해 서 [CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) 를 사용 하 고 세션을 가져오세요.</span><span class="sxs-lookup"><span data-stu-id="94b4f-112">Admins should continue to use [New-CsOnlineSession](https://docs.microsoft.com/powershell/module/skype/new-csonlinesession) and import the session before using Skype for Business Online cmdlets.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="94b4f-113">관련 항목</span><span class="sxs-lookup"><span data-stu-id="94b4f-113">Related topics</span></span>

[<span data-ttu-id="94b4f-114">Microsoft 팀 Powershell 설치</span><span class="sxs-lookup"><span data-stu-id="94b4f-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="94b4f-115">팀을 사용 하 여 팀 관리 PowerShell</span><span class="sxs-lookup"><span data-stu-id="94b4f-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="94b4f-116">팀 PowerShell 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="94b4f-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="94b4f-117">Microsoft 팀 cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="94b4f-117">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="94b4f-118">비즈니스용 Skype cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="94b4f-118">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
