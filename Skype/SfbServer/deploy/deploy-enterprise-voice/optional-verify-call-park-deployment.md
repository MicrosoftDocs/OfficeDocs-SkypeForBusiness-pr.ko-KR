---
title: ) 비즈니스용 Skype에서 통화 공원 배포 확인
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: 비즈니스용 Skype Server Enterprise Voice에서 통화 공원 배포를 확인 하는 중입니다.
ms.openlocfilehash: 94d230491c0207c05016545de3c45cf0582ca496
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36196289"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="8e13a-103">) 비즈니스용 Skype에서 통화 공원 배포 확인</span><span class="sxs-lookup"><span data-stu-id="8e13a-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="8e13a-104">비즈니스용 Skype Server Enterprise Voice에서 통화 공원 배포를 확인 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="8e13a-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="8e13a-105">통화 대기를 설치 및 구성한 후에는 파킹 및 검색 통화가 예상 대로 작동 하는지 확인 하는 구성을 검증 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e13a-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="8e13a-106">최소한 다음 사항을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="8e13a-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="8e13a-107">통화 공원을 사용 하도록 설정한 사용자에 게 전화를 걸고 사용자에 게 전화를 걸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e13a-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8e13a-108">이 테스트를 수행 하기 전에 음성 정책에서 통화 대기를 사용 하도록 설정한 경우 통화를 진행 하는 사용자는 비즈니스용 Skype에서 로그 아웃 한 다음 다시 로그인 하 여 통화 전송 목록의 통화 대기 옵션을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8e13a-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="8e13a-109">통화를 검색 하려면 궤도 번호로 전화를 겁니다.</span><span class="sxs-lookup"><span data-stu-id="8e13a-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="8e13a-110">다른 전화를 걸고, 파킹 된 통화 시간을 초과 하 고, ringback를 선택 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8e13a-110">Park another call, let the parked call time out, and do not pick up the ringback.</span></span> <span data-ttu-id="8e13a-111">시간 제한 통화가 **Ontimeouturi**에 대해 지정 된 대체 대상으로 올바르게 라우팅 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8e13a-111">Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

