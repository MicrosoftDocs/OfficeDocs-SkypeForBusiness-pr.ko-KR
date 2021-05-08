---
title: 온라인 커넥터 비즈니스용 Skype 다운로드 및 설치
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 9c1cc3dc-7d6d-43ca-8e4a-7763a3f78cb3
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 다운로드, 설치 및 비즈니스용 Skype 온라인 커넥터를 사용하여 Windows PowerShell 온라인에 연결하는 원격 Windows PowerShell 세션을 비즈니스용 Skype.
ms.openlocfilehash: e9429b385f83f6b76e211614f953f7d439df524e
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238869"
---
# <a name="download-and-install-the-teams-powershell-module"></a><span data-ttu-id="2a90d-103">PowerShell Teams 다운로드 및 설치</span><span class="sxs-lookup"><span data-stu-id="2a90d-103">Download and install the Teams PowerShell module</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!NOTE]

> <span data-ttu-id="2a90d-104">최신 Teams PowerShell 공개 릴리스는 비즈니스용 Skype Online 커넥터와 통합되어 온라인 [PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) 관리 및 Teams 비즈니스용 Skype 모듈을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2a90d-104">The latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams and Skype for Business online PowerShell management.</span></span>


1. <span data-ttu-id="2a90d-105">[PowerShell Teams 설치합니다.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="2a90d-105">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="2a90d-106">명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2a90d-106">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="2a90d-107">시작에 대한 자세한 Windows PowerShell 을 참조하세요커넥트 Microsoft 365 Office 365 단일 창에서 모든 Windows PowerShell 또는 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) [](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window)</span><span class="sxs-lookup"><span data-stu-id="2a90d-107">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="2a90d-108">관련 주제</span><span class="sxs-lookup"><span data-stu-id="2a90d-108">Related topics</span></span>
[<span data-ttu-id="2a90d-109">비즈니스용 Skype 온라인 관리용 컴퓨터를 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2a90d-109">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)
