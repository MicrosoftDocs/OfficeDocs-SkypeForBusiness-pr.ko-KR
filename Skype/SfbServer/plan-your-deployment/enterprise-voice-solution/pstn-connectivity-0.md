---
title: 비즈니스용 Skype 서버에서 PSTN 연결 계획
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: 비즈니스용 Skype 서버에서 엔터프라이즈 음성으로 PSTN 연결을 계획 합니다.
ms.openlocfilehash: f0b6aa6b43562fea91885b0d55d75fd234ab97de
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187578"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="236c9-103">비즈니스용 Skype 서버에서 PSTN 연결 계획</span><span class="sxs-lookup"><span data-stu-id="236c9-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="236c9-104">비즈니스용 Skype 서버에서 엔터프라이즈 음성으로 PSTN 연결을 계획 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c9-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="236c9-105">엔터프라이즈급 VoIP 솔루션은 서비스 품질 (QoS)에 동의 하지 않고 PSTN (공공 교환 전화 네트워크)에 대 한 통화를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c9-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="236c9-106">전화를 걸고 받는 사용자는 기본 기술을 인식 하지 못합니다. 사용자 관점에서 보면 엔터프라이즈 음성 인프라와 PSTN 간의 통화는 다른 전화 통화 처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c9-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="236c9-107">비즈니스용 Skype Server는 다음 옵션을 사용 하 여 안정적이 고 확장 가능한 PSTN 연결을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="236c9-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="236c9-108">**SIP Trunks** 인터넷 통신 서비스 공급자 (itsp)</span><span class="sxs-lookup"><span data-stu-id="236c9-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="236c9-109">PSTN 게이트웨이에 대 한 **직접 SIP 연결**</span><span class="sxs-lookup"><span data-stu-id="236c9-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="236c9-110">PBX로 **직접 SIP 연결**</span><span class="sxs-lookup"><span data-stu-id="236c9-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="236c9-111">해당 크기, 지역 및 기존 음성 인프라에 따라 엔터프라이즈는 다양 한 위치에서 하나, 두 가지 또는 세 가지 옵션을 모두 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="236c9-111">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span> <span data-ttu-id="236c9-112">이러한 옵션에 대 한 자세한 내용은 다음 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="236c9-112">For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="236c9-113">이 섹션의</span><span class="sxs-lookup"><span data-stu-id="236c9-113">In this section</span></span>

- [<span data-ttu-id="236c9-114">비즈니스용 Skype 서버의 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="236c9-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="236c9-115">비즈니스용 Skype 서버에서 직접 SIP 연결</span><span class="sxs-lookup"><span data-stu-id="236c9-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="236c9-116">M:N 비즈니스용 Skype 서버에서의 트렁크</span><span class="sxs-lookup"><span data-stu-id="236c9-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="236c9-117">비즈니스용 Skype 서버의 번역 규칙</span><span class="sxs-lookup"><span data-stu-id="236c9-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="236c9-118">비즈니스용 Skype 서버의 아웃 바운드 음성 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="236c9-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

