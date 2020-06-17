---
title: 마이그레이션 후 단순 URL 변경
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
description: 비즈니스용 Skype 서버는 단순 Url을 지원 합니다.
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753908"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="ce3e4-103">마이그레이션 후 단순 URL 변경</span><span class="sxs-lookup"><span data-stu-id="ce3e4-103">Change simple URLs after migration</span></span>

<span data-ttu-id="ce3e4-104">비즈니스용 Skype 서버에서는 다음과 같은 세 가지 단순 Url을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce3e4-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="ce3e4-105">**모임**은 사이트 또는 조직의 모든 전화 회의에 대한 기준 URL로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce3e4-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="ce3e4-106">모임 단순 URL을 사용하면 모임에 참가할 링크를 쉽게 이해하고 전달하고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce3e4-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="ce3e4-107">**전화 접속** 을 사용 하면 전화 접속 회의 설정 웹 페이지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce3e4-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="ce3e4-108">전화 접속 단순 URL은 모임에 전화를 거는 사용자가 필요한 전화 번호와 PIN 정보에 액세스할 수 있도록 모든 모임 초대에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce3e4-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="ce3e4-109">**관리자** 는 비즈니스용 Skype 서버 제어판에 빠르게 액세스할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce3e4-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="ce3e4-110">관리 단순 URL은 조직의 내부 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="ce3e4-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="ce3e4-111">비즈니스용 Skype 서버로 마이그레이션한 후에는 변경 내용이 단순 Url에 대 한 DNS 레코드 및 인증서에 미치는 영향을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce3e4-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="ce3e4-112">레거시 비즈니스용 Skype 서버 디렉터를 토폴로지에서 계속 사용 중인 경우에는 단순 Url을 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce3e4-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="ce3e4-113">마이그레이션 후 비즈니스용 Skype 서버 디렉터를 토폴로지에서 제거한 경우에는 비즈니스용 Skype 서버 풀 중 하나를 가리키도록 단순 URL DNS 레코드를 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce3e4-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="ce3e4-114">그러나 단순 URL 이름을 변경할 때마다 각 디렉터 및 프런트 엔드 서버에서 Enable-CsComputer를 실행하여 변경 내용을 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce3e4-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="ce3e4-115">모임 단순 URL을 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="ce3e4-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="ce3e4-116">토폴로지 작성기에서 최상위 노드 **비즈니스용 Skype 서버**를 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce3e4-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="ce3e4-117">왼쪽 창에서 **단순 url** 을 선택한 다음 **모임 Url** 아래에서 회의 url을 선택 하 고 **url 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce3e4-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="ce3e4-118">URL을 원하는 값으로 업데이트하고 **확인**을 클릭하여 편집한 URL을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="ce3e4-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="ce3e4-119">관리 단순 URL을 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="ce3e4-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="ce3e4-120">토폴로지 작성기에서 최상위 노드 **비즈니스용 Skype 서버**를 마우스 오른쪽 단추로 클릭 하 고 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce3e4-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="ce3e4-121">왼쪽 창에서 **단순 url** 을 선택한 다음 **관리 액세스 URL** 상자 아래에 있는 비즈니스용 Skype 서버 제어판에 대 한 관리 액세스용으로 사용할 단순 url을 입력 하 고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce3e4-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="ce3e4-122">관리 URL에는 최대한 간단한 URL을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ce3e4-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="ce3e4-123">가장 간단한 방법은 https://admin 입니다. <em>\<domain\></em></span><span class="sxs-lookup"><span data-stu-id="ce3e4-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ce3e4-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce3e4-124">See also</span></span>

[<span data-ttu-id="ce3e4-125">비즈니스용 Skype 서버의 단순 Url에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="ce3e4-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
