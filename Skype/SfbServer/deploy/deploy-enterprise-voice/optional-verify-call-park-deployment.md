---
title: (선택 사항) 비즈니스용 Skype에서 통화 파크 배포 확인
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
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: 비즈니스용 Skype 서버에서 통화 파킹 배포 Enterprise Voice.
ms.openlocfilehash: a7edb9f47610bf7cdae068ca789670ab4048bb9c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830898"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a><span data-ttu-id="dbc3c-103">(선택 사항) 비즈니스용 Skype에서 통화 파크 배포 확인</span><span class="sxs-lookup"><span data-stu-id="dbc3c-103">(Optional) Verify Call Park deployment in Skype for Business</span></span>
 
<span data-ttu-id="dbc3c-104">비즈니스용 Skype 서버에서 통화 파킹 배포 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="dbc3c-104">Verifying your deployment of Call Park in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="dbc3c-105">통화 파킹을 설치 및 구성한 후 통화를 파킹하고 검색하는 통화가 예상대로 작동하는지 구성을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbc3c-105">After you install and configure Call Park, you need to verify the configuration to make sure that parking and retrieving calls works as expected.</span></span> <span data-ttu-id="dbc3c-106">최소한 다음 사항을 확인하십시오.</span><span class="sxs-lookup"><span data-stu-id="dbc3c-106">At minimum, verify the following:</span></span>
  
- <span data-ttu-id="dbc3c-107">통화 파크를 사용하도록 설정한 사용자에게 전화를 걸고 사용자가 통화를 파크하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbc3c-107">Call a user who has Call Park enabled and have the user park the call.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="dbc3c-108">이 테스트를 수행하기 직전에 음성 정책에서 통화 파킹을 사용하도록 설정한 경우 통화를 파킹된 사용자가 전송 통화 목록에서 통화 파킹 옵션을 볼 수 있도록 비즈니스용 Skype에서 로그인한 다음 다시 로그인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbc3c-108">If you enabled Call Park in voice policy just before performing this test, the user who is parking the call needs to sign out of Skype for Business, and then sign back in, to be able to see the Call Park option in the transfer call list.</span></span> 
  
- <span data-ttu-id="dbc3c-109">파킹된 통화 번호로 전화를 걸어 통화를 재개합니다.</span><span class="sxs-lookup"><span data-stu-id="dbc3c-109">Dial the orbit number to retrieve the call.</span></span>
    
- <span data-ttu-id="dbc3c-p102">다른 통화를 대기 상태로 설정하고 대기된 통화의 제한 시간을 초과시키며 되걸려오는 전화를 받지 않습니다. 제한 시간이 초과된 통화가 **OnTimeoutURI** 에 지정한 대체 대상으로 제대로 라우팅되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="dbc3c-p102">Park another call, let the parked call time out, and do not pick up the ringback. Verify that the timed-out call is correctly routed to the fallback destination that is specified for **OnTimeoutURI**.</span></span>
    

