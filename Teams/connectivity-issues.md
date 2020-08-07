---
title: 팀 클라이언트의 연결 문제 해결
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 52097d78a3eae14bcaba98fb1613092af97d302e
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581139"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="8f2ec-103">Microsoft Teams 클라이언트의 연결 문제 해결</span><span class="sxs-lookup"><span data-stu-id="8f2ec-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="8f2ec-104">Microsoft Teams 클라이언트에서 발견되는 대부분의 문제는 방화벽 또는 프록시 연결 문제로 추적됩니다.</span><span class="sxs-lookup"><span data-stu-id="8f2ec-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="8f2ec-105">방화벽 또는 프록시에서 필수 URL, IP 주소 및 포트가 열려 있는지 확인하면 불필요한 문제 해결을 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f2ec-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="8f2ec-106">Microsoft 팀에 필요한 Url 및 Ip에 대 한 특정 정보는 [microsoft 365 및 Office 365 url 및 IP 주소](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) 지원 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8f2ec-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="8f2ec-107">다음 시나리오는 방화벽에서 특정 URL 및 포트가 열려 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8f2ec-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="8f2ec-108">인증</span><span class="sxs-lookup"><span data-stu-id="8f2ec-108">Authentication</span></span>

-   <span data-ttu-id="8f2ec-109">Microsoft Teams 클라이언트 연결</span><span class="sxs-lookup"><span data-stu-id="8f2ec-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="8f2ec-110">공동 작업</span><span class="sxs-lookup"><span data-stu-id="8f2ec-110">Collaboration</span></span>

-   <span data-ttu-id="8f2ec-111">미디어</span><span class="sxs-lookup"><span data-stu-id="8f2ec-111">Media</span></span>

-   <span data-ttu-id="8f2ec-112">공유 서비스</span><span class="sxs-lookup"><span data-stu-id="8f2ec-112">Shared Services</span></span>

-   <span data-ttu-id="8f2ec-113">타사 통합</span><span class="sxs-lookup"><span data-stu-id="8f2ec-113">Third Party Integration</span></span>

-   <span data-ttu-id="8f2ec-114">비즈니스용 Skype 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="8f2ec-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="8f2ec-115">비즈니스용 Skype 클라이언트 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="8f2ec-115">Skype for Business Client Interoperability</span></span>


## <a name="related-topics"></a><span data-ttu-id="8f2ec-116">관련 항목</span><span class="sxs-lookup"><span data-stu-id="8f2ec-116">Related topics</span></span>

[<span data-ttu-id="8f2ec-117">Teams 문제 해결</span><span class="sxs-lookup"><span data-stu-id="8f2ec-117">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)