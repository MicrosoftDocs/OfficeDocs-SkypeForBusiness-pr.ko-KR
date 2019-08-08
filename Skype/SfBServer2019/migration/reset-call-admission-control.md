---
title: 통화 허용 제어 서비스 다시 설정
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 레거시 프론트 엔드 풀이 CAC (통화 허용 제어)를 호스트 하는 경우에는 레거시 프런트 엔드 풀을 제거 하려면 먼저 CAC 호스팅을 비즈니스용 Skype 서버 2019 풀로 이동 해야 합니다.
ms.openlocfilehash: 812391eda436906020c41b14a53c8ea18c4b1aee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241794"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="42b0f-103">통화 허용 제어 서비스 다시 설정</span><span class="sxs-lookup"><span data-stu-id="42b0f-103">Reset call admission control</span></span>

<span data-ttu-id="42b0f-104">레거시 프론트 엔드 풀이 CAC (통화 허용 제어)를 호스트 하는 경우에는 레거시 프런트 엔드 풀을 제거 하려면 먼저 CAC 호스팅을 비즈니스용 Skype 서버 2019 풀로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="42b0f-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="42b0f-105">CAC를 다시 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="42b0f-105">To reset CAC</span></span>

1. <span data-ttu-id="42b0f-106">토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="42b0f-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="42b0f-107">사이트 노드를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="42b0f-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="42b0f-108">**통화 허용 제어 설정**에서 **통화 허용 제어가** 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="42b0f-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="42b0f-109">**프런트 엔드 풀에서 cac (호출 허용 컨트롤)를 실행 하려면**cac를 호스트할 비즈니스용 Skype 서버 2019 풀을 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="42b0f-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="42b0f-110">토폴로지를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="42b0f-110">Publish the topology.</span></span>
    

