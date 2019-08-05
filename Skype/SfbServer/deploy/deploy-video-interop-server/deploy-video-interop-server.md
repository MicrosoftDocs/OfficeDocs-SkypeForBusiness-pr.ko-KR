---
title: 비즈니스용 Skype 서버에서 비디오 Interop 서버 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: '요약: 비즈니스용 Skype 서버에서 VIS 서버 역할을 배포 합니다.'
ms.openlocfilehash: c6ee0e52a4ac84622fee9ba281a64d1094c38c4c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36197346"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="779ea-103">비즈니스용 Skype 서버에서 비디오 Interop 서버 배포</span><span class="sxs-lookup"><span data-stu-id="779ea-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="779ea-104">**요약:** 비즈니스용 Skype 서버에서 VIS 서버 역할을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="779ea-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="779ea-105">비즈니스용 Skype 서버는 이제 cisco C60 또는 Cisco MX300와 같은 Cisco teleconferencing 시스템 (VTCs)과 직접 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="779ea-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="779ea-106">이를 위해서는 비디오 Interop 서버 (VIS) 라는 새 서버 역할을 도입 하 고 VIS와 상호 운용 하는 장비의 올바른 구성을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="779ea-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="779ea-107">CUCM (Cisco 통합 커뮤니케이션 관리자)와 같은 기존 Cisco 인프라를 사용 하 여 VTC를 등록 한 경우 비디오 SIP 트렁크가 CUCM와 VIS 풀 사이에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="779ea-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="779ea-108">이 섹션의</span><span class="sxs-lookup"><span data-stu-id="779ea-108">In this section</span></span>

<span data-ttu-id="779ea-109">VIS server 또는 풀 및 VTC 시스템 간 상호 운용성을 구성 하려면 다음 다섯 가지 절차를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="779ea-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="779ea-110">비즈니스용 Skype 서버에서 VIS 풀 만들기</span><span class="sxs-lookup"><span data-stu-id="779ea-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="779ea-111">비즈니스용 Skype 서버에서 VIS 서버 역할 배포</span><span class="sxs-lookup"><span data-stu-id="779ea-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="779ea-112">비즈니스용 Skype 서버에서 비디오 Interop 서버 구성</span><span class="sxs-lookup"><span data-stu-id="779ea-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="779ea-113">비즈니스용 Skype 서버와 상호 운용할 CUCM 구성</span><span class="sxs-lookup"><span data-stu-id="779ea-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="779ea-114">비즈니스용 Skype 서버와 상호 운용을 위한 VTC 구성</span><span class="sxs-lookup"><span data-stu-id="779ea-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="779ea-115">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="779ea-115">Related sections</span></span>

[<span data-ttu-id="779ea-116">비즈니스용 Skype 서버의 비디오 Interop 서버 계획</span><span class="sxs-lookup"><span data-stu-id="779ea-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

