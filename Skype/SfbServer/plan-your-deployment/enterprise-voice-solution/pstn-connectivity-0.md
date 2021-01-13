---
title: 비즈니스용 Skype 서버에서 PSTN 연결 계획
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
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: 비즈니스용 Skype 서버에서 Enterprise Voice PSTN 연결을 계획합니다.
ms.openlocfilehash: 492f4e2cc71644cb1e9957f407a549cce5dbc31d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813568"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="cbbfe-103">비즈니스용 Skype 서버에서 PSTN 연결 계획</span><span class="sxs-lookup"><span data-stu-id="cbbfe-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="cbbfe-104">비즈니스용 Skype 서버에서 Enterprise Voice PSTN 연결을 계획합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbfe-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="cbbfe-105">엔터프라이즈급 VoIP 솔루션은 QoS(서비스 품질)를 떨어트려도 PSTN(공용 전화망)과의 통화를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbfe-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="cbbfe-106">통화를 걸고 받는 사용자는 사용자의 관점에서 볼 때, Enterprise Voice 인프라와 PSTN 간의 통화는 다른 전화 통화처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbfe-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="cbbfe-107">비즈니스용 Skype 서버는 다음 옵션을 사용하여 안정적이고 확장 가능한 PSTN 연결을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbfe-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="cbbfe-108">ITSP(인터넷 전화 통신 서비스 공급자)에 대한 **SIP 트렁크**</span><span class="sxs-lookup"><span data-stu-id="cbbfe-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="cbbfe-109">PSTN 게이트웨이에 대한 **직접 SIP 연결**</span><span class="sxs-lookup"><span data-stu-id="cbbfe-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="cbbfe-110">PBX에 대한 **직접 SIP 연결**</span><span class="sxs-lookup"><span data-stu-id="cbbfe-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="cbbfe-111">크기, 포함 지역 및 기존 음성 인프라에 따라 엔터프라이즈는 여러 위치에서 위의 옵션 중 하나 또는 두 개를 사용할 수도 있고 세 옵션을 모두 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbfe-111">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span> <span data-ttu-id="cbbfe-112">이러한 옵션에 대한 자세한 내용은 다음 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="cbbfe-112">For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="cbbfe-113">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="cbbfe-113">In this section</span></span>

- [<span data-ttu-id="cbbfe-114">비즈니스용 Skype 서버의 SIP 트렁크</span><span class="sxs-lookup"><span data-stu-id="cbbfe-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="cbbfe-115">비즈니스용 Skype 서버의 직접 SIP 연결</span><span class="sxs-lookup"><span data-stu-id="cbbfe-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="cbbfe-116">비즈니스용 Skype 서버의 M:N 트렁크</span><span class="sxs-lookup"><span data-stu-id="cbbfe-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="cbbfe-117">비즈니스용 Skype 서버의 변환 규칙</span><span class="sxs-lookup"><span data-stu-id="cbbfe-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="cbbfe-118">비즈니스용 Skype 서버에서 아웃바운드 음성 라우팅 계획</span><span class="sxs-lookup"><span data-stu-id="cbbfe-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

