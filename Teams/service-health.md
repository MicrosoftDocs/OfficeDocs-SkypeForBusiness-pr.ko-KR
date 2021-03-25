---
title: Microsoft Teams의 서비스 상태 확인
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: 'Teams 서비스가 정상 상태인지 확인하는 것이 좋습니다. 다른 Microsoft 365 또는 Office 365 구성 요소(예: Exchange, SharePoint 및 비즈니스용 OneDrive)입니다.'
appliesto:
- Microsoft Teams
ms.openlocfilehash: 53184bbdc25cc96e667cd8c0ddff9eae5bfdfe8c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51107514"
---
<a name="verify-service-health-for-microsoft-teams"></a><span data-ttu-id="5c240-103">Microsoft Teams의 서비스 상태 확인</span><span class="sxs-lookup"><span data-stu-id="5c240-103">Verify service health for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="5c240-104">Microsoft Teams의 서비스 상태는 Microsoft 365 관리 센터에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="5c240-104">Service health for Microsoft Teams is displayed on the Microsoft 365 admin center.</span></span> <span data-ttu-id="5c240-105">문제를 해결하기 전에 Teams 서비스가 정상 상태인지 확인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5c240-105">Before troubleshooting issues, it's a good practice to verify that the Teams service is healthy.</span></span> <span data-ttu-id="5c240-106"><a href=" https://admin.microsoft.com/adminportal/home?ref=servicehealth" target="_blank">Teams Service Health 콘솔로</a> 이동하여 서비스 상태 검토</span><span class="sxs-lookup"><span data-stu-id="5c240-106">Go to the <a href=" https://admin.microsoft.com/adminportal/home?ref=servicehealth" target="_blank">Teams Service Health</a> console to review the service health.</span></span>

<span data-ttu-id="5c240-107">또한 Microsoft Teams는 추가 Microsoft 365 또는 Office 365 서비스를 기본으로 구축되어 있으므로 서비스 상태를 볼 때 Exchange, SharePoint 및 비즈니스용 OneDrive 상태도 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c240-107">Also, keep in mind that, Microsoft Teams is built on top of additional Microsoft 365 or Office 365 services, so when looking at Service Health, remember to also check the status of Exchange, SharePoint, and OneDrive for Business.</span></span> <span data-ttu-id="5c240-108">이러한 다른 서비스에 대한 서비스 상태 문제는 Teams가 자동으로 영향을 받는 것(예: Exchange에서 주소 책 다운로드를 사용할 수 없음)을 의미하지는 않지만 영향을 받는 서비스에 대한 권고를 검토하여 Microsoft Teams에 영향을 주는지 여부를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5c240-108">Service Health issues for these other services does not automatically mean that Teams is impacted (e.g. Address Book downloads in Exchange are unavailable), but that you should review the advisories for those affected services to determine if there is an impact to Microsoft Teams.</span></span>

![서비스 상태 페이지의 스크린샷입니다.](media/Verify_service_health_for_Microsoft_Teams_image1.png)

![Microsoft Teams 서비스를 보여주는 스크린샷이 정상입니다.](media/Verify_service_health_for_Microsoft_Teams_image2.png)


## <a name="related-topics"></a><span data-ttu-id="5c240-111">관련 항목</span><span class="sxs-lookup"><span data-stu-id="5c240-111">Related topics</span></span>

[<span data-ttu-id="5c240-112">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="5c240-112">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)