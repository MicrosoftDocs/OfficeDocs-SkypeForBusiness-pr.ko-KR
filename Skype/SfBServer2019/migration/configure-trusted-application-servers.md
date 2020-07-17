---
title: 트러스트된 응용 프로그램 서버 구성
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
description: 혼합 환경에서 신뢰할 수 있는 응용 프로그램 서버를 새로 만드는 경우에는 다음 홉 풀을 비즈니스용 Skype 서버 2019 풀로 설정 해야 합니다. 혼합 환경에서는 레거시 풀과 비즈니스용 Skype 서버 2019 풀이 모두 드롭다운 목록에 표시 됩니다. 레거시 풀은 선택할 수 없습니다.
ms.openlocfilehash: 1c0aac1efa4f83a81ccf2f3bb5ecbc925ee58839
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753948"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="61c31-105">트러스트된 응용 프로그램 서버 구성</span><span class="sxs-lookup"><span data-stu-id="61c31-105">Configure trusted application servers</span></span>

<span data-ttu-id="61c31-106">혼합 환경에서 신뢰할 수 있는 응용 프로그램 서버를 새로 만드는 경우에는 다음 홉 풀을 비즈니스용 Skype 서버 2019 풀로 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c31-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="61c31-107">혼합 환경에서는 드롭다운 목록에 레거시 풀과 비즈니스용 Skype 서버 2019 풀이 모두 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="61c31-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="61c31-108">레거시 풀은 선택할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="61c31-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="61c31-109">신뢰할 수 있는 응용 프로그램 서버를 마이그레이션하는 경우에는 사용 중인 버전 MA도 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c31-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="61c31-110">비즈니스용 Skype 서버 2019에 대 한 신뢰할 수 있는 응용 프로그램 풀을 새로 만드는 경우 비즈니스용 Skype 서버 2019에 포함 된 버전 또는 사용 가능한 최신 버전으로 요소 MA를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c31-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="61c31-111">신뢰할 수 있는 응용 프로그램 서버를 만들 때 비즈니스용 Skype 서버 2019을 다음 홉으로 선택</span><span class="sxs-lookup"><span data-stu-id="61c31-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="61c31-112">토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="61c31-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="61c31-113">왼쪽 창에서 **신뢰할 수 있는 응용 프로그램 서버** 를 마우스 오른쪽 단추로 클릭 하 고 **새 신뢰할 수 있는 응용 프로그램 풀**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c31-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="61c31-114">신뢰할 수 있는 응용 프로그램 풀의 **풀 FQDN** 을 입력 하 고 단일 서버 또는 다중 서버로 설정할지 여부를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c31-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="61c31-115">**다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="61c31-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="61c31-116">**다음 홉 선택** 페이지의 목록에서 비즈니스용 Skype 서버 2019 프런트 엔드 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c31-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="61c31-117">**마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="61c31-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="61c31-118">최상위 노드인 **비즈니스용 Skype 서버**를 선택 하 고 **동작** 메뉴에서 **게시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c31-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="61c31-119">**신뢰할 수 있는 응용 프로그램 풀이** 성공적으로 만들어졌으며 올바른 프런트 엔드 풀과 연결 되었는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="61c31-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

