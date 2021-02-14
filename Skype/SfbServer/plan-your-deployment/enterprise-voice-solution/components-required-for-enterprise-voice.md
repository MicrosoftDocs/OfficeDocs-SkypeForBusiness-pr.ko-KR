---
title: 비즈니스용 Skype Enterprise Voice 구성 요소
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
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: 비즈니스용 Skype Enterprise Voice 구성 요소의 요약입니다.
ms.openlocfilehash: 1a7f13cc171af44ecbd0f48706ec12d882e50b33
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825828"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="4bb17-103">비즈니스용 Skype Enterprise Voice 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4bb17-103">Components required for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="4bb17-104">비즈니스용 Skype Enterprise Voice 구성 요소의 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="4bb17-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="4bb17-105">토폴로지에서 Enterprise Voice 구성 요소를 배포하려면 다음 구성 요소가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb17-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="4bb17-106">신호 및 일부 구성에서 내부 비즈니스용 Skype 서버, Enterprise Voice 인프라 및 PSTN(Public Switched Telephone Network) 게이트웨이 또는 SIP(Session Initiation Protocol) 트렁크 간의 미디어를 변환하는 하나 이상의 중재 서버.</span><span class="sxs-lookup"><span data-stu-id="4bb17-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="4bb17-107">중재 서버는 배포에서 가장 Enterprise Voice 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4bb17-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="4bb17-108">자세한 내용은 비즈니스용 Skype 서버의 중재 서버 구성 요소를 [참조하세요.](mediation-server.md)</span><span class="sxs-lookup"><span data-stu-id="4bb17-108">For more information, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>
    
    <span data-ttu-id="4bb17-109">중재 서버는 프런트 엔드 서버와 함께 함께 설치하거나 독립 실행형 서버로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bb17-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="4bb17-110">SIP 트렁크 또는 PSTN 게이트웨이를 포함할 수 있는 PSTN 연결 구성 요소</span><span class="sxs-lookup"><span data-stu-id="4bb17-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="4bb17-111">자세한 내용은 비즈니스용 [Skype 서버의 PSTN 연결 구성 요소를 참조하세요.](pstn-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="4bb17-111">For more information, see [PSTN connectivity components in Skype for Business Server](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="4bb17-112">에지 서버 - 사용자가 조직의 방화벽 외부에 있는 Enterprise Voice 기능을 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb17-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="4bb17-113">액세스 에지 서비스는 조직의 방화벽 외부에 있는 비즈니스용 Skype 사용자의 통화에 대한 SIP 신호를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb17-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="4bb17-114">A/V 에지 서비스를 사용하면 미디어가 NAT 및 방화벽을 트래버스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bb17-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="4bb17-115">회사 방화벽 외부에서 UC(통합 통신) 클라이언트를 사용하는 발신자는 개인적인 통화와 전화 회의 모두에 A/V 에지 서비스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4bb17-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="4bb17-p104">A/V 에지 서비스와 함께 A/V 인증 서비스가 배치되어 인증 서비스를 제공합니다. A/V 에지 서비스에 연결하려는 외부 사용자는 A/V 인증 서비스에서 제공한 인증 토큰이 있어야 통화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4bb17-p104">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="4bb17-118">또한 일부 Enterprise Voice 구성 요소는 프런트 엔드 서버에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="4bb17-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="4bb17-119">이러한 구성 요소에 대한 자세한 내용은 비즈니스용 Skype 서버의 프런트 엔드 서버 VoIP 구성 [요소를 참조하세요.](front-end-server-voip.md)</span><span class="sxs-lookup"><span data-stu-id="4bb17-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)</span></span>
    

