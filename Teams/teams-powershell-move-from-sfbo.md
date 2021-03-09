---
title: 비즈니스용 Skype Online 커넥터에서 Teams PowerShell 모듈로 이동
author: pupara
ms.author: pupara
ms.reviewer: pupara
manager: bulenteg
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.collection:
- M365-collaboration
description: 비즈니스용 Skype Online 커넥터에서 Teams PowerShell 모듈로 이동하여 Teams를 관리하는 방법에 대해 자세히 알아보습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32029de1ec33ee89c8dba30d8368131b291fc3f8
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569084"
---
# <a name="move-from-skype-for-business-online-connector-to-the-teams-powershell-module"></a><span data-ttu-id="813ac-103">비즈니스용 Skype Online 커넥터에서 Teams PowerShell 모듈로 이동</span><span class="sxs-lookup"><span data-stu-id="813ac-103">Move from Skype for Business Online Connector to the Teams PowerShell module</span></span>

<span data-ttu-id="813ac-104">비즈니스용 Skype Online 커넥터를 Teams PowerShell 모듈로 이동하여 Teams를 관리하려면 기존 PowerShell 스크립트를 업데이트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="813ac-104">To move from using Skype for Business Online Connector to the Teams PowerShell module to manage Teams, you'll need to update your existing PowerShell scripts.</span></span> <span data-ttu-id="813ac-105">이 문서에서는 이 작업을 하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="813ac-105">This article explains how to do this.</span></span>

1. <span data-ttu-id="813ac-106">최신 Teams PowerShell 모듈을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="813ac-106">Install the latest Teams PowerShell module.</span></span> <span data-ttu-id="813ac-107">단계에 대한 자세한 내용은 [Microsoft Teams Powershell 설치를 참조하세요.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="813ac-107">For steps, see [Install Microsoft Teams Powershell](teams-powershell-install.md).</span></span>
2. <span data-ttu-id="813ac-108">비즈니스용 Skype Online 커넥터를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="813ac-108">Uninstall Skype For Business Online Connector.</span></span> <span data-ttu-id="813ac-109">이렇게하려면 제어판에서 프로그램 및 기능으로 **이동하고** 비즈니스용 **Skype Online을** 선택하고 모듈을 Windows PowerShell 선택한 다음 제거를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="813ac-109">To do this, in Control Panel, go **Programs and Features**, select **Skype for Business Online, Windows PowerShell Module**, and then select **Uninstall**.</span></span> 
3. <span data-ttu-id="813ac-110">PowerShell 스크립트에서 에서 또는 로 참조되는 모듈 이름을 ```Import-Module``` ```SkypeOnlineConnector``` ```LyncOnlineConnector``` ```MicrosoftTeams``` 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="813ac-110">In your PowerShell scripts, change the module name that's referenced in ```Import-Module``` from ```SkypeOnlineConnector``` or ```LyncOnlineConnector``` to ```MicrosoftTeams```.</span></span>

    <span data-ttu-id="813ac-111">예를 들어 으로 ```Import-Module -Name SkypeOnlineConnector``` ```Import-Module -Name MicrosoftTeams``` 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="813ac-111">For example, change ```Import-Module -Name SkypeOnlineConnector``` to ```Import-Module -Name MicrosoftTeams```.</span></span>
4. <span data-ttu-id="813ac-112">Teams PowerShell 모듈 2.0 이상을 사용하는 경우 New-csOnlineSession을 Connect-MicrosoftTeams로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="813ac-112">When using Teams PowerShell Module 2.0 or later, change New-csOnlineSession to Connect-MicrosoftTeams.</span></span> 

```powershell
  # When using Teams PowerShell Module 1.1.6
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   $sfbSession = New-CsOnlineSession -Credential $credential
   Import-PSSession $sfbSession
   
   # When using Teams PowerShell Module 2.0 or later
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```

## <a name="related-topics"></a><span data-ttu-id="813ac-113">관련 항목</span><span class="sxs-lookup"><span data-stu-id="813ac-113">Related topics</span></span>

[<span data-ttu-id="813ac-114">Microsoft Teams Powershell 설치</span><span class="sxs-lookup"><span data-stu-id="813ac-114">Install Microsoft Teams Powershell</span></span>](teams-powershell-install.md)

[<span data-ttu-id="813ac-115">Teams PowerShell을 사용하여 팀 관리</span><span class="sxs-lookup"><span data-stu-id="813ac-115">Manage Teams with Teams PowerShell</span></span>](teams-powershell-managing-teams.md)

[<span data-ttu-id="813ac-116">Teams PowerShell 릴리스 정보</span><span class="sxs-lookup"><span data-stu-id="813ac-116">Teams PowerShell release notes</span></span>](teams-powershell-release-notes.md)

[<span data-ttu-id="813ac-117">Microsoft Teams cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="813ac-117">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)

[<span data-ttu-id="813ac-118">비즈니스용 Skype cmdlet 참조</span><span class="sxs-lookup"><span data-stu-id="813ac-118">Skype for Business cmdlet reference</span></span>](https://docs.microsoft.com/powershell/skype/intro?view=skype-ps)
