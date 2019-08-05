---
title: Microsoft 팀 클라이언트의 연결 문제 해결
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: 방화벽 또는 프록시 연결로 인해 발생 하는 Microsoft 팀 클라이언트의 연결 문제를 해결 하 고이를 해결 하는 방법을 알아봅니다.
appliesto:
- Microsoft Teams
ms.openlocfilehash: d208671415e44ca5ec83313d0d8af666534f2b20
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "36180486"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="3363a-103">Microsoft 팀 클라이언트의 연결 문제 해결</span><span class="sxs-lookup"><span data-stu-id="3363a-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="3363a-104">Microsoft 팀 클라이언트에서 발견 된 대부분의 문제는 방화벽 또는 프록시 연결을 통해 다시 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3363a-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="3363a-105">방화벽 또는 프록시에서 필요한 Url, IP 주소 및 포트가 열려 있는지 확인 하면 불필요 한 문제 해결이 최소화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3363a-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="3363a-106">Microsoft 팀에 필요한 Url 및 Ip에 대 한 특정 정보는 [Office 365 url 및 IP 주소](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) 지원 문서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3363a-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="3363a-107">다음 시나리오에는 방화벽에서 열어야 하는 특정 Url 및 포트가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3363a-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="3363a-108">인증서</span><span class="sxs-lookup"><span data-stu-id="3363a-108">Authentication</span></span>

-   <span data-ttu-id="3363a-109">Microsoft 팀 클라이언트 연결</span><span class="sxs-lookup"><span data-stu-id="3363a-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="3363a-110">협동</span><span class="sxs-lookup"><span data-stu-id="3363a-110">Collaboration</span></span>

-   <span data-ttu-id="3363a-111">미디어</span><span class="sxs-lookup"><span data-stu-id="3363a-111">Media</span></span>

-   <span data-ttu-id="3363a-112">공유 서비스</span><span class="sxs-lookup"><span data-stu-id="3363a-112">Shared Services</span></span>

-   <span data-ttu-id="3363a-113">타사 통합</span><span class="sxs-lookup"><span data-stu-id="3363a-113">Third Party Integration</span></span>

-   <span data-ttu-id="3363a-114">비즈니스용 Skype 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="3363a-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="3363a-115">비즈니스용 Skype 클라이언트 상호 운용성</span><span class="sxs-lookup"><span data-stu-id="3363a-115">Skype for Business Client Interoperability</span></span>
