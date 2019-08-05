---
title: 비즈니스용 Skype 서버에 대 한 사용자 계정 속성 사용자 지정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: 이 섹션의 절차를 사용 하 여 개별 사용자 계정 속성을 수정할 수 있습니다.
ms.openlocfilehash: fda11a1b52519f3653c841837af20392383cadd1
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/25/2019
ms.locfileid: "36197858"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="ab279-103">비즈니스용 Skype 서버에 대 한 사용자 계정 속성 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="ab279-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="ab279-104">이 섹션의 절차를 사용 하 여 개별 사용자 계정 속성을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="ab279-105">개별 사용자 수준에서 수행할 수 있는 두 가지 기본 작업은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="ab279-106">특정 사용자 계정에 대 한 전화 통신 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="ab279-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="ab279-107">다른 풀로 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="ab279-107">Move users to another pool</span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="ab279-108">특정 사용자 계정에 대 한 전화 통신 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="ab279-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="ab279-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="ab279-109"></span></span>

<span data-ttu-id="ab279-110">특정 사용자에 대 한 전화 통신 설정을 사용자 지정할 수 있습니다 (비즈니스용 Skype 서버에서 개별 사용자가 사용 하도록 설정 되어 있고 조직이 전화 접속을 지 원하는 경우).</span><span class="sxs-lookup"><span data-stu-id="ab279-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="ab279-111">비즈니스용 Skype 서버 사용자 전화 통신 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="ab279-112">**오디오/비디오 사용 안 함** 사용자가 음성 및 영상 통화를 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="ab279-113">**Pc 대 pc 전용** 사용자는 pc 대 PC 음성 또는 영상 통화만 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="ab279-114">**엔터프라이즈 음성** 사용자는 비즈니스용 Skype 서버 인프라를 사용 하 여 수신 및 발신 전화를 모두 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="ab279-115">사용자는 PC 대 PC 전화도 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="ab279-116">**원격 통화 제어** 사용자는 비즈니스용 Skype 서버를 사용 하 여 데스크톱 전화를 제어할 수 있으며 PC 대 PC 통화를 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="ab279-117">조직의 전화 통신을 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 엔터프라이즈 음성을 사용할 수 있도록 설정](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) 하 고 배포 설명서의 [비즈니스용 Skype 서버에서 enterprise voice 배포](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ab279-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="ab279-118">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ab279-119">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="ab279-120">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="ab279-121">**사용자 검색** 상자에 원하는 사용자 계정의 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 줄의 URI (Uniform resource identifier) 중 일부 또는 전체를 입력 한 다음 찾기를 클릭 합니다. \*\* \*\*.</span><span class="sxs-lookup"><span data-stu-id="ab279-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="ab279-122">표에서 수정 하려는 사용자 계정을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="ab279-123">**편집** 메뉴에서 **수정을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="ab279-124">**전화 통신**에서 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="ab279-125">사용자에 게 오디오 및 비디오 통화를 사용 하지 않도록 설정 하려면 **오디오/비디오 사용 안 함을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="ab279-126">사용자에 대해 PC 대 PC 오디오 통신을 사용 하도록 설정 하 고, 원격 통화 제어 또는 엔터프라이즈 음성을 지원 하지 않으려면 **pc 대 pc 전용**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-126">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**.</span></span> <span data-ttu-id="ab279-127">사용자가 PC 대 PC 오디오 통신에 사용 하는 전화의 **회선 URI** 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-127">Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="ab279-128">Pc 대 PC 오디오 통신을 비롯 한 서비스 정책 수업에 따라 비즈니스용 Skype 인프라를 사용 하 여 사용자의 전화 통화를 라우팅하려면 **엔터프라이즈 음성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="ab279-129">**줄 URI**에서 엔터프라이즈 음성의 전화 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="ab279-130">**다이얼 플랜 정책** 및 **음성 정책**에서 사용자에 대 한 적절 한 정책을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="ab279-131">사용자가 거는 전화 번호를 E 164 형식으로 변환 하기 위한 정규화 규칙을 지정 하려면 **위치 정책**에서 적절 한 위치 프로필을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="ab279-132">사용자가 비즈니스용 Skype 서버에서 데스크톱 전화선을 제어 하 여 pc에서 PC로 거는 통화와 PC에서 전화를 걸 수 있도록 하는 원격 통화 제어 기능을 사용 하도록 설정 하려면 **원격 통화 제어**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="ab279-133">**줄 URI**에서 원격 통화 제어에 대 한 전화 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="ab279-134">사용자에 게는 전화 라우팅에 대해 데스크톱 전화 및 PBX (개인 브랜치 교환) 연결이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="ab279-135">다른 풀로 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="ab279-135">Move users to another pool</span></span>
<span data-ttu-id="ab279-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="ab279-136"></span></span>

<span data-ttu-id="ab279-137">비즈니스용 Skype Server 제어판을 사용 하 여 특정 서버나 풀에 사용자를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="ab279-138">Lync Server 2010 이전 버전을 실행 하는 원본 풀의 모든 기존 사용자를 복잡 한 Active Directory 환경의 비즈니스용 Skype 서버 대상 풀에서 이동 하면 Active Directory 복제 속도가 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="ab279-139">이러한 문제를 방지 하려면 검색 필터를 사용 하 여 Lync Server 2010 이전 버전을 실행 하는 풀에서 사용자를 개별적으로 이동 하거나 비즈니스용 Skype Server Management Shell을 사용 하 여 사용자를 cmdlet으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="ab279-140">또한 필터 기능은 비즈니스용 Skype 서버 사용자에 게 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="ab279-141">선택한 사용자를 다른 서버 또는 풀로 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="ab279-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="ab279-142">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ab279-143">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="ab279-144">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="ab279-145">**사용자 검색** 상자에 원하는 사용자 계정의 표시 이름, 이름, 성, SAM (보안 계정 관리자) 계정 이름, SIP 주소 또는 줄의 URI (Uniform resource identifier) 중 일부 또는 전체를 입력 한 다음 찾기를 클릭 합니다. \*\* \*\*.</span><span class="sxs-lookup"><span data-stu-id="ab279-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="ab279-146">표에서 특정 사용자 또는 목록에서 사용자를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="ab279-147">**작업** 메뉴에서 **선택한 사용자 이동을 클릭 하 여 그룹으로 이동**합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="ab279-148">**사용자 이동**에서 **대상 등록자 풀**로 사용자를 이동 하려는 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="ab279-149">) 대상 서버 또는 풀을 사용할 수 없는 경우 **강제** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="ab279-150">**강제**를 선택 하면 사용자 계정이 이동 되지만 연결 된 사용자 데이터는 삭제 됩니다 (예: 사용자가 예약한 컨퍼런스).</span><span class="sxs-lookup"><span data-stu-id="ab279-150">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="ab279-151">이를 선택 하지 않으면 계정과 관련 데이터가 모두 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-151">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="ab279-152">한 서버 또는 풀의 모든 사용자를 다른 서버 또는 풀로 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="ab279-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="ab279-153">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ab279-154">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="ab279-155">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="ab279-156">**작업** 메뉴에서 **모든 사용자를 풀로 이동을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="ab279-157">**사용자 이동**에서 **원본 등록자 풀**에서 이동 하려는 사용자 계정이 포함 된 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="ab279-158">**대상 등록자 풀**에서 사용자를 이동 하려는 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="ab279-159">) 대상 서버 또는 풀을 사용할 수 없는 경우 **강제** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="ab279-160">**강제**를 선택 하면 사용자 계정이 이동 되지만 연결 된 사용자 데이터는 삭제 됩니다 (예: 사용자가 예약한 컨퍼런스).</span><span class="sxs-lookup"><span data-stu-id="ab279-160">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled).</span></span> <span data-ttu-id="ab279-161">이를 선택 하지 않으면 계정과 관련 데이터가 모두 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-161">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="ab279-162">필터를 사용 하 여 한 풀에서 다른 풀로 사용자를 이동 하려면</span><span class="sxs-lookup"><span data-stu-id="ab279-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="ab279-163">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ab279-164">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="ab279-165">왼쪽 탐색 모음에서 **사용자**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="ab279-166">**사용자 검색**에서 **검색**을 클릭 한 다음 **필터 추가**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="ab279-167">검색 조건에서 **등록자 그룹**을 선택 하 고 **같음**, **현재 풀 FQDN**을 차례로 선택한 다음 **찾기를**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="ab279-168">**작업** 메뉴에서 **모든 사용자를 풀로 이동을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ab279-169">기존 사용자 집합에 필터가 적용 되는 경우 **모든 사용자를 풀로 이동 하** 는 옵션이 사용자의 필터링 된 하위 집합에 해당 하는 것이 아니라 \*\*\*\* 모든 사용자가 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="ab279-170">**사용자 이동**에서 **원본 등록자 풀**에서 이동 하려는 사용자 계정이 포함 된 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="ab279-171">**대상 등록자 풀**에서 사용자를 이동 하려는 풀을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="ab279-172">) 대상 서버 또는 풀을 사용할 수 없는 경우 **강제** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="ab279-173">**강제**를 선택 하면 사용자 계정이 이동 되지만 연결 된 사용자 데이터는 삭제 됩니다 (예: 사용자가 예약 하 고 연락처를 사용 하는 컨퍼런스).</span><span class="sxs-lookup"><span data-stu-id="ab279-173">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts).</span></span> <span data-ttu-id="ab279-174">이를 선택 하지 않으면 계정과 관련 데이터가 모두 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-174">If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="ab279-175">Windows Powershell cmdlet을 사용 하 여 한 풀에서 다른 그룹으로 사용자 이동</span><span class="sxs-lookup"><span data-stu-id="ab279-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="ab279-176">Windows PowerShell 명령 (로컬 또는 원격)을 실행 하는 방법에 따라 다음과 같이 올바른 비즈니스용 Skype 서버 관리 역할의 구성원으로 로그온 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="ab279-177">에서.</span><span class="sxs-lookup"><span data-stu-id="ab279-177">a.</span></span> <span data-ttu-id="ab279-178">로컬 컴퓨터에서 명령을 실행 하는 경우 (예: 프런트 엔드 서버에 직접 로그온 하는 경우) 다음을 수행 합니다. 비즈니스용 Skype 서버 관리 셸이 설치 된 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원으로 로그온 하거나 필요한 경우 **대리인 설정 권한에**설명 된 대로 사용자 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="ab279-179">b.</span><span class="sxs-lookup"><span data-stu-id="ab279-179">b.</span></span> <span data-ttu-id="ab279-180">다른 컴퓨터에서 원격으로 명령을 실행 하는 경우 (예: 컴퓨터에 로그온 하 고 표준 Edition 프런트 엔드 서버에서 원격으로 명령을 실행 하는 경우) 다음을 수행 합니다. CsUserAdministrator 역할 또는 CsAdministrator에 할당 된 사용자 계정에서 역할을 설정 하 고 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="ab279-181">비즈니스용 Skype 서버 관리 셸을 시작 합니다. **시작**, **모든 프로그램**, **비즈니스용 skype**를 차례로 클릭 한 다음 비즈니스용 **skype server management shell**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="ab279-182">단일 사용자를 이동 하려면 다음과 같이 Move-CsUser cmdlet을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="ab279-183">이동할 사용자가 사용자 Pilar Ackerman이 고 사용자가 현재 할당 된 홈 풀에서 pool pool01.contoso.net 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="ab279-184">많은 수의 사용자를 이동 하려면 **Get-csuser** cmdlet을 사용 하 여 필터를 사용 하 고 사용자의 결과 집합을 **이동-csuser**에 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="ab279-185">**Get csuser** 및 **Move csuser** 의 결합 된 명령은 다음과 같이 표시 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ab279-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


