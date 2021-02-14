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
description: 비즈니스용 Skype 서버는 단순 URL을 지원합니다.
ms.openlocfilehash: 1b25dd74f5bdca433554091b3f8ce1c1d2dfa8ce
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753908"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="612aa-103">마이그레이션 후 단순 URL 변경</span><span class="sxs-lookup"><span data-stu-id="612aa-103">Change simple URLs after migration</span></span>

<span data-ttu-id="612aa-104">비즈니스용 Skype 서버는 세 가지 단순 URL을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="612aa-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="612aa-105">**모임** 은 사이트 또는 조직의 모든 전화 회의에 대한 기준 URL로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="612aa-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="612aa-106">모임 단순 URL을 사용하면 모임에 참가할 링크를 쉽게 이해하고 전달하고 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612aa-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="612aa-107">**전화 접속을** 사용하면 전화 접속 회의 설정 웹 페이지로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612aa-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="612aa-108">전화 접속 단순 URL은 모임에 전화 접속하려는 사용자가 필요한 전화 번호 및 PIN 정보에 액세스할 수 있도록 모든 모임 초대에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="612aa-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="612aa-109">**관리자는** 비즈니스용 Skype 서버 제어판에 빠르게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="612aa-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="612aa-110">관리 단순 URL은 조직의 내부 URL입니다.</span><span class="sxs-lookup"><span data-stu-id="612aa-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="612aa-111">비즈니스용 Skype 서버로 마이그레이션한 후 변경이 단순 URL에 대한 DNS 레코드 및 인증서에 미치는 영향을 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612aa-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="612aa-112">레거시 비즈니스용 Skype 서버 Director가 토폴로지에서 계속 사용 중이면 단순 URL을 변경할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="612aa-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="612aa-113">마이그레이션 후 비즈니스용 Skype 서버 Director가 토폴로지에서 제거된 경우 단순 URL DNS 레코드가 비즈니스용 Skype 서버 풀 중 하나를 지점으로 하여 업데이트되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612aa-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="612aa-114">그러나 단순 URL 이름을 변경할 때마다 각 디렉터 및 프런트 엔드 서버에서 Enable-CsComputer를 실행하여 변경 내용을 등록해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="612aa-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="612aa-115">Meet 단순 URL을 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="612aa-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="612aa-116">토폴로지 작성기에서 위쪽 노드 **비즈니스용 Skype 서버를** 마우스 오른쪽 단추로 클릭한 다음 속성 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="612aa-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="612aa-117">왼쪽 창에서 단순 **URL을** 선택한 다음  모임 URL 아래에서 모임 URL을 선택한 다음 URL 편집을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="612aa-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="612aa-118">URL을 원하는 값으로 업데이트하고 **확인** 을 클릭하여 편집한 URL을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="612aa-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="612aa-119">관리 단순 URL을 업데이트하려면</span><span class="sxs-lookup"><span data-stu-id="612aa-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="612aa-120">토폴로지 작성기에서 위쪽 노드 **비즈니스용 Skype 서버를** 마우스 오른쪽 단추로 클릭한 다음 속성 **편집을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="612aa-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="612aa-121">왼쪽 **창에서** 단순 URL을 선택한 다음 관리 액세스 URL 상자 아래에 비즈니스용 Skype 서버 제어판에 대한 관리 액세스에 사용할 단순 **URL을** 입력한 다음 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="612aa-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="612aa-122">관리 URL에는 최대한 간단한 URL을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="612aa-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="612aa-123">가장 간단한 옵션은 https://admin . <em>\<domain\></em> .</span><span class="sxs-lookup"><span data-stu-id="612aa-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="612aa-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="612aa-124">See also</span></span>

[<span data-ttu-id="612aa-125">비즈니스용 Skype 서버의 단순 URL에 대한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="612aa-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
