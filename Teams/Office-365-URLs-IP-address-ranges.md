---
title: Microsoft 365 및 Office 365 URL 및 IP 주소 범위
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: URL 및 IP 주소 범위를 Microsoft 365 또는 Office 365 올바르게 구성하고 서비스와의 연결에 대해 가능한 경우 전달 프록시를 Microsoft Teams 방법을 알아보십시오.
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
ms.openlocfilehash: 9a29984b0b389bacb50a9aa6512a9ccc8bfe07de
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094520"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="f1751-103">Microsoft 365 및 Office 365 URL 및 IP 주소 범위</span><span class="sxs-lookup"><span data-stu-id="f1751-103">Microsoft 365 and Office 365 URLs and IP address ranges</span></span>
=======================================================

<span data-ttu-id="f1751-104">[URL Microsoft 365](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) Office 365 올바르게 구성해야 하는 URL, IP 주소, 포트 및 프로토콜에 대한 자세한 최신 목록을 확인하려면 URL 및 IP 주소 범위로 Teams.</span><span class="sxs-lookup"><span data-stu-id="f1751-104">Go to [Microsoft 365 and Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="f1751-105">Microsoft는 계속해서 Microsoft 365 및 Office 365 서비스를 개선하고 새 기능을 추가하고 있으며 이는 필수 포트, URL, IP 주소가 시간이 지나면서 변경됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="f1751-105">Microsoft is continuously improving the Microsoft 365 and Office 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="f1751-106">이 정보가 업데이트되거나 변경될 때 알림을 받기 위해 [RSS를](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) 통해 구독하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f1751-106">We recommend that you [subscribe via RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="f1751-107">Teams 호출 및 모임 환경은 차세대 클라우드 기반 인프라를 기반으로 Skype 비즈니스용 Skype.</span><span class="sxs-lookup"><span data-stu-id="f1751-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="f1751-108">이러한 기술 투자에는 미디어 처리 및 신호 처리를 위한 Azure 기반 클라우드 서비스, H.264 비디오 코덱, SILK 및 Opus 오디오 코덱, 네트워크 탄력성, 원격 분석 및 품질 진단이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1751-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="f1751-109">따라서 URL 및 IPS가 Skype 및 비즈니스용 SKYPE.</span><span class="sxs-lookup"><span data-stu-id="f1751-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="f1751-110">모든 Microsoft 365 및 Office 365 경우 서비스를 Teams 권장되는 연결 방법은 가능한 경우 전달 프록시를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="f1751-110">For all Microsoft 365 and Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="f1751-111">프록시 서버가 클라이언트와 데이터 Office 365 사이에 있는 경우 미디어가 UDP 대신 TCP를 강제로 하여 미디어 품질에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f1751-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="f1751-112">데이터 관리 및 엔드포인트 관리에서 트래픽 우회를 구성하는 데 사용할 수 있는 샘플 프록시 PAC [Microsoft 365 Office 365 다운로드합니다.](/office365/enterprise/managing-office-365-endpoints)</span><span class="sxs-lookup"><span data-stu-id="f1751-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Microsoft 365 and Office 365 endpoints](/office365/enterprise/managing-office-365-endpoints).</span></span>

<span data-ttu-id="f1751-113">네트워킹 및 보안 정책에서 프록시 서버를 통해 Microsoft 365 Office 365 트래픽이 필요하면 프로덕션에 배포하기 전에 위의 요구 사항이 Teams 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f1751-113">If your networking and security policies require Microsoft 365 or Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production.</span></span> <span data-ttu-id="f1751-114">자세한 내용은 온라인 또는 Teams 프록시 비즈니스용 Skype [를 참조하십시오.](proxy-servers-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="f1751-114">For more information, read [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md).</span></span>