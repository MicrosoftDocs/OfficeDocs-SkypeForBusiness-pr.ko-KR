---
title: 비즈니스용 Skype 서버의 사용자 계정 속성 사용자 지정
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
ms.assetid: 505d9619-adab-4cc4-b054-89286e18a19b
description: 이 섹션의 절차에 따라 개별 사용자 계정 속성을 수정할 수 있습니다.
ms.openlocfilehash: 6f2c3a76f9047da0a5d78695518cfb8355ab82e3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826268"
---
# <a name="customize-user-account-properties-for-skype-for-business-server"></a><span data-ttu-id="46b8c-103">비즈니스용 Skype 서버의 사용자 계정 속성 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="46b8c-103">Customize user account properties for Skype for Business Server</span></span>
 
<span data-ttu-id="46b8c-104">이 섹션의 절차에 따라 개별 사용자 계정 속성을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-104">You can use the procedures in this section to modify individual user account properties.</span></span>
  
<span data-ttu-id="46b8c-105">개별 사용자 수준에서는 다음 두 가지 기본 작업을 수행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-105">There are two basic operations that can be done at the individual user level:</span></span>
  
- [<span data-ttu-id="46b8c-106">특정 사용자 계정에 대한 전화 통신 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="46b8c-106">Configure telephony options for a specific user account</span></span>](customize-properties.md#Tel_Op)
    
- [<span data-ttu-id="46b8c-107">사용자를 다른 풀로 이동</span><span class="sxs-lookup"><span data-stu-id="46b8c-107">Move users to another pool</span></span>](customize-properties.md#Move_Users)
    
## <a name="configure-telephony-options-for-a-specific-user-account"></a><span data-ttu-id="46b8c-108">특정 사용자 계정에 대한 전화 통신 옵션 구성</span><span class="sxs-lookup"><span data-stu-id="46b8c-108">Configure telephony options for a specific user account</span></span>
<span data-ttu-id="46b8c-109"><a name="Tel_Op"> </a></span><span class="sxs-lookup"><span data-stu-id="46b8c-109"><a name="Tel_Op"> </a></span></span>

<span data-ttu-id="46b8c-110">개별 사용자가 비즈니스용 Skype 서버에 대해 사용하도록 설정되어 있으며 조직에서 전화 통신을 지원하는 경우 특정 사용자에 대한 전화 통신 설정을 사용자 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-110">You can customize the telephony settings for a specific user (so long as the individual user has been enabled for Skype for Business Server and the organization supports telephony).</span></span>
  
<span data-ttu-id="46b8c-111">비즈니스용 Skype 서버 사용자 전화 통신 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-111">Skype for Business Server user telephony options include the following:</span></span>
  
- <span data-ttu-id="46b8c-112">**오디오/비디오 사용 안** 사용자는 오디오 및 비디오로 전화를 걸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-112">**Audio/video disabled** The user cannot make calls with audio and video.</span></span>
    
- <span data-ttu-id="46b8c-113">**PC 대 PC 전용** 사용자는 PC 대 PC 음성 또는 화상 통화만 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-113">**PC-to-PC only** The user can make only PC-to-PC audio or video calls.</span></span>
    
- <span data-ttu-id="46b8c-114">**Enterprise Voice** 사용자는 비즈니스용 Skype 서버 인프라를 사용하여 모든 수신 및 수신 전화를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-114">**Enterprise Voice** The user can use the Skype for Business Server infrastructure to route all incoming and outgoing calls.</span></span> <span data-ttu-id="46b8c-115">또한 사용자는 PC 대 PC 호출을 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-115">The user can also make PC-to-PC calls.</span></span>
    
- <span data-ttu-id="46b8c-116">**원격 통화 제어** 사용자는 비즈니스용 Skype 서버를 사용하여 데스크톱 전화를 제어할 수 있으며 PC 대 PC 통화도 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-116">**Remote call control** The user can use Skype for Business Server to control the desktop phone, and can also make PC-to-PC calls.</span></span>
    
<span data-ttu-id="46b8c-117">조직에 대한 전화 통신 구성에 대한 자세한 내용은 비즈니스용 [Skype](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) 서버에서 Enterprise Voice 사용자를 사용하도록 설정하고 배포 설명서에서 비즈니스용 [Skype](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) Enterprise Voice 배포를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="46b8c-117">For details about configuring telephony for an organization, see [Enable users for Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md) and [Deploy Enterprise Voice in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-enterprise-voice.md) in the Deployment documentation.</span></span>
  
1. <span data-ttu-id="46b8c-118">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="46b8c-119">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="46b8c-120">왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-120">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="46b8c-121">**사용자 검색** 상자에 원하는 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-121">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span>
    
5. <span data-ttu-id="46b8c-122">표에서 수정할 사용자 계정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-122">In the table, click the user account that you want to modify.</span></span>
    
6. <span data-ttu-id="46b8c-123">**편집** 메뉴에서 **수정** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-123">On the **Edit** menu, click **Modify**.</span></span>
    
7. <span data-ttu-id="46b8c-124">**전화 통신** 에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-124">In **Telephony**, do the following:</span></span>
    
   - <span data-ttu-id="46b8c-125">사용자에 대해 음성 및 화상 통화를 사용하지 않도록 설정하려면 **오디오/비디오 사용 안 함** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-125">To disable audio and video calls for the user, click **Audio/video disabled**.</span></span>
    
   - <span data-ttu-id="46b8c-p102">사용자에 대해 PC 대 PC 음성 통신을 사용하도록 설정하고 원격 통화 제어 또는 Enterprise Voice는 사용하도록 설정하지 않으려면 **PC 대 PC 전용** 을 클릭합니다. 사용자가 PC 대 PC 음성 통신에 사용하는 전화에 대해 **줄 URI** 의 값을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-p102">To enable PC-to-PC audio communications for the user, but not remote call control or Enterprise Voice, click **PC-to-PC only**. Specify a value for **Line URI** for the telephone that the user uses for PC-to-PC audio communications.</span></span>
    
   - <span data-ttu-id="46b8c-128">PC 대 PC 오디오 통신을 비롯한 서비스 정책 클래스에 따라 비즈니스용 Skype 인프라를 사용하여 사용자의 전화 통화를 라우팅하려면 **Enterprise Voice.**</span><span class="sxs-lookup"><span data-stu-id="46b8c-128">To route the user's phone calls by using the Skype for Business infrastructure in accordance with the class of service policy, including PC-to-PC audio communication, click **Enterprise Voice**.</span></span> <span data-ttu-id="46b8c-129">**줄 URI** 에서 Enterprise Voice의 전화 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-129">In **Line URI**, specify the telephone number for Enterprise Voice.</span></span> <span data-ttu-id="46b8c-130">**다이얼 플랜 정책** 및 **음성 정책** 에서 사용자에게 적절한 정책을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-130">In **Dial plan policy** and **Voice policy**, specify the appropriate policies for the user.</span></span> <span data-ttu-id="46b8c-131">사용자가 건 전화 번호를 E.164 형식으로 변환하는 정규화 규칙을 지정하려면 **위치 정책** 에서 적절한 위치 프로필을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-131">To specify the normalization rules for translating phone numbers dialed by the user to the E.164 format, select the appropriate location profile in **Location policy**.</span></span>
    
   - <span data-ttu-id="46b8c-132">사용자가 비즈니스용 Skype 서버에서 데스크톱 전화 줄을 제어하여 PC 대 PC 통화 및 PC 대 전화 통화를 할 수 있도록 하는 원격 통화 제어를 사용하도록 설정하려면 원격 통화 **제어를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="46b8c-132">To enable remote call control, which enables users to control their desktop phone line from Skype for Business Server to make PC-to-PC calls and PC-to-phone calls, click **Remote call control**.</span></span> <span data-ttu-id="46b8c-133">**줄 URI** 에서 원격 통화 제어에 대해 전화 번호를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-133">In **Line URI**, specify the telephone number for remote call control.</span></span> <span data-ttu-id="46b8c-134">사용자에게는 데스크톱 전화가 있어야 하며 통화 라우팅을 위한 PBX(Private Branch Exchange) 연결을 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-134">The user must have a desktop phone and private branch exchange (PBX) connection for call routing.</span></span>
    
## <a name="move-users-to-another-pool"></a><span data-ttu-id="46b8c-135">사용자를 다른 풀로 이동</span><span class="sxs-lookup"><span data-stu-id="46b8c-135">Move users to another pool</span></span>
<span data-ttu-id="46b8c-136"><a name="Move_Users"> </a></span><span class="sxs-lookup"><span data-stu-id="46b8c-136"><a name="Move_Users"> </a></span></span>

<span data-ttu-id="46b8c-137">비즈니스용 Skype 서버 제어판을 사용하여 사용자를 특정 서버 또는 풀에 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-137">You can use Skype for Business Server Control Panel to assign users to a specific server or pool.</span></span>
  
> [!TIP]
> <span data-ttu-id="46b8c-138">Lync Server 2010 또는 이전 버전이 실행되는 원본 풀에서 복잡한 Active Directory 환경의 비즈니스용 Skype 서버 대상 풀로 모든 기존 사용자를 이동하면 Active Directory 복제 속도가 느려질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-138">Moving all existing users from a source pool that is running Lync Server 2010 or earlier to a Skype for Business Server destination pool in a complex Active Directory environment might result in slower Active Directory replication.</span></span> <span data-ttu-id="46b8c-139">이러한 문제를 방지하기 위해 검색 필터를 사용하여 Lync Server 2010 이전 버전이 실행되는 풀에서 사용자를 별도로 이동하거나 비즈니스용 Skype 서버 관리 셸을 사용하여 cmdlet을 사용하여 사용자를 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-139">To avoid this, you can use search filters to move users from pools that are running Lync Server 2010 or earlier separately, or you can use Skype for Business Server Management Shell to move users with cmdlets.</span></span> <span data-ttu-id="46b8c-140">또한 필터 기능은 비즈니스용 Skype 서버 사용자와 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-140">Also, the filter functionality works with Skype for Business Server users.</span></span> 
  
### <a name="to-move-selected-users-to-a-different-server-or-pool"></a><span data-ttu-id="46b8c-141">선택한 사용자를 다른 서버 또는 풀로 이동</span><span class="sxs-lookup"><span data-stu-id="46b8c-141">To move selected users to a different server or pool</span></span>

1. <span data-ttu-id="46b8c-142">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="46b8c-143">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="46b8c-144">왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-144">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="46b8c-145">**사용자 검색** 상자에 원하는 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-145">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want, and then click **Find**.</span></span> 
    
5. <span data-ttu-id="46b8c-146">표에서 목록에서 특정 사용자 또는 사용자를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-146">In the table, select a specific user or users in the list.</span></span> 
    
6. <span data-ttu-id="46b8c-147">작업 **메뉴에서** 선택한 사용자를 **풀로 이동을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="46b8c-147">On the **Action** menu, click **Move selected users to pool**.</span></span>
    
7. <span data-ttu-id="46b8c-148">사용자 **이동에서** 대상 등록자 풀에서 사용자를 이동할 **풀을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="46b8c-148">In **Move Users**, select the pool that you want to move the users to in **Destination registrar pool**.</span></span>
    
8. <span data-ttu-id="46b8c-149">(선택 사항) 대상 서버나 풀을 사용할 수 없는 경우 **강제 적용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-149">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="46b8c-p106">**강제 적용** 을 선택하면 사용자 계정이 이동되지만 연결된 사용자 데이터가 삭제됩니다(예: 사용자가 예약한 회의). 이 확인란을 선택하지 않으면 계정 및 연결된 데이터가 둘 다 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-p106">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-all-users-from-one-server-or-pool-to-a-different-server-or-pool"></a><span data-ttu-id="46b8c-152">특정 서버나 풀의 모든 사용자를 다른 서버나 풀로 이동하려면</span><span class="sxs-lookup"><span data-stu-id="46b8c-152">To move all users from one server or pool to a different server or pool</span></span>

1. <span data-ttu-id="46b8c-153">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-153">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="46b8c-154">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="46b8c-155">왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-155">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="46b8c-156">**동작** 메뉴에서 **모든 사용자를 풀로 이동** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-156">On the **Action** menu, click **Move all users to pool**.</span></span>
    
5. <span data-ttu-id="46b8c-157">**사용자 이동** 의 **원본 등록자 풀** 에서 이동할 사용자 계정이 있는 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-157">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
6. <span data-ttu-id="46b8c-158">**대상 등록자 풀** 에서 사용자를 이동할 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-158">In **Destination registrar pool**, select the pool that you want to move the users to.</span></span>
    
7. <span data-ttu-id="46b8c-159">(선택 사항) 대상 서버나 풀을 사용할 수 없는 경우 **강제 적용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-159">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="46b8c-p107">**강제 적용** 을 선택하면 사용자 계정이 이동되지만 연결된 사용자 데이터가 삭제됩니다(예: 사용자가 예약한 회의). 이 확인란을 선택하지 않으면 계정 및 연결된 데이터가 둘 다 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-p107">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-a-different-pool-by-using-a-filter"></a><span data-ttu-id="46b8c-162">필터를 사용하여 한 풀에서 다른 풀로 사용자를 이동하려면</span><span class="sxs-lookup"><span data-stu-id="46b8c-162">To move users from one pool to a different pool by using a filter</span></span>

1. <span data-ttu-id="46b8c-163">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-163">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="46b8c-164">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="46b8c-165">왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-165">In the left navigation bar, click **Users**.</span></span>
    
4. <span data-ttu-id="46b8c-166">사용자 **검색에서** **검색을** 클릭한 다음 필터 **추가를 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="46b8c-166">In **User Search**, click **Search**, and then click **Add Filter**.</span></span>
    
5. <span data-ttu-id="46b8c-167">검색 조건에서 **등록자 풀**, **같음**, **현재 풀 FQDN** 을 차례로 선택한 후 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-167">In the Search criteria, select **Registrar Pool**, select **Equal to**, select **Current Pool FQDN**, and then click **Find**.</span></span>
    
6. <span data-ttu-id="46b8c-168">**동작** 메뉴에서 **모든 사용자를 풀로 이동** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-168">On the **Action** menu, click **Move all users to pool**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="46b8c-169">기존 사용자 집합에 필터를 적용하면 모든  사용자를 풀로 이동하는 옵션이 필터링된 사용자 하위 집합의 컨텍스트에 있습니다. </span><span class="sxs-lookup"><span data-stu-id="46b8c-169">When a filter is applied to an existing set of users, the option **Move all users to pool** is in the context of the filtered subset of users, not **all** possible users.</span></span>
  
7. <span data-ttu-id="46b8c-170">**사용자 이동** 의 **원본 등록자 풀** 에서 이동할 사용자 계정이 있는 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-170">In **Move Users**, select the pool that contains the user accounts that you want to move in **Source registrar pool**.</span></span>
    
8. <span data-ttu-id="46b8c-171">대상 **등록자 풀에서** 사용자를 이동할 풀을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-171">In **Destination registrar pool**, select the pool where you want to move the users.</span></span>
    
9. <span data-ttu-id="46b8c-172">(선택 사항) 대상 서버나 풀을 사용할 수 없는 경우 **강제 적용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-172">(Optional) If the destination server or pool is unavailable, select the **Force** check box.</span></span>
    
    > [!CAUTION]
    > <span data-ttu-id="46b8c-p108">**강제 적용** 을 선택하면 사용자 계정이 이동되지만 연결된 사용자 데이터가 삭제됩니다(예: 사용자가 예약한 회의 및 대화 상대). 이 확인란을 선택하지 않으면 계정 및 연결된 데이터가 둘 다 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-p108">If you select **Force**, the user account is moved, but any associated user data is deleted (for example, conferences that the user has scheduled and contacts). If you do not select it, both the account and the associated data are moved.</span></span> 
  
### <a name="to-move-users-from-one-pool-to-another-using-windows-powershell-cmdlets"></a><span data-ttu-id="46b8c-175">Windows Powershell cmdlet을 사용하여 풀에서 다른 풀로 사용자를 이동</span><span class="sxs-lookup"><span data-stu-id="46b8c-175">To move users from one pool to another using Windows Powershell cmdlets</span></span>

1. <span data-ttu-id="46b8c-176">로컬 또는 원격으로 Windows PowerShell 명령을 실행하는 방법에 따라 다음과 같이 올바른 비즈니스용 Skype 서버 관리 역할의 구성원으로 로그온해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-176">Depending on how you run Windows PowerShell commands (that is, locally or remotely), you need to log on as a member of the correct Skype for Business Server administrative roles as follows:</span></span>
    
   <span data-ttu-id="46b8c-177">a.</span><span class="sxs-lookup"><span data-stu-id="46b8c-177">a.</span></span> <span data-ttu-id="46b8c-178">로컬 컴퓨터에서 명령을 실행하는 경우(예: 프런트 엔드 서버에 직접 로그온): 비즈니스용 Skype 서버 관리 셸이 설치된 컴퓨터에 RTCUniversalServerAdmins 그룹의 구성원으로 또는 위임 설치 권한에 설명된 필요한 사용자 권한을 사용하여 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-178">If you are running the commands on the local machine (for example, you log on directly to a Front End Server): Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
   <span data-ttu-id="46b8c-179">b.</span><span class="sxs-lookup"><span data-stu-id="46b8c-179">b.</span></span> <span data-ttu-id="46b8c-180">다른 컴퓨터에서 원격으로 명령을 실행하는 경우(예: 컴퓨터에 로그온하고 Standard Edition 프런트 엔드 서버에서 원격으로 명령을 실행하는 경우): CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-180">If you are running the commands remotely on another computer (for example, you log on to your computer and run the commands remotely on a Standard Edition Front End Server): From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="46b8c-181">비즈니스용 Skype 서버 관리 셸 시작: **시작,** 모든 **프로그램,** 비즈니스용 **Skype,** 비즈니스용 Skype 서버 관리 셸을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="46b8c-181">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="46b8c-182">단일 사용자를 이동하려면 다음과 같이 Move-CsUser cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-182">To move single users, use the Move-CsUser cmdlet as follows:</span></span>
    
    ```PowerShell
    Move-CsUser -Identity "Pilar Ackerman" -Target "pool01.contoso.net"
    ```

    <span data-ttu-id="46b8c-183">이동할 사용자가 Pilar Ackerman인 경우 현재 할당된 홈 풀에서 풀로 이동됩니다pool01.contoso.net</span><span class="sxs-lookup"><span data-stu-id="46b8c-183">Where the user to move is the user Pilar Ackerman, and the user will be moved from their currently assigned home pool to the pool pool01.contoso.net</span></span>
    
4. <span data-ttu-id="46b8c-184">많은 수의 사용자를 이동하려면 **Get-CsUser** cmdlet과 함께 필터를 사용하고 결과 사용자 집합을 **Move-CsUser** 에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-184">To move a large number of users, use filters with the **Get-CsUser** cmdlet and pass the resulting set of users to **Move-CsUser**:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "CurrentPoolFqdn"} | Move-CsUser -Target "TargetPoolFQDN"
    ```

    <span data-ttu-id="46b8c-185">**Get-CsUser** 및 **Move-CsUser** 의 조합 명령의 결과는 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46b8c-185">The combined commands of the **Get-CsUser** and **Move-CsUser** might result in this:</span></span>
    
    ```PowerShell
    Get-CsUser -Filter {RegistrarPool -eq "pool02.contoso.net"} | Move-CsUser -Target "pool01.contoso.net"
    ```


