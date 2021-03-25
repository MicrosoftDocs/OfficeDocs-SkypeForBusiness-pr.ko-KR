---
title: 비즈니스용 Skype 서버에서 E9-1-1 배포 범위 정의
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2c572dfd-e901-471d-b5a0-18bc8d1d5328
description: 비즈니스용 Skype 서버 2013에서 E9-1-1 배포를 계획하는 데 Enterprise Voice.
ms.openlocfilehash: 39397064fe525a2b1324b8ef0a0f0bb1df287653
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114574"
---
# <a name="define-the-scope-of-the-e9-1-1-deployment-in-skype-for-business-server"></a><span data-ttu-id="012b9-103">비즈니스용 Skype 서버에서 E9-1-1 배포 범위 정의</span><span class="sxs-lookup"><span data-stu-id="012b9-103">Define the scope of the E9-1-1 deployment in Skype for Business Server</span></span>

<span data-ttu-id="012b9-104">비즈니스용 Skype 서버 2013에서 E9-1-1 배포를 계획하는 데 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="012b9-104">Decisions necessary for planning an E9-1-1 deployment in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="012b9-105">E9-1-1에 대해 비즈니스용 Skype를 구성하기 전에 E9-1-1 배포를 계획해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="012b9-105">Before you configure Skype for Business for E9-1-1, you need to plan your E9-1-1 deployment.</span></span> <span data-ttu-id="012b9-106">이때 고려할 몇 가지 사항은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="012b9-106">Some of the questions to consider include:</span></span>

 <span data-ttu-id="012b9-107">**E9-1-1과 관련하여 조직의 정책 및 법적 의무는 무엇입니까?**</span><span class="sxs-lookup"><span data-stu-id="012b9-107">**What are your organization's policy and legal obligations with regard to E9-1-1?**</span></span>

 <span data-ttu-id="012b9-108">PBX에 대한 E9-1-1 법적 요구 사항(E9-1-1 용어로는 MLTS(Multi-line Telephone Systems)라고 함)은 지역마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="012b9-108">E9-1-1 legal requirements for PBXs (called Multi-line Telephone Systems, or MLTS, in E9-1-1 parlance) differ from state to state.</span></span> <span data-ttu-id="012b9-109">법률 팀에 문의하여 관련 지리에서 비즈니스용 Skype 배포에 적용될 수 있는 의무를 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="012b9-109">You should consult with your legal team to understand the obligations that may apply to your deployment of Skype for Business in your relevant geographies.</span></span>

 <span data-ttu-id="012b9-110">**엔터프라이즈 내에서 E9-1-1을 사용하도록 설정할 영역**</span><span class="sxs-lookup"><span data-stu-id="012b9-110">**What areas within your enterprise need to be enabled for E9-1-1?**</span></span>

 <span data-ttu-id="012b9-p103">선택한 위치에서 또는 전체 엔터프라이즈에서 E9-1-1을 사용하도록 설정할 수 있습니다. 예를 들어 각 지역의 지점에 대해 서로 다른 E9-1-1 요구 사항을 지정할 수도 있고 다른 국가의 사이트는 제외할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="012b9-p103">You can enable E9-1-1 for the entire enterprise or for selected locations. For example, you may have varying E9-1-1 requirements for offices in different states, or you may want to exclude sites outside the U.S.</span></span>

 <span data-ttu-id="012b9-113">**분기 사이트에 E9-1-1을 배포할 방법**</span><span class="sxs-lookup"><span data-stu-id="012b9-113">**How will you deploy E9-1-1 to branch sites?**</span></span>

 <span data-ttu-id="012b9-114">분기 사이트에 E9-1-1을 배포할 때 이해해야 하는 중요한 개념은 음성 탄성입니다.</span><span class="sxs-lookup"><span data-stu-id="012b9-114">Voice resiliency is an important concept to understand when deploying E9-1-1 at a branch site.</span></span> <span data-ttu-id="012b9-115">중앙 집중식 E-9-1-1 SIP 트렁크가 발생하고 WAN이 정전된 경우 로그인하는 클라이언트가 위치 정보 서비스에서 위치를 얻거나 응급 서비스 서비스 공급자에 연결하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="012b9-115">If you have centralized E-9-1-1 SIP trunks and a WAN outage occurs, clients signing in may not be able to obtain a location from Location Information service or to connect to the emergency services service provider.</span></span> <span data-ttu-id="012b9-116">비즈니스용 Skype는 지점에서 음성 탄력성 처리를 위한 몇 가지 전략을 제공합니다. 예를 들어, 탄력적인 데이터 네트워크가 있는 경우, 각 분기에 SIP 트렁크를 배포하거나, 정전 중에 로컬 게이트웨이로 긴급 통화를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="012b9-116">Skype for Business provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing emergency calls out to the local gateway during outages.</span></span> <span data-ttu-id="012b9-117">자세한 내용은 [Planning for Branch-Site Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-branch-site-voice-resiliency)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="012b9-117">For details, see [Planning for Branch-Site Voice Resiliency](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-branch-site-voice-resiliency).</span></span>

 <span data-ttu-id="012b9-118">**네트워크 외부에서 작업하는 사용자에 대해 E9-1-1을 사용하도록 설정할지 여부**</span><span class="sxs-lookup"><span data-stu-id="012b9-118">**Will you enable E9-1-1 for users working outside the network?**</span></span>

 <span data-ttu-id="012b9-119">자동 위치 취득은 조직의 네트워크 내부에 있는 클라이언트에서만 사용할 수 있으므로 조직에서는 오프-프레미스 동안 비즈니스용 Skype 클라이언트에서 걸은 E9-1-1 통화를 지원할지 여부를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="012b9-119">Automatic location acquisition is available only for clients located inside the organization's network, so your organization needs to decide whether it will support E9-1-1 calls made from Skype for Business clients while off-premises.</span></span> <span data-ttu-id="012b9-120">예를 들어 사용자가 재택 근무 중이거나 고객 사이트에서 작업 중일 때 긴급 통화를 할 수 있도록 설정할지를 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="012b9-120">For example, will you enable users to place emergency calls if they are working from home or from a customer site?</span></span> <span data-ttu-id="012b9-121">클라이언트가 엔터프라이즈 네트워크 외부에 있는 경우 사용자에게 위치를 선택하라는 메시지를 표시하도록 클라이언트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="012b9-121">If a client is located outside the enterprise network, the client can be configured to prompt the user for a location.</span></span> <span data-ttu-id="012b9-122">그러나 사용자가 제공하는 위치는 MSAG(마스터 주소 가이드)와 비교하여 미리 유효성을 검사할 수 없기 때문에 응급 서비스 서비스 공급자 발송자는 통화를 PSAP(Public Safety Answering Point)로 라우팅하기 전에 구두로 발신자에게 위치의 유효성을 확인받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="012b9-122">However, because these user-provided locations cannot be prevalidated against the Master Street Address Guide (MSAG), the emergency services service provider dispatcher will need to confirm the validity of the location verbally with the caller before routing the call to the Public Safety Answering Point (PSAP).</span></span>

> [!NOTE]
> <span data-ttu-id="012b9-123">VPN을 사용하여 조직의 네트워크에 연결하는 사용자의 비즈니스용 Skype 클라이언트는 내부 IP 주소 정보를 선택할 수 있지만 이러한 주소를 사용하여 사용자의 실제 위치를 식별할 수는 없습니다. VPN 서브넷을 위치 정보 서비스에서 제외해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="012b9-123">Skype for Business clients of users who connect to your organization's network by using VPN can pick up internal IP address information, but because these addresses cannot be used to identify the user's actual location, it is essential that VPN subnets are excluded from the Location Information service.</span></span>

 <span data-ttu-id="012b9-124">**해외 사이트에 대해 긴급 통화 라우팅을 제공할지 여부**</span><span class="sxs-lookup"><span data-stu-id="012b9-124">**Do you want to provide emergency call routing to sites outside the U.S.?**</span></span>

 <span data-ttu-id="012b9-p106">응급 서비스 서비스 공급자가 서비스를 제공하지 않는 회사 지역(예: 다른 국가)에 대해 긴급 통화 라우팅 기능을 제공하려는 경우가 있을 수 있습니다. 이렇게 하려면 새 사이트를 만든 다음, 로컬 PSTN 게이트웨이를 통해 통화를 라우팅하는 PSTN 사용을 참조하는 음성 정책을 사이트에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="012b9-p106">You may want to provide emergency routing to areas of your company not served by an emergency services service provider (for example, international locations). To do this, create a new site, and then assign voice policies to the sites that refer to a PSTN usage that routes the call through the local PSTN gateway.</span></span>