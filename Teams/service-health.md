---
title: Microsoft 팀의 서비스 상태 확인
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
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
description: 팀 서비스가 정상 인지, 그리고 Exchange, SharePoint, 비즈니스용 OneDrive 등의 다른 Microsoft 365 또는 Office 365 구성 요소를 확인 하는 것도 좋은 방법입니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1451750d5e329ddb27307b21334fb7d281255d73
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690174"
---
<a name="verify-service-health-for-microsoft-teams"></a><span data-ttu-id="a72a8-103">Microsoft 팀의 서비스 상태 확인</span><span class="sxs-lookup"><span data-stu-id="a72a8-103">Verify service health for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="a72a8-104">Microsoft 팀의 서비스 상태는 Microsoft 365 관리 센터에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a72a8-104">Service health for Microsoft Teams is displayed on the Microsoft 365 admin center.</span></span> <span data-ttu-id="a72a8-105">문제를 해결 하기 전에 팀 서비스가 정상 인지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a72a8-105">Before troubleshooting issues, it's a good practice to verify that the Teams service is healthy.</span></span> <span data-ttu-id="a72a8-106"><a href=" https://admin.microsoft.com/adminportal/home?ref=servicehealth" target="_blank">팀 서비스 상태</a> 콘솔로 이동 하 여 서비스 상태를 검토 합니다.</span><span class="sxs-lookup"><span data-stu-id="a72a8-106">Go to the <a href=" https://admin.microsoft.com/adminportal/home?ref=servicehealth" target="_blank">Teams Service Health</a> console to review the service health.</span></span>

<span data-ttu-id="a72a8-107">또한 Microsoft 팀은 추가 Microsoft 365 또는 Office 365 서비스에 기반을 두고 있으며, 서비스 상태를 확인할 때 Exchange, SharePoint, 비즈니스용 OneDrive의 상태도 확인 해야 한다는 것을 기억 하세요.</span><span class="sxs-lookup"><span data-stu-id="a72a8-107">Also, keep in mind that, Microsoft Teams is built on top of additional Microsoft 365 or Office 365 services, so when looking at Service Health, remember to also check the status of Exchange, SharePoint, and OneDrive for Business.</span></span> <span data-ttu-id="a72a8-108">이러한 다른 서비스에 대 한 서비스 상태 문제는 팀에 영향을 주는 것 (예: Exchange에서 주소록 다운로드를 사용할 수 없음)을 자동으로 의미 하지 않지만 해당 서비스에 대 한 권고를 검토 하 여 Microsoft 팀에 게 영향이 있는지 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a72a8-108">Service Health issues for these other services does not automatically mean that Teams is impacted (e.g. Address Book downloads in Exchange are unavailable), but that you should review the advisories for those affected services to determine if there is an impact to Microsoft Teams.</span></span>

![서비스 상태 페이지 스크린샷](media/Verify_service_health_for_Microsoft_Teams_image1.png)

![Microsoft 팀 서비스를 보여 주는 스크린샷은 정상 상태입니다.](media/Verify_service_health_for_Microsoft_Teams_image2.png)
