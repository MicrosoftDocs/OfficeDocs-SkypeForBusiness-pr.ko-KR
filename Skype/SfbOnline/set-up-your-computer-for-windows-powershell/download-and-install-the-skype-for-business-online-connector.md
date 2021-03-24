---
title: 비즈니스용 Skype Online 커넥터 모듈 다운로드 및 설치
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
description: 비즈니스용 Skype Online 커넥터를 다운로드, 설치 및 사용하여 비즈니스용 Skype online에 Windows PowerShell 원격 세션을 만들 수 있습니다.
ms.openlocfilehash: 0e00b9dd18b04deaf3d2123de1fa9609040c4e2f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097204"
---
# <a name="download-and-install-the-teams-powershell-module"></a><span data-ttu-id="d435d-103">Teams PowerShell 모듈 다운로드 및 설치</span><span class="sxs-lookup"><span data-stu-id="d435d-103">Download and install the Teams PowerShell module</span></span>

> [!NOTE]

> <span data-ttu-id="d435d-104">최신 [Teams PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/) 공개 릴리스는 비즈니스용 Skype Online 커넥터와 통합되어 Teams 및 비즈니스용 Skype 온라인 PowerShell 관리를 위한 단일 모듈을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d435d-104">The latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams and Skype for Business online PowerShell management.</span></span>


1. <span data-ttu-id="d435d-105">Teams [PowerShell 모듈을 설치합니다.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="d435d-105">Install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
2. <span data-ttu-id="d435d-106">명령 Windows PowerShell 프롬프트를 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d435d-106">Open a Windows PowerShell command prompt and run the following commands:</span></span> 

   ```powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```
   <span data-ttu-id="d435d-107">시작에 대한 자세한 Windows PowerShell 단일 창에서 모든 [Microsoft 365 또는 Office 365](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) 서비스에 연결하거나 Windows PowerShell 에 대한 컴퓨터를 [Windows PowerShell.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="d435d-107">If you want more information about starting Windows PowerShell, see [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](/microsoft-365/enterprise/connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window) or [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d435d-108">관련 항목</span><span class="sxs-lookup"><span data-stu-id="d435d-108">Related topics</span></span>
[<span data-ttu-id="d435d-109">비즈니스용 Skype 온라인 관리용 컴퓨터를 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d435d-109">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)