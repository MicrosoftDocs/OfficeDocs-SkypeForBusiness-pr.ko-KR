---
title: 비즈니스용 Skype 서버에서 새 PIN 정책 만들기
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: '요약: 비즈니스용 Skype 서버에서 새 PIN 정책을 만듭니다.'
ms.openlocfilehash: aaedcbfe28cb8e64b4adf7a302eef8c0d3d08a1f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36189684"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="d9022-103">비즈니스용 Skype 서버에서 새 PIN 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="d9022-103">Create a new PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="d9022-104">**요약:** 비즈니스용 Skype 서버에서 새 PIN 정책을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-104">**Summary:** Create a new PIN policy in Skype for Business Server.</span></span>
  
<span data-ttu-id="d9022-105">**Pin 정책** 페이지를 사용 하 여 IP 전화와 함께 비즈니스용 Skype에 연결 하는 사용자에 게 pin (개인 식별 번호) 인증을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-105">You can use the **PIN Policy** page to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="d9022-106">PIN 인증을 사용 하려면 웹 서비스 설정에서 **Pin 인증 사용** 이 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="d9022-107">사용자 수준 또는 사이트 수준 PIN 정책을 만들려면 다음 단계를 따르세요.</span><span class="sxs-lookup"><span data-stu-id="d9022-107">Follow these steps to create a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="d9022-108">사용자 또는 사이트 PIN 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d9022-108">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="d9022-109">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 비즈니스용 Skype 서버를 배포한 네트워크의 컴퓨터에 로그온 합니다. .</span><span class="sxs-lookup"><span data-stu-id="d9022-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="d9022-110">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d9022-111">왼쪽 탐색 모음에서 **보안** 을 클릭 한 다음 **고정 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="d9022-112">**고정 정책** 페이지에서 **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-112">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="d9022-113">사용자 수준 정책을 만들려면 **사용자 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-113">To create a user-level policy, click **User policy**.</span></span> <span data-ttu-id="d9022-114">**새 PIN 정책의** **이름**에 정책을 설명 하는 이름을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-114">In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="d9022-115">사이트 수준 정책을 만들려면 **사이트 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-115">To create a site-level policy, click **Site policy**.</span></span> <span data-ttu-id="d9022-116">사이트 검색 **선택** 필드에 정책을 만들려는 사이트 이름의 전부 또는 일부를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-116">In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy.</span></span> <span data-ttu-id="d9022-117">사이트 결과 목록에서 원하는 사이트를 클릭 한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-117">In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="d9022-118">**설명** 필드에 고정 정책에 대 한 설명을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-118">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="d9022-119">**최소 pin 길이** 필드에 허용 하려는 최소 pin 길이를 입력 하거나 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-119">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow.</span></span> <span data-ttu-id="d9022-120">기본 최소 길이는 다섯 자리입니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-120">The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="d9022-121">사용자가 잠길 때까지 허용 되는 최대 로그온 시도 횟수를 지정할 수 있으려면 **최대 로그온 시도 수 지정** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-121">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box.</span></span> <span data-ttu-id="d9022-122">이 옵션을 선택 하지 않으면 허용 되는 최대 시도 수는 PIN 길이에 따라 자동으로 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-122">If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length.</span></span> <span data-ttu-id="d9022-123">기본적으로 최대 시도 횟수는 자동으로 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-123">By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="d9022-124">최대 로그온 시도 **횟수 지정** 확인란을 선택한 경우 **최대 로그온 시도**에서 허용 하려는 최대 로그온 시도 횟수를 입력 하거나 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-124">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="d9022-125">핀이 만료 되 게 하려면 **PIN 만료 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-125">To have PINs expire, select the **Enable PIN expiration** check box.</span></span> <span data-ttu-id="d9022-126">이 옵션을 선택 하지 않으면 Pin이 만료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-126">If you do not select this option, PINs will never expire.</span></span> <span data-ttu-id="d9022-127">기본적으로 Pin은 만료 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-127">By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="d9022-128">**Pin 만료 사용** 확인란을 선택한 경우 **pin이 (일) 후에 만료**되는 경우 해당 pin이 만료 되는 일 수를 입력 하거나 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-128">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="d9022-129">**Pin 기록 개수**에 사용자가 PIN을 다시 사용할 수 있으려면 먼저 사용자가 만들어야 하는 pin의 수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-129">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN.</span></span> <span data-ttu-id="d9022-130">기본적으로 사용자는 Pin을 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-130">By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="d9022-131">"1234" 및 "8888"와 같이 Pin에 대 한 일반적인 자릿수를 허용 하려면 **공통 패턴 허용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-131">To allow common patterns of digits in PINs, such as "1234" and "8888", select the **Allow common patterns** check box.</span></span> <span data-ttu-id="d9022-132">이 옵션을 선택 하지 않으면 복잡 한 자릿수의 숫자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-132">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="d9022-133">기본적으로 복잡 한 자릿수 패턴만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-133">By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="d9022-134">공통 패턴을 허용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-134">We recommend that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="d9022-135">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d9022-135">Click **Commit**.</span></span>
    

