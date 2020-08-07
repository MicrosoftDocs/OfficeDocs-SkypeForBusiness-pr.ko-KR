---
title: Microsoft 365 및 Office 365 Url 및 IP 주소 범위
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Microsoft 365 또는 Office 365 Url 및 IP 주소 범위를 적절히 구성 하 고 Microsoft 팀 서비스와 연결 하는 데 가능한 한 전달 프록시를 우회 하는 방법에 대해 알아봅니다.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.network.ports
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 94fd32cb4f68d636a6ff49ecf3b9c19689542142
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46582125"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="81f89-103">Microsoft 365 및 Office 365 Url 및 IP 주소 범위</span><span class="sxs-lookup"><span data-stu-id="81f89-103">Microsoft 365 and Office 365 URLs and IP address ranges</span></span>
=======================================================

<span data-ttu-id="81f89-104">[Microsoft 365 및 Office 365 url 및 ip 주소 범위로](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) 이동 하 여 팀에 맞게 올바르게 구성 해야 하는 URL, IP 주소, 포트 및 프로토콜에 대 한 상세 및 최신 목록을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f89-104">Go to [Microsoft 365 and Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="81f89-105">Microsoft는 계속해서 Microsoft 365 및 Office 365 서비스를 개선하고 새 기능을 추가하고 있으며 이는 필수 포트, URL, IP 주소가 시간이 지나면서 변경됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="81f89-105">Microsoft is continuously improving the Microsoft 365 and Office 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="81f89-106">이 정보를 업데이트 하거나 변경할 때 알림을 받으려면 [RSS를 통해 구독](https://go.microsoft.com/fwlink/p/?linkid=236301) 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="81f89-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="81f89-107">팀 통화 및 모임 환경은 Skype 및 비즈니스용 Skype에서 함께 사용 되는 차세대 클라우드 기반 인프라에 기반을 둔 것입니다.</span><span class="sxs-lookup"><span data-stu-id="81f89-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="81f89-108">이러한 기술 투자에는 미디어 처리 및 신호, SILK 및 Opus audio 코덱, 네트워크 탄력성, 원격 분석, 품질 진단 등을 위한 Azure 기반 클라우드 서비스가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81f89-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="81f89-109">따라서 Skype와 비즈니스용 Skype 모두에 연결 될 수 있는 Url과 Ip가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f89-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="81f89-110">모든 Microsoft 365 및 Office 365 작업 부하의 경우, 가능한 경우 팀 서비스에 대 한 연결 방법이 전방 프록시를 우회 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="81f89-110">For all Microsoft 365 and Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="81f89-111">프록시 서버가 클라이언트와 Office 365 데이터 센터 사이에 있으면 UDP 대신 TCP를 통해 미디어를 강제로 사용할 수 있으므로 미디어 품질에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81f89-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="81f89-112">[Microsoft 365 및 Office 365 끝점 관리](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)에서 트래픽 바이패스를 구성 하는 데 사용할 수 있는 샘플 프록시 PAC 파일을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f89-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Microsoft 365 and Office 365 endpoints](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).</span></span>

<span data-ttu-id="81f89-113">네트워킹 및 보안 정책에 따라 프록시 서버를 통해 Microsoft 365 또는 Office 365 트래픽이 진행 되어야 하는 경우 팀을 프로덕션에 배포 하기 전에 위의 요구 사항이 이미 충족 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="81f89-113">If your networking and security policies require Microsoft 365 or Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production.</span></span> <span data-ttu-id="81f89-114">자세한 내용은 [팀에 대 한 프록시 서버 또는 비즈니스용 Skype Online](proxy-servers-for-skype-for-business-online.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="81f89-114">For more information, read [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md).</span></span>
