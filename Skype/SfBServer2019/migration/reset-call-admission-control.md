---
title: 통화 허용 콘트롤 재설정
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 레거시 프런트 엔드 풀이 CAC(통화 제어)를 호스팅하는 경우 레거시 프런트 엔드 풀을 제거하려면 먼저 CAC 호스팅을 비즈니스용 Skype 서버 2019 풀로 이동해야 합니다.
ms.openlocfilehash: 850ab5c13483d024d52c483c63ef09468f8374b3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753300"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="d49f4-103">통화 허용 콘트롤 재설정</span><span class="sxs-lookup"><span data-stu-id="d49f4-103">Reset call admission control</span></span>

<span data-ttu-id="d49f4-104">레거시 프런트 엔드 풀이 CAC(통화 제어)를 호스팅하는 경우 레거시 프런트 엔드 풀을 제거하려면 먼저 CAC 호스팅을 비즈니스용 Skype 서버 2019 풀로 이동해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d49f4-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="d49f4-105">CAC를 다시 설정하려면</span><span class="sxs-lookup"><span data-stu-id="d49f4-105">To reset CAC</span></span>

1. <span data-ttu-id="d49f4-106">토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d49f4-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="d49f4-107">사이트 노드를 마우스 오른쪽 단추로 클릭한 다음 **속성 편집** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d49f4-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="d49f4-108">**통화 허용 제어 설정** 아래에서 **통화 허용 제어 사용** 이 선택되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d49f4-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="d49f4-109">**CAC(통화 제어)를** 실행하려면 프런트 엔드 풀에서 CAC를 호스팅할 비즈니스용 Skype 서버 2019 풀을 선택한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="d49f4-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="d49f4-110">토폴로지를 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="d49f4-110">Publish the topology.</span></span>
    

