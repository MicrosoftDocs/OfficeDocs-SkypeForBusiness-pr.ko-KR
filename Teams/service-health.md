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
description: Teams 서비스뿐만 아니라 Exchange, SharePoint 및 비즈니스용 OneDrive와 같은 다른 Microsoft 365 또는 Office 365 구성 요소도 정상 상태인지 확인하는 것이 좋습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 600bf8802dfb76dc1e96534be0ee303354267661
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581839"
---
<a name="verify-service-health-for-microsoft-teams"></a><span data-ttu-id="a4e55-103">Microsoft Teams의 서비스 상태 확인</span><span class="sxs-lookup"><span data-stu-id="a4e55-103">Verify service health for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="a4e55-104">Microsoft Teams의 서비스 상태는 Microsoft 365 관리 센터에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4e55-104">Service health for Microsoft Teams is displayed on the Microsoft 365 admin center.</span></span> <span data-ttu-id="a4e55-105">문제를 해결하기 전에 Teams 서비스가 정상 상태인지 확인하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a4e55-105">Before troubleshooting issues, it's a good practice to verify that the Teams service is healthy.</span></span> <span data-ttu-id="a4e55-106"><a href=" https://admin.microsoft.com/adminportal/home?ref=servicehealth" target="_blank">Teams 서비스 상태</a> 콘솔로 이동하여 서비스 상태 검토</span><span class="sxs-lookup"><span data-stu-id="a4e55-106">Go to the <a href=" https://admin.microsoft.com/adminportal/home?ref=servicehealth" target="_blank">Teams Service Health</a> console to review the service health.</span></span>

<span data-ttu-id="a4e55-107">또한 Microsoft Teams는 추가 Microsoft 365 또는 Office 365 서비스를 토대하여 구축되어 있으므로 Service Health를 볼 때 Exchange, SharePoint 및 비즈니스용 OneDrive의 상태도 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e55-107">Also, keep in mind that, Microsoft Teams is built on top of additional Microsoft 365 or Office 365 services, so when looking at Service Health, remember to also check the status of Exchange, SharePoint, and OneDrive for Business.</span></span> <span data-ttu-id="a4e55-108">이러한 다른 서비스에 대한 서비스 상태 문제는 Teams가 자동으로 영향을 받는 것(예: Exchange의 주소장 다운로드를 사용할 수 없음)을 의미하지는 않지만 영향을 받는 서비스에 대한 권고를 검토하여 Microsoft Teams에 영향을 주는지 여부를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4e55-108">Service Health issues for these other services does not automatically mean that Teams is impacted (e.g. Address Book downloads in Exchange are unavailable), but that you should review the advisories for those affected services to determine if there is an impact to Microsoft Teams.</span></span>

![서비스 상태 페이지의 스크린샷.](media/Verify_service_health_for_Microsoft_Teams_image1.png)

![Microsoft Teams 서비스가 정상 상태인 스크린샷](media/Verify_service_health_for_Microsoft_Teams_image2.png)


## <a name="related-topics"></a><span data-ttu-id="a4e55-111">관련 항목</span><span class="sxs-lookup"><span data-stu-id="a4e55-111">Related topics</span></span>

[<span data-ttu-id="a4e55-112">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="a4e55-112">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)