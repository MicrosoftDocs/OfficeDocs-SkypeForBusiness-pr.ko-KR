---
title: Microsoft 팀 클라이언트의 연결 문제 해결
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: 방화벽 또는 프록시 연결로 인해 발생 하는 Microsoft 팀 클라이언트의 연결 문제를 해결 하 고이를 해결 하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 79718ebc58205cd63ab291f0985e4dd7e452be3e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236842"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="031fd-103">Microsoft 팀 클라이언트의 연결 문제 해결</span><span class="sxs-lookup"><span data-stu-id="031fd-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="031fd-104">Microsoft 팀 클라이언트에서 발견 된 대부분의 문제는 방화벽 또는 프록시 연결을 통해 다시 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="031fd-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="031fd-105">방화벽 또는 프록시에서 필요한 Url, IP 주소 및 포트가 열려 있는지 확인 하면 불필요 한 문제 해결이 최소화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="031fd-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="031fd-106">Microsoft 팀에 필요한 Url 및 Ip에 대 한 특정 정보는 [Office 365 url 및 IP 주소](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) 지원 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="031fd-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="031fd-107">다음 시나리오에는 방화벽에서 열어야 하는 특정 Url 및 포트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="031fd-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="031fd-108">인증서</span><span class="sxs-lookup"><span data-stu-id="031fd-108">Authentication</span></span>

-   <span data-ttu-id="031fd-109">Microsoft 팀 클라이언트 연결</span><span class="sxs-lookup"><span data-stu-id="031fd-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="031fd-110">협동</span><span class="sxs-lookup"><span data-stu-id="031fd-110">Collaboration</span></span>

-   <span data-ttu-id="031fd-111">미디어</span><span class="sxs-lookup"><span data-stu-id="031fd-111">Media</span></span>

-   <span data-ttu-id="031fd-112">공유 서비스</span><span class="sxs-lookup"><span data-stu-id="031fd-112">Shared Services</span></span>

-   <span data-ttu-id="031fd-113">타사 통합</span><span class="sxs-lookup"><span data-stu-id="031fd-113">Third Party Integration</span></span>

-   <span data-ttu-id="031fd-114">비즈니스용 Skype 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="031fd-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="031fd-115">비즈니스용 Skype 클라이언트 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="031fd-115">Skype for Business Client Interoperability</span></span>
