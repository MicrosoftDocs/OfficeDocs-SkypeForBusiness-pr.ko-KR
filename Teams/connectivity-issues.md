---
title: 팀 클라이언트의 연결 문제 해결
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: 주로 방화벽 또는 프록시 연결에서 발생하는 Microsoft Teams 클라이언트의 연결 문제 해결 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cef20522784ba2d63d1461104a51f3148f48cf53
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44689644"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="88940-103">Microsoft Teams 클라이언트의 연결 문제 해결</span><span class="sxs-lookup"><span data-stu-id="88940-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="88940-104">Microsoft Teams 클라이언트에서 발견되는 대부분의 문제는 방화벽 또는 프록시 연결 문제로 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="88940-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="88940-105">방화벽 또는 프록시에서 필수 URL, IP 주소 및 포트가 열려 있는지 확인하면 불필요한 문제 해결을 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88940-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="88940-106">Microsoft 팀에 필요한 Url 및 Ip에 대 한 특정 정보는 [microsoft 365 및 Office 365 url 및 IP 주소](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) 지원 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="88940-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="88940-107">다음 시나리오는 방화벽에서 특정 URL 및 포트가 열려 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="88940-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="88940-108">인증</span><span class="sxs-lookup"><span data-stu-id="88940-108">Authentication</span></span>

-   <span data-ttu-id="88940-109">Microsoft Teams 클라이언트 연결</span><span class="sxs-lookup"><span data-stu-id="88940-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="88940-110">공동 작업</span><span class="sxs-lookup"><span data-stu-id="88940-110">Collaboration</span></span>

-   <span data-ttu-id="88940-111">미디어</span><span class="sxs-lookup"><span data-stu-id="88940-111">Media</span></span>

-   <span data-ttu-id="88940-112">공유 서비스</span><span class="sxs-lookup"><span data-stu-id="88940-112">Shared Services</span></span>

-   <span data-ttu-id="88940-113">타사 통합</span><span class="sxs-lookup"><span data-stu-id="88940-113">Third Party Integration</span></span>

-   <span data-ttu-id="88940-114">비즈니스용 Skype 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="88940-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="88940-115">비즈니스용 Skype 클라이언트 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="88940-115">Skype for Business Client Interoperability</span></span>
