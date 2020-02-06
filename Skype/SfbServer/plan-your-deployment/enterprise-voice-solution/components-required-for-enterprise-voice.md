---
title: 비즈니스용 Skype 서버에서 엔터프라이즈 음성에 필요한 구성 요소
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: 비즈니스용 Skype 서버의 엔터프라이즈 음성 구성 요소 요약
ms.openlocfilehash: a2e32e2301a404afd06038d438fbb62a13235d65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803108"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="709f7-103">비즈니스용 Skype 서버에서 엔터프라이즈 음성에 필요한 구성 요소</span><span class="sxs-lookup"><span data-stu-id="709f7-103">Components required for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="709f7-104">비즈니스용 Skype 서버의 엔터프라이즈 음성 구성 요소 요약</span><span class="sxs-lookup"><span data-stu-id="709f7-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="709f7-105">엔터프라이즈 음성을 배포 하려면 토폴로지에 다음 구성 요소가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="709f7-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="709f7-106">신호를 변환 하는 하나 이상의 중재 서버, 일부 구성에서 내부 비즈니스용 Skype 서버 간 미디어, 엔터프라이즈 음성 인프라 및 PSTN (공개 교환 전화 네트워크) 게이트웨이 또는 세션 초기화 프로토콜 (SIP) 트렁크.</span><span class="sxs-lookup"><span data-stu-id="709f7-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="709f7-107">중재 서버는 엔터프라이즈 음성 배포에서 가장 중요 한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="709f7-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="709f7-108">자세한 내용은 [비즈니스용 Skype 서버에서 중재 서버 구성 요소](mediation-server.md)조정을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="709f7-108">For more information, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>
    
    <span data-ttu-id="709f7-109">중재 서버는 프런트 엔드 서버와 collocated 또는 독립 실행형 서버로 설치 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="709f7-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="709f7-110">PSTN 연결 구성 요소-SIP trunks 또는 PSTN 게이트웨이를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="709f7-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="709f7-111">자세한 내용은 [비즈니스용 Skype 서버의 PSTN 연결 구성 요소](pstn-connectivity.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="709f7-111">For more information, see [PSTN connectivity components in Skype for Business Server](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="709f7-112">Edge 서버-사용자가 조직의 방화벽 외부에 있을 때 Enterprise Voice 기능을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="709f7-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="709f7-113">액세스에 지 서비스는 조직의 방화벽 외부에 있는 비즈니스용 Skype 사용자의 통화에 대 한 SIP 신호를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="709f7-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="709f7-114">A/V Edge 서비스는 NAT와 방화벽의 미디어 이동을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="709f7-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="709f7-115">회사 방화벽 외부에서 통합 커뮤니케이션 (UC) 클라이언트를 사용 하는 발신자는 개인 및 전화 회의 둘 다에 대 한 A/V에 지 서비스에 의존 합니다.</span><span class="sxs-lookup"><span data-stu-id="709f7-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="709f7-116">A/V 인증 서비스는 A/v에 대 한 인증 서비스를 제공 하는 collocated와 함께 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="709f7-116">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service.</span></span> <span data-ttu-id="709f7-117">A/V Edge 서비스에 연결 하려고 하는 외부 사용자는 해당 통화를 통과할 수 있도록 A/V 인증 서비스에서 제공 하는 인증 토큰이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="709f7-117">Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="709f7-118">또한 일부 엔터프라이즈 음성 구성 요소는 프런트 엔드 서버에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="709f7-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="709f7-119">이러한 구성 요소에 대 한 자세한 내용은 [비즈니스용 Skype 서버에 대 한 프런트 엔드 서버 VoIP 구성 요소](front-end-server-voip.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="709f7-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)</span></span>
    

