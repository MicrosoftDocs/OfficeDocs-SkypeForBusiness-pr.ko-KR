---
title: 비즈니스용 Skype 서버에서 VIS 서버 역할 배포
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
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: '요약: 비즈니스용 Skype 서버에서 VIS(Video Interop 서버) 역할을 배포합니다.'
ms.openlocfilehash: 773e2ddf790aa1b6c36ff6926d8bc4d16ea613f5
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801968"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a><span data-ttu-id="bb0c3-103">비즈니스용 Skype 서버에서 VIS 서버 역할 배포</span><span class="sxs-lookup"><span data-stu-id="bb0c3-103">Deploy the VIS server role in Skype for Business Server</span></span>
 
<span data-ttu-id="bb0c3-104">**요약:** 비즈니스용 Skype 서버에서 VIS(Video Interop 서버) 역할을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="bb0c3-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
<span data-ttu-id="bb0c3-105">토폴로지 작성기에서 방금 만든 서버에서 VIS 서비스를 설정하려면 비즈니스용 Skype 서버 배포 마법사를 시작하고 비즈니스용 **Skype** 서버 시스템 설치 또는 업데이트를 누르고 마법사에서 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="bb0c3-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="bb0c3-106">로컬 **구성 저장소 설치를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb0c3-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="bb0c3-107">설치 **또는 비즈니스용 Skype 서버 구성 요소를 제거합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb0c3-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="bb0c3-108">인증서 요청, 설치 또는 **할당을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb0c3-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="bb0c3-109">서비스 **시작을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="bb0c3-109">Select **Start services**.</span></span>
    
<span data-ttu-id="bb0c3-110">이제 이 서비스의 소프트웨어가 설치되고 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb0c3-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="bb0c3-111">서비스 mmc 도구를 열어 비즈니스용 **Skype 서버 Video Interop 서버** 서비스가 다른 비즈니스용 Skype 서버 서비스와 함께 실행 중인지 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb0c3-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="bb0c3-112">그런 다음 VIS 서버 또는 풀을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb0c3-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="bb0c3-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bb0c3-113">See also</span></span>

[<span data-ttu-id="bb0c3-114">비즈니스용 Skype 서버에서 비디오 Interop 서버 구성</span><span class="sxs-lookup"><span data-stu-id="bb0c3-114">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
