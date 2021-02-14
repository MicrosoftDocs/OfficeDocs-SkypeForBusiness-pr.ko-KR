---
title: 비즈니스용 Skype 서버에서 비디오 Interop 서버 배포
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bb7d2abd-d033-4d7d-b588-6d9228c3eccf
description: '요약: 비즈니스용 Skype 서버에서 VIS 서버 역할을 배포합니다.'
ms.openlocfilehash: 7b3ee96b1ff2e6c633efa9e1cc98aa14bb5babc3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801958"
---
# <a name="deploy-video-interop-server-in-skype-for-business-server"></a><span data-ttu-id="f6baa-103">비즈니스용 Skype 서버에서 비디오 Interop 서버 배포</span><span class="sxs-lookup"><span data-stu-id="f6baa-103">Deploy Video Interop Server in Skype for Business Server</span></span>
 
<span data-ttu-id="f6baa-104">**요약:** 비즈니스용 Skype 서버에서 VIS 서버 역할을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="f6baa-104">**Summary:** Deploy the VIS server role in Skype for Business Server.</span></span>
  
<span data-ttu-id="f6baa-105">비즈니스용 Skype 서버는 이제 Cisco C60 또는 Cisco MX300과 같은 Cisco 원격 회의 시스템(VTC)과 직접 통합될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6baa-105">Skype for Business Server can now integrate directly with Cisco teleconferencing systems (VTCs) such as the Cisco C60 or Cisco MX300.</span></span> <span data-ttu-id="f6baa-106">이를 위해서는 VIS(Video Interop Server)라는 새 서버 역할이 도입되어 VIS와 상호 작업할 장비와 VIS를 모두 올바르게 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6baa-106">This requires the introduction of a new server role called the Video Interop Server (VIS), and correct configuration of both the VIS and the equipment it will interoperate with.</span></span> <span data-ttu-id="f6baa-107">VTC는 Cisco CUCM(통합 통신 관리자)과 같은 기존 Cisco 인프라에 등록되고 CUCM과 VIS 풀 간에 비디오 SIP 트렁크가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6baa-107">A VTC registers with existing Cisco infrastructure such as Cisco Unified Communication Manager (CUCM), and a video SIP trunk is used between CUCM and the VIS pool.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="f6baa-108">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="f6baa-108">In this section</span></span>

<span data-ttu-id="f6baa-109">VIS 서버 또는 풀과 VTC 시스템 간의 상호 운영성을 구성하려면 다음 다섯 가지 절차를 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6baa-109">Configuring interoperability between a VIS server or pool and VTC systems requires performing the following five procedures:</span></span> 
  
- [<span data-ttu-id="f6baa-110">비즈니스용 Skype 서버에서 VIS 풀 만들기</span><span class="sxs-lookup"><span data-stu-id="f6baa-110">Create a VIS pool in Skype for Business Server</span></span>](create-a-vis-pool.md)
    
- [<span data-ttu-id="f6baa-111">비즈니스용 Skype 서버에서 VIS 서버 역할 배포</span><span class="sxs-lookup"><span data-stu-id="f6baa-111">Deploy the VIS server role in Skype for Business Server</span></span>](deploy-the-vis-server-role.md)
    
- [<span data-ttu-id="f6baa-112">비즈니스용 Skype 서버에서 비디오 Interop 서버 구성</span><span class="sxs-lookup"><span data-stu-id="f6baa-112">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
    
- [<span data-ttu-id="f6baa-113">비즈니스용 Skype 서버와의 상호 연결에 대해 CUCM 구성</span><span class="sxs-lookup"><span data-stu-id="f6baa-113">Configure CUCM for Interoperation with Skype for Business Server</span></span>](configure-cucm-for-interoperation.md)
    
- [<span data-ttu-id="f6baa-114">비즈니스용 Skype 서버와의 상호 연계를 위한 VTC 구성</span><span class="sxs-lookup"><span data-stu-id="f6baa-114">Configure a VTC for Interoperation with Skype for Business Server</span></span>](configure-a-vtc-for-interoperation.md)
    
## <a name="related-sections"></a><span data-ttu-id="f6baa-115">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="f6baa-115">Related sections</span></span>

[<span data-ttu-id="f6baa-116">비즈니스용 Skype 서버의 비디오 Interop 서버 계획</span><span class="sxs-lookup"><span data-stu-id="f6baa-116">Plan for Video Interop Server in Skype for Business Server</span></span>](../../plan-your-deployment/video-interop-server.md)
  

