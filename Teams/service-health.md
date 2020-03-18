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
description: 팀 서비스는 정상 상태이 고 Exchange, SharePoint, 비즈니스용 OneDrive 등의 기타 Office 365 구성 요소를 확인 하는 것이 좋습니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 219c484b4bf8eff35d78966820a3002e55aecbb7
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706578"
---
<a name="verify-service-health-for-microsoft-teams"></a><span data-ttu-id="09130-103">Microsoft 팀의 서비스 상태 확인</span><span class="sxs-lookup"><span data-stu-id="09130-103">Verify service health for Microsoft Teams</span></span>
===========================================

<span data-ttu-id="09130-104">Microsoft 팀의 서비스 상태는 Microsoft 365 관리 센터에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09130-104">Service health for Microsoft Teams is displayed on the Microsoft 365 admin center.</span></span> <span data-ttu-id="09130-105">문제를 해결 하기 전에 팀 서비스가 정상 인지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="09130-105">Before troubleshooting issues, it's a good practice to verify that the Teams service is healthy.</span></span>

<span data-ttu-id="09130-106">또한 Microsoft 팀은 추가 Office 365 서비스를 기반으로 구축 되므로 서비스 상태를 확인할 때 Exchange, SharePoint, 비즈니스용 OneDrive의 상태도 확인 해야 한다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="09130-106">Also, keep in mind that, Microsoft Teams is built on top of additional Office 365 services, so when looking at Service Health, remember to also check the status of Exchange, SharePoint, and OneDrive for Business.</span></span> <span data-ttu-id="09130-107">이러한 다른 서비스에 대 한 서비스 상태 문제는 팀에 영향을 주는 것 (예: Exchange에서 주소록 다운로드를 사용할 수 없음)을 자동으로 의미 하지 않지만 영향을 받는 서비스에 대 한 권고를 검토 하 여 영향을 받는지 확인 해야 합니다. Microsoft 팀.</span><span class="sxs-lookup"><span data-stu-id="09130-107">Service Health issues for these other services does not automatically mean that Teams is impacted (e.g. Address Book downloads in Exchange are unavailable), but that you should review the advisories for those affected services to determine if there is an impact to Microsoft Teams.</span></span>

![서비스 상태 페이지 스크린샷](media/Verify_service_health_for_Microsoft_Teams_image1.png)

![Microsoft 팀 서비스를 보여 주는 스크린샷은 정상 상태입니다.](media/Verify_service_health_for_Microsoft_Teams_image2.png)
