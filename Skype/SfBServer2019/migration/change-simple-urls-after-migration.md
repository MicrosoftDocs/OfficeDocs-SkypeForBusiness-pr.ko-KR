---
title: 마이그레이션 후 단순 URL 변경
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
description: 비즈니스용 Skype 서버는 간단한 Url을 지원 합니다.
ms.openlocfilehash: ab820c1b24eb9b2e8befc85a34e82d068c9083ea
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813886"
---
# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="2fb6a-103">마이그레이션 후 단순 URL 변경</span><span class="sxs-lookup"><span data-stu-id="2fb6a-103">Change simple URLs after migration</span></span>

<span data-ttu-id="2fb6a-104">비즈니스용 Skype 서버는 다음과 같은 세 가지 간단한 Url을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb6a-104">Skype for Business Server supports three simple URLs:</span></span>
  
- <span data-ttu-id="2fb6a-105">**회의** 는 사이트 또는 조직의 모든 컨퍼런스에 대 한 기본 URL로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2fb6a-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="2fb6a-106">모임에 참여 하는 간단한 URL을 사용 하 여 모임을 연결 하는 링크는 이해 하기 쉬우며, 의사 소통 및 배포 하기가 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb6a-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span> 
    
- <span data-ttu-id="2fb6a-107">**전화 접속-** 전화 접속 회의 설정 웹 페이지에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb6a-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="2fb6a-108">모임에 전화를 걸려면 사용자가 필요한 전화 번호와 PIN 정보에 액세스할 수 있도록 전화 접속 간단한 URL이 모든 모임 초대에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb6a-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span> 
    
- <span data-ttu-id="2fb6a-109">**관리자** 는 비즈니스용 Skype Server 제어판에 빠르게 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb6a-109">**Admin** enables quick access to the Skype for Business Server Control Panel.</span></span> <span data-ttu-id="2fb6a-110">관리 단순 URL은 조직 내부입니다.</span><span class="sxs-lookup"><span data-stu-id="2fb6a-110">The Admin simple URL is internal to your organization.</span></span> 
    
<span data-ttu-id="2fb6a-111">비즈니스용 Skype 서버를 마이그레이션한 후에는 변경 내용이 간단한 Url에 대 한 DNS 레코드 및 인증서에 어떤 영향을 미치는지 알아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb6a-111">After migrating to Skype for Business Server, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="2fb6a-112">레거시 비즈니스용 Skype Server Director가 토폴로지에서 사용 중인 경우에는 간단한 Url을 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb6a-112">If the legacy Skype for Business Server Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="2fb6a-113">마이그레이션 후에 비즈니스용 Skype 서버 디렉터가 토폴로지에서 제거 되는 경우 간단한 URL DNS 레코드를 비즈니스용 Skype 서버 풀 중 하나를 가리키도록 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb6a-113">If the Skype for Business Server Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Skype for Business Server pools.</span></span> <span data-ttu-id="2fb6a-114">그러나 간단한 URL 이름을 변경할 때마다 각 디렉터 및 프런트 엔드 서버에서-CsComputer를 실행 하 여 변경 내용을 등록 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb6a-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

## <a name="to-update-the-meet-simple-url"></a><span data-ttu-id="2fb6a-115">기본 모임 URL을 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="2fb6a-115">To update the Meet simple URL</span></span>

1. <span data-ttu-id="2fb6a-116">토폴로지 작성기에서 상위 노드 **비즈니스용 Skype 서버**를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb6a-116">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="2fb6a-117">왼쪽 창에서 **간단한 url** 을 선택 하 고 모임 url 아래에 있는 url을 선택한 다음 **url 편집**을 클릭 합니다 **.**</span><span class="sxs-lookup"><span data-stu-id="2fb6a-117">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>
    
3. <span data-ttu-id="2fb6a-118">URL을 원하는 값으로 업데이트 한 다음 **확인** 을 클릭 하 여 편집한 url을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb6a-118">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span> 
    
## <a name="to-update-the-admin-simple-url"></a><span data-ttu-id="2fb6a-119">관리 간단한 URL을 업데이트 하려면</span><span class="sxs-lookup"><span data-stu-id="2fb6a-119">To update the Admin simple URL</span></span>

1. <span data-ttu-id="2fb6a-120">토폴로지 작성기에서 상위 노드 **비즈니스용 Skype 서버**를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb6a-120">In Topology Builder, right-click the top node **Skype for Business Server**, and then click **Edit Properties**.</span></span>
    
2. <span data-ttu-id="2fb6a-121">왼쪽 창에서 **간단한 url** 을 선택 하 고 **관리 액세스 URL** 상자 아래에 있는 비즈니스용 Skype Server 제어판의 관리 액세스에 사용할 간단한 url을 입력 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="2fb6a-121">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Skype for Business Server Control Panel, and then click **OK**.</span></span>
    
   > [!TIP]
   > <span data-ttu-id="2fb6a-122">관리 URL에 가장 간단한 URL을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2fb6a-122">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="2fb6a-123">가장 간단한 방법은 https://admin입니다. <em> \<도메인\></em>.</span><span class="sxs-lookup"><span data-stu-id="2fb6a-123">The simplest option is https://admin.<em>\<domain\></em>.</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2fb6a-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2fb6a-124">See also</span></span>

[<span data-ttu-id="2fb6a-125">비즈니스용 Skype 서버의 간단한 Url에 대 한 DNS 요구 사항</span><span class="sxs-lookup"><span data-stu-id="2fb6a-125">DNS requirements for simple URLs in Skype for Business Server</span></span>](../../SfbServer/plan-your-deployment/network-requirements/simple-urls.md)
