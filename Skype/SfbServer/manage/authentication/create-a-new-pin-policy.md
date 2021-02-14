---
title: 비즈니스용 Skype 서버에서 새 PIN 정책 만들기
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 8bdf0478-fe9f-4371-93ff-db39381a25db
description: '요약: 비즈니스용 Skype 서버에서 새 PIN 정책을 만들 수 있습니다.'
ms.openlocfilehash: b0d1be74e509fbaddfc59250f4f5ce05a2021260
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828408"
---
# <a name="create-a-new-pin-policy-in-skype-for-business-server"></a><span data-ttu-id="faa76-103">비즈니스용 Skype 서버에서 새 PIN 정책 만들기</span><span class="sxs-lookup"><span data-stu-id="faa76-103">Create a new PIN policy in Skype for Business Server</span></span>
 
<span data-ttu-id="faa76-104">**요약:** 비즈니스용 Skype 서버에서 새 PIN 정책을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-104">**Summary:** Create a new PIN policy in Skype for Business Server.</span></span>
  
<span data-ttu-id="faa76-105">**PIN** 정책 페이지를 사용하여 IP 전화를 사용하여 비즈니스용 Skype에 연결하는 사용자에게 PIN(개인 식별 번호) 인증을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-105">You can use the **PIN Policy** page to provide personal identification number (PIN) authentication to users who are connecting to Skype for Business with IP Phones.</span></span> <span data-ttu-id="faa76-106">PIN 인증을 사용하려면 웹 서비스 설정에서 **PIN 인증 사용** 이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-106">To use PIN authentication, make sure that **Enable PIN Authentication** is selected in Web Service settings.</span></span>
  
<span data-ttu-id="faa76-107">사용자 수준 또는 사이트 수준 PIN 정책을 만들려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-107">Follow these steps to create a user-level or a site-level PIN policy.</span></span> 
  
### <a name="to-create-a-user-or-site-pin-policy"></a><span data-ttu-id="faa76-108">사용자 또는 사이트 PIN 정책을 만들려면</span><span class="sxs-lookup"><span data-stu-id="faa76-108">To create a user or site PIN policy</span></span>

1.  <span data-ttu-id="faa76-109">RTCUniversalServerAdmins 그룹의 구성원인 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 비즈니스용 Skype 서버를 배포한 네트워크에 있는 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>
    
2. <span data-ttu-id="faa76-110">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="faa76-111">왼쪽 탐색 모음에서 **보안** 을 클릭하고 **PIN 정책** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-111">In the left navigation bar, click **Security** and then click **PIN Policy**.</span></span>
    
4. <span data-ttu-id="faa76-112">**PIN 정책** 페이지에서 **새로 만들기** 를 클릭한 다음, 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-112">On the **PIN Policy** page, click **New**, and then do one of the following:</span></span>
    
   - <span data-ttu-id="faa76-p102">사용자 수준 정책을 만들려면 **사용자 정책** 을 클릭합니다. **새 PIN 정책** 의 **이름** 에 정책에 대해 설명하는 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-p102">To create a user-level policy, click **User policy**. In **New PIN Policy**, in **Name**, type a name that describes the policy.</span></span>
    
   - <span data-ttu-id="faa76-p103">사이트 수준 정책을 만들려면 **사이트 정책** 을 클릭합니다. **사이트 선택** 검색 필드에 정책을 만들 사이트의 이름 전부 또는 일부를 입력합니다. 사이트 결과 목록에서 원하는 사이트를 클릭한 다음 **확인** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-p103">To create a site-level policy, click **Site policy**. In the **Select a Site** search field, type all or part of the name of the site for which you want to create a policy. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="faa76-118">**설명** 필드에 PIN 정책에 대한 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-118">In the **Description** field, type a description of the PIN policy.</span></span>
    
6. <span data-ttu-id="faa76-p104">**최소 PIN 길이** 필드에서 허용할 최소 PIN 길이를 입력하거나 선택합니다. 기본 최소 길이는 5자리입니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-p104">In the **Minimum PIN length** field, type or select the minimum PIN length that you want to allow. The default minimum length is five digits.</span></span>
    
7. <span data-ttu-id="faa76-p105">사용자가 잠길 때까지의 최대 로그온 시도 횟수를 지정하려면 **최대 로그온 시도 횟수 지정** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 PIN 길이에 따라 최대 로그온 시도 횟수가 자동으로 결정됩니다. 기본적으로 최대 시도 횟수는 자동으로 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-p105">To be able to specify the maximum number of logon attempts before a user is locked out, select the **Specify maximum logon attempts** check box. If you do not select this option, the maximum number of allowed attempts is automatically determined based on the PIN length. By default, the maximum number of attempts is automatically determined.</span></span>
    
8. <span data-ttu-id="faa76-124">**최대 로그온 시도 횟수 지정** 확인란을 선택한 경우 **최대 로그온 시도 횟수** 에 허용할 최대 로그온 시도 횟수를 입력하거나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-124">If you selected the **Specify maximum logon attempts** check box, in **Maximum logon attempts**, type or select the maximum number of logon attempts that you want to allow.</span></span>
    
9. <span data-ttu-id="faa76-p106">PIN이 만료되도록 하려면 **PIN 만료 사용** 확인란을 선택합니다. 이 옵션을 선택하지 않으면 PIN이 만료되지 않습니다. 기본적으로 PIN은 만료되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-p106">To have PINs expire, select the **Enable PIN expiration** check box. If you do not select this option, PINs will never expire. By default, PINs never expire.</span></span>
    
10. <span data-ttu-id="faa76-128">**PIN 만료 사용** 확인란을 선택한 경우 **다음 이후 PIN 만료(일)** 에 PIN이 만료될 때까지의 기간(일)을 입력하거나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-128">If you selected the **Enable PIN expiration** check box, in **PIN expires after (days)**, type or select the number of days after which PINs expire.</span></span>
    
11. <span data-ttu-id="faa76-p107">**PIN 기록 카운트** 에 사용자가 PIN을 다시 사용할 수 있을 때까지 만들어야 하는 PIN의 개수를 입력합니다. 기본적으로 사용자는 PIN을 다시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-p107">In **PIN history count**, type the number of PINs that a user must create before the user can reuse a PIN. By default, users can reuse their PINs.</span></span>
    
12. <span data-ttu-id="faa76-131">"1234" 및 "8888"과 같은 PINS의 공통 숫자 패턴을  허용하려면 공통 패턴 허용 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-131">To allow common patterns of digits in PINs, such as "1234" and "8888", select the **Allow common patterns** check box.</span></span> <span data-ttu-id="faa76-132">이 옵션을 선택하지 않으면 복잡한 숫자 패턴만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-132">If you do not select this option, only complex patterns of digits are allowed.</span></span> <span data-ttu-id="faa76-133">기본적으로는 복잡한 숫자 패턴만 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-133">By default, only complex patterns of digits are allowed.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="faa76-134">공통 패턴은 허용하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-134">We recommend that you do not allow common patterns.</span></span> 
  
13. <span data-ttu-id="faa76-135">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="faa76-135">Click **Commit**.</span></span>
    

