---
title: 통화 허용 제어 서비스 다시 설정
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 레거시 프론트 엔드 풀이 CAC (통화 허용 제어)를 호스트 하는 경우에는 레거시 프런트 엔드 풀을 제거 하려면 먼저 CAC 호스팅을 비즈니스용 Skype 서버 2019 풀로 이동 해야 합니다.
ms.openlocfilehash: cbc481e55d044ef196bd91dbfa8f7ebc796f28b5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812806"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="e4ca2-103">통화 허용 제어 서비스 다시 설정</span><span class="sxs-lookup"><span data-stu-id="e4ca2-103">Reset call admission control</span></span>

<span data-ttu-id="e4ca2-104">레거시 프론트 엔드 풀이 CAC (통화 허용 제어)를 호스트 하는 경우에는 레거시 프런트 엔드 풀을 제거 하려면 먼저 CAC 호스팅을 비즈니스용 Skype 서버 2019 풀로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ca2-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="e4ca2-105">CAC를 다시 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="e4ca2-105">To reset CAC</span></span>

1. <span data-ttu-id="e4ca2-106">토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e4ca2-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="e4ca2-107">사이트 노드를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ca2-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="e4ca2-108">**통화 허용 제어 설정**에서 **통화 허용 제어가** 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ca2-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="e4ca2-109">**프런트 엔드 풀에서 cac (호출 허용 컨트롤)를 실행 하려면**cac를 호스트할 비즈니스용 Skype 서버 2019 풀을 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ca2-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="e4ca2-110">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e4ca2-110">Publish the topology.</span></span>
    

