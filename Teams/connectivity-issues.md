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
ms.openlocfilehash: ee6cb916388dbfc0109185a0280da052980f8ccd
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137758"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="52f84-103">Microsoft Teams 클라이언트의 연결 문제 해결</span><span class="sxs-lookup"><span data-stu-id="52f84-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="52f84-104">Microsoft Teams 클라이언트에서 발견되는 대부분의 문제는 방화벽 또는 프록시 연결 문제로 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="52f84-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="52f84-105">방화벽 또는 프록시에서 필수 URL, IP 주소 및 포트가 열려 있는지 확인하면 불필요한 문제 해결을 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="52f84-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="52f84-106">Microsoft Teams에서 필요한 URL 및 IP에 대한 자세한 내용은 [Office 365 URL 및 IP 주소](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) 지원 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="52f84-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="52f84-107">다음 시나리오는 방화벽에서 특정 URL 및 포트가 열려 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="52f84-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="52f84-108">인증</span><span class="sxs-lookup"><span data-stu-id="52f84-108">Authentication</span></span>

-   <span data-ttu-id="52f84-109">Microsoft Teams 클라이언트 연결</span><span class="sxs-lookup"><span data-stu-id="52f84-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="52f84-110">공동 작업</span><span class="sxs-lookup"><span data-stu-id="52f84-110">Collaboration</span></span>

-   <span data-ttu-id="52f84-111">미디어</span><span class="sxs-lookup"><span data-stu-id="52f84-111">Media</span></span>

-   <span data-ttu-id="52f84-112">공유 서비스</span><span class="sxs-lookup"><span data-stu-id="52f84-112">Shared Services</span></span>

-   <span data-ttu-id="52f84-113">타사 통합</span><span class="sxs-lookup"><span data-stu-id="52f84-113">Third Party Integration</span></span>

-   <span data-ttu-id="52f84-114">비즈니스용 Skype 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="52f84-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="52f84-115">비즈니스용 Skype 클라이언트 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="52f84-115">Skype for Business Client Interoperability</span></span>
