---
title: 비즈니스용 Skype 서버에서 VIS 서버 역할 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6401e67-59fe-4419-a0ab-ffac88e67632
description: '요약: 비즈니스용 Skype 서버에서 VIS (비디오 Interop Server) 역할을 배포 합니다.'
ms.openlocfilehash: 1e200382bc6b6eac00bcf69b49592337f6b5c3b4
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235694"
---
# <a name="deploy-the-vis-server-role-in-skype-for-business-server"></a><span data-ttu-id="6f95c-103">비즈니스용 Skype 서버에서 VIS 서버 역할 배포</span><span class="sxs-lookup"><span data-stu-id="6f95c-103">Deploy the VIS server role in Skype for Business Server</span></span>
 
<span data-ttu-id="6f95c-104">**요약:** 비즈니스용 Skype 서버에서 VIS (비디오 Interop Server) 역할을 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f95c-104">**Summary:** Deploy the Video Interop Server (VIS) role in Skype for Business Server.</span></span>
  
<span data-ttu-id="6f95c-105">토폴로지 작성기에서 방금 만든 서버에서 VIS 서비스를 설정 하려면 비즈니스용 Skype 서버 배포 마법사를 시작 하 고 비즈니스용 **Skype Server System 설치 또는 업데이트** 를 누른 후 마법사에서 다음 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f95c-105">To set up the VIS service on the server just created in Topology Builder, start the Skype for Business Server deployment wizard, press **Install or Update Skype for Business Server System** and follow these steps in the wizard:</span></span>
  
1.  <span data-ttu-id="6f95c-106">**로컬 구성 저장소 설치**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f95c-106">Select **Install Local Configuration Store**.</span></span>
    
2. <span data-ttu-id="6f95c-107">**비즈니스용 Skype 서버 구성 요소 설치 또는 제거를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f95c-107">Select **Setup or Remove Skype for Business Server Components**.</span></span>
    
3. <span data-ttu-id="6f95c-108">**요청, 설치 또는 인증서 할당을**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f95c-108">Select **Request, Install or Assign Certificates**.</span></span>
    
4. <span data-ttu-id="6f95c-109">**서비스 시작**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f95c-109">Select **Start services**.</span></span>
    
<span data-ttu-id="6f95c-110">이 서비스에 대 한 소프트웨어가 설치 되어 실행 중입니다.</span><span class="sxs-lookup"><span data-stu-id="6f95c-110">The software for this service is now installed and running.</span></span> <span data-ttu-id="6f95c-111">서비스 mmc 도구를 열어 비즈니스용 **Skype 서버 영상 Interop 서버** 서비스가 다른 비즈니스용 skype 서버 서비스와 함께 실행 되 고 있는지 확인 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6f95c-111">You may open the Services mmc tool to see if the **Skype for Business Server Video Interop Server** service is running along with other Skype for Business Server services.</span></span> <span data-ttu-id="6f95c-112">다음으로 VIS 서버 또는 풀을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6f95c-112">Next, you must configure the VIS server or pool.</span></span>
## <a name="see-also"></a><span data-ttu-id="6f95c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f95c-113">See also</span></span>

[<span data-ttu-id="6f95c-114">비즈니스용 Skype 서버에서 비디오 Interop 서버 구성</span><span class="sxs-lookup"><span data-stu-id="6f95c-114">Configure the Video Interop Server in Skype for Business Server</span></span>](configure-the-vis.md)
