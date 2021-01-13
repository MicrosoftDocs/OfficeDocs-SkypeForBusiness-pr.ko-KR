---
title: 비즈니스용 Skype 서버의 사용자 계정 관리
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
ms.assetid: 2fe7e3a7-bc75-4d4b-94af-a8818722b0d3
description: 이 문서의 섹션에서는 비즈니스용 Skype 서버에서 Active Directory 사용자를 활성화, 일시적으로 사용하지 않도록 설정 또는 제거하는 방법을 설명합니다.
ms.openlocfilehash: aa1b1b21ba089815af20b61da3360179fb10935e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832778"
---
# <a name="manage-user-accounts-for-skype-for-business-server"></a><span data-ttu-id="12864-103">비즈니스용 Skype 서버의 사용자 계정 관리</span><span class="sxs-lookup"><span data-stu-id="12864-103">Manage user accounts for Skype for Business Server</span></span>

<span data-ttu-id="12864-104">이 문서의 섹션에서는 비즈니스용 Skype 서버에서 Active Directory 사용자를 활성화, 일시적으로 사용하지 않도록 설정 또는 제거하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-104">The sections in this article describe how to enable, temporarily disable, or remove Active Directory users from Skype for Business Server.</span></span>

<span data-ttu-id="12864-105">Active Directory 사용자를 사용하도록 설정하는 방법에 대한 자세한 내용은 새 사용자 계정 [만들기를 참조하십시오.](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="12864-105">For information on how to enable an Active Directory user, see [Create a New User Account](https://technet.microsoft.com/library/cc732336%28v=ws.11%29.aspx).</span></span> <span data-ttu-id="12864-106">Active Directory 사용자를 삭제하는 방법에 대한 자세한 내용은 사용자 계정 [삭제를 참조하십시오.](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="12864-106">For information on how to delete an Active Directory user, see [Delete a User Account](https://technet.microsoft.com/library/cc753730%28v=ws.11%29.aspx).</span></span>

<span data-ttu-id="12864-107">이러한 절차는 비즈니스용 Skype 사용량이 가장 낮은 유지 관리 기간 동안 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-107">These procedures should be performed during a maintenance window, when Skype for Business usage is lowest.</span></span> <span data-ttu-id="12864-108">이 수행 여부는 조직의 요구에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="12864-108">Whether this is done on a daily or weekly schedule will be determined by the needs of your organization.</span></span>

<span data-ttu-id="12864-109">이 문서에는 다음 절차가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12864-109">This article contains the following procedures:</span></span>

- [<span data-ttu-id="12864-110">한 명 이상의 사용자를 검색하려면</span><span class="sxs-lookup"><span data-stu-id="12864-110">To search for one or more users</span></span>](user-accounts.md#Search)

- [<span data-ttu-id="12864-111">새 비즈니스용 Skype 서버 사용자 추가 및 사용</span><span class="sxs-lookup"><span data-stu-id="12864-111">Add and enable a new Skype for Business Server user</span></span>](user-accounts.md#Add)

- [<span data-ttu-id="12864-112">이전에 비즈니스용 Skype 서버에 대해 사용하도록 설정된 사용자 계정을 사용하지 않도록 설정하거나 다시 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="12864-112">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>](user-accounts.md#Disable)

- [<span data-ttu-id="12864-113">사용자를 사용하지 않도록 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="12864-113">Disable a user for Enterprise Voice</span></span>](user-accounts.md#Disable_EV)

- [<span data-ttu-id="12864-114">비즈니스용 Skype 서버 관리 셸을 사용하여 사용자 계정 제거</span><span class="sxs-lookup"><span data-stu-id="12864-114">Remove a user account with the Skype for Business Server Management Shell</span></span>](user-accounts.md#Remove)

## <a name="to-search-for-one-or-more-users"></a><span data-ttu-id="12864-115">한 명 이상의 사용자를 검색하려면</span><span class="sxs-lookup"><span data-stu-id="12864-115">To search for one or more users</span></span>
<span data-ttu-id="12864-116"><a name="Search"> </a></span><span class="sxs-lookup"><span data-stu-id="12864-116"><a name="Search"> </a></span></span>

<span data-ttu-id="12864-117">검색 쿼리 결과를 사용하여 비즈니스용 Skype 서버에 대한 Active Directory 사용자를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12864-117">You can use the results of a search query to configure Active Directory users for Skype for Business Server.</span></span> <span data-ttu-id="12864-118">표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)로 사용자를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12864-118">You can search for users by display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI).</span></span>

<span data-ttu-id="12864-119">비즈니스용 Skype 서버 제어판 또는 Active Directory 사용자 및 컴퓨터 스냅인을 사용하여 사용자를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12864-119">You can search for users by using the Skype for Business Server Control Panel or the Active Directory Users and Computers snap-in.</span></span> <span data-ttu-id="12864-120">다음 절차에서는 비즈니스용 Skype 서버 제어판을 사용하여 사용자를 검색하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-120">The following procedure describes how to use Skype for Business Server Control Panel to search for users.</span></span>

> [!NOTE]
> <span data-ttu-id="12864-121">중앙 포리스트 토폴로지가 있는 환경에서는 사용자의 전자 메일 주소로 사용자를 검색할 때 검색 결과가 정확하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12864-121">In an environment with a central forest topology, search results might not be accurate when you search for a user by the user's email address.</span></span> <span data-ttu-id="12864-122">이러한 경우에는 sip:name과 같은 SIP 주소 접두사를 지정하여 사용자를 검색하거나, 검색 필터를 추가하고 전자 메일 주소의 일부분이 포함된 SIP 주소를 선택하거나, **Get-CSUser** cmdlet을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12864-122">Instead, you can search for users by specifying a SIP address prefix, for example, sip:name, add a search filter and select a SIP address that contains a partial email address, or use the **Get-CSUser** cmdlet.</span></span>

1. <span data-ttu-id="12864-123">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-123">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="12864-124">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="12864-124">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="12864-125">왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-125">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="12864-126">**사용자 검색** 상자에 검색할 사용자 계정의 표시 이름, 이름, 성, SAM 계정 이름, SIP 주소 또는 줄 URI를 모두 입력하거나 첫 부분을 입력하고 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-126">In the **Search users** box, type all or the first portion of the display name, first name, last name, SAM account name, SIP address, or line URI of the user account that you want to search for, and then click **Find**.</span></span>

5. <span data-ttu-id="12864-127">(선택 사항) 추가 검색 조건을 지정하여 결과 범위를 좁힙니다.</span><span class="sxs-lookup"><span data-stu-id="12864-127">(Optional) Specify additional search criteria to narrow the results:</span></span>

   <span data-ttu-id="12864-128">a.</span><span class="sxs-lookup"><span data-stu-id="12864-128">a.</span></span> <span data-ttu-id="12864-129">화면 오른쪽 위의 **검색 결과** 위에 있는 확장 화살표 단추를 클릭하고 **필터 추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-129">Click the expand arrow button in the upper-right corner of the screen above **Search results**, and then click **Add Filter**.</span></span>

   <span data-ttu-id="12864-130">b.</span><span class="sxs-lookup"><span data-stu-id="12864-130">b.</span></span> <span data-ttu-id="12864-131">사용자 속성을 입력하거나 드롭다운 목록의 화살표를 클릭하여 사용자 속성을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-131">Enter the user property by typing it or clicking the arrow in the drop-down list to select a user property.</span></span>

   <span data-ttu-id="12864-132">c.</span><span class="sxs-lookup"><span data-stu-id="12864-132">c.</span></span> <span data-ttu-id="12864-133">**같음** 목록에서 **같음** 또는 **같지 않음** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-133">In the **Equal to** list, click **Equal to** or **Not equal to**.</span></span>

   <span data-ttu-id="12864-134">d.</span><span class="sxs-lookup"><span data-stu-id="12864-134">d.</span></span> <span data-ttu-id="12864-135">텍스트 상자에 검색 결과를 필터링하는 데 사용할 검색 조건을 입력하고 **찾기** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-135">In the text box, type the search criteria you want to use to filter search results, and then click **Find**.</span></span>

6. <span data-ttu-id="12864-p110">**검색 결과** 아래에 검색 결과가 나타납니다. 목록에서 원하는 사용자 또는 모든 사용자를 선택하고 선택한 사용자에 대해 구성 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12864-p110">The search results appear under **Search Results**. You can select any or all of the users in the list and perform configuration tasks on the users you select.</span></span>

## <a name="add-and-enable-a-new-skype-for-business-server-user"></a><span data-ttu-id="12864-138">새 비즈니스용 Skype 서버 사용자 추가 및 사용</span><span class="sxs-lookup"><span data-stu-id="12864-138">Add and enable a new Skype for Business Server user</span></span>
<span data-ttu-id="12864-139"><a name="Add"> </a></span><span class="sxs-lookup"><span data-stu-id="12864-139"><a name="Add"> </a></span></span>

<span data-ttu-id="12864-140">Active Directory 사용자 및 컴퓨터에서 사용자 계정을 사용하도록 설정한 후 비즈니스용 Skype 서버 제어판을 사용하여 비즈니스용 Skype 서버에 Active Directory 사용자를 추가하여 새 비즈니스용 Skype 서버 사용자 계정을 만들고 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12864-140">After enabling a user account in Active Directory Users and Computers, you can use Skype for Business Server Control Panel to create and enable new Skype for Business Server user accounts by adding an Active Directory user to Skype for Business Server.</span></span>

<span data-ttu-id="12864-141">cmdlet(특히 [Enable-CsUser)을](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12864-141">You can also use a cmdlet, specifically [Enable-CsUser](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps).</span></span>

1. <span data-ttu-id="12864-142">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-142">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="12864-143">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="12864-143">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="12864-144">왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-144">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="12864-145">**사용자 사용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-145">Click **Enable users**.</span></span>

5. <span data-ttu-id="12864-146">**새 Lync Server 사용자** 대화 상자에서 **추가** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-146">On the **New Lync Server User** dialog, click **Add**.</span></span>

6. <span data-ttu-id="12864-147">**사용자 검색** 상자에 원하는 Active Directory 사용자 계정의 이름, 표시 이름, 성, SAM(보안 계정 관리자) 계정 이름, 전자 메일 주소, UPN(사용자 계정 이름) 또는 전화 번호를 모두 또는 일부분 입력하고 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-147">In the **Search users** box, type all or the first portion of the name, display name, first name, last name, Security Accounts Manager (SAM) account name, email address, User Principal Name (UPN), or phone number of the Active Directory user account that you want, and then click **Find**.</span></span>

7. <span data-ttu-id="12864-148">테이블에서 비즈니스용 Skype 서버에 추가할 계정을 선택하고 확인을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12864-148">In the table, select the account you want to add to Skype for Business Server, and then click **OK**.</span></span>

8. <span data-ttu-id="12864-149">풀에 사용자를 할당하고, 세부 정보를 추가로 지정하고, 원하는 사용자에게 정책을 할당한 후에 **사용** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-149">Assign the user to a pool, specify any additional details, and assign the policies to the user you want, and then click **Enable**.</span></span>

## <a name="disable-or-re-enable-a-user-account-previously-enabled-for-skype-for-business-server"></a><span data-ttu-id="12864-150">이전에 비즈니스용 Skype 서버에 대해 사용하도록 설정된 사용자 계정을 사용하지 않도록 설정하거나 다시 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="12864-150">Disable or re-enable a user account previously enabled for Skype for Business Server</span></span>
<span data-ttu-id="12864-151"><a name="Disable"> </a></span><span class="sxs-lookup"><span data-stu-id="12864-151"><a name="Disable"> </a></span></span>

<span data-ttu-id="12864-152">다음 절차에 따라 사용자 계정에 대해 구성한 비즈니스용 Skype 서버 설정을 잃지 않고 비즈니스용 Skype 서버에서 이전에 사용하도록 설정된 사용자 계정을 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12864-152">You can use the following procedure to disable a previously enabled user account in Skype for Business Server without losing the Skype for Business Server settings that you configured for the user account.</span></span> <span data-ttu-id="12864-153">비즈니스용 Skype 서버 사용자 계정 설정은 손실되지 않습니다. 따라서 사용자 계정을 다시 구성하지 않고도 이전에 사용하도록 설정된 사용자 계정을 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12864-153">Because you do not lose the Skype for Business Server user account settings, you can re-enable a previously enabled user account again without having to reconfigure the user account.</span></span>

1. <span data-ttu-id="12864-154">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-154">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="12864-155">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="12864-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="12864-156">왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-156">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="12864-157">**사용자 검색** 상자에 사용하지 않도록 설정하거나 다시 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫 부분을 입력하고 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-157">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="12864-158">표에서 사용하지 않도록 설정하거나 다시 사용하도록 설정할 사용자 계정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-158">In the table, click the user account that you want to disable or re-enable.</span></span>

6. <span data-ttu-id="12864-159">**동작** 메뉴에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-159">On the **Action** menu, do one of the following:</span></span>

   - <span data-ttu-id="12864-160">비즈니스용 Skype 서버의 사용자 계정을 일시적으로 사용하지 않도록 설정하려면 **Lync Server에** 대해 일시적으로 사용하지 않도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="12864-160">To temporarily disable the user account for Skype for Business Server, click **Temporarily disable for Lync Server**.</span></span>

   - <span data-ttu-id="12864-161">비즈니스용 Skype 서버의 사용자 계정을 사용하도록 설정하려면 **Lync Server에** 대해 다시 사용하도록 설정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-161">To enable the user account for Skype for Business Server, click **Re-enable for Lync Server**.</span></span>

### <a name="use-windows-powershell-to-disable-or-re-enable-user-accounts"></a><span data-ttu-id="12864-162">Windows Powershell을 사용하여 사용자 계정을 사용하지 않도록 설정하거나 다시 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="12864-162">Use Windows Powershell to Disable or Re-enable User Accounts</span></span>

<span data-ttu-id="12864-163">사용자 계정은 **Set-CsUser** cmdlet을 사용하여 일시적으로 사용하지 않도록 설정한 다음 나중에 다시 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12864-163">User accounts can be temporarily disabled, and then later re-enabled, by using the **Set-CsUser** cmdlet.</span></span> <span data-ttu-id="12864-164">이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸의 원격 세션에서 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12864-164">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="12864-165">원격 서버를 사용하여 비즈니스용 Skype Windows PowerShell 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를](https://go.microsoft.com/fwlink/p/?linkId=255876)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12864-165">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="12864-166">이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-166">The process is the same in Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account"></a><span data-ttu-id="12864-167">사용자 계정을 사용하지 않도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="12864-167">To disable a user account</span></span>

- <span data-ttu-id="12864-168">사용자 계정을 일시적으로 사용하지 않도록 설정하려면 Enabled 속성의 값을 False($False)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-168">To temporarily disable a user account, set the value of the Enabled property to False ($False).</span></span> <span data-ttu-id="12864-169">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="12864-169">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $False
  ```

### <a name="to-re-enable-a-user-account"></a><span data-ttu-id="12864-170">사용자 계정을 다시 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="12864-170">To re-enable a user account</span></span>

- <span data-ttu-id="12864-171">사용하지 않도록 설정된 사용자 계정을 다시 사용하도록 설정하려면 Enabled 속성의 값을 True($True)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-171">To re-enable a disabled user account, set the value of the Enabled property to True ($True).</span></span> <span data-ttu-id="12864-172">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="12864-172">For example:</span></span>

  ```PowerShell
  Set-CsUser -Identity "Ken Myer" -Enabled $True
  ```

<span data-ttu-id="12864-173">자세한 내용은 [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="12864-173">For more information, see the help topic for the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="disable-a-user-for-enterprise-voice"></a><span data-ttu-id="12864-174">사용자를 사용하지 않도록 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="12864-174">Disable a user for Enterprise Voice</span></span>
<span data-ttu-id="12864-175"><a name="Disable_EV"> </a></span><span class="sxs-lookup"><span data-stu-id="12864-175"><a name="Disable_EV"> </a></span></span>

<span data-ttu-id="12864-176">다음 절차에 따라 비즈니스용 Skype Enterprise Voice 계정의 계정을 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-176">Use the following procedure to disable Enterprise Voice for a user account that is enabled for Skype for Business Server.</span></span>

### <a name="to-disable-a-user-account-for-enterprise-voice"></a><span data-ttu-id="12864-177">사용자 계정을 사용하지 않도록 설정하려면 Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="12864-177">To disable a user account for Enterprise Voice</span></span>

1. <span data-ttu-id="12864-178">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-178">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="12864-179">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="12864-179">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="12864-180">왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-180">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="12864-181">**사용자 검색** 상자에 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫부분을 입력하고 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-181">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to enable, and then click **Find**.</span></span>

5. <span data-ttu-id="12864-182">표에서 사용자 계정에서 사용하도록 설정할 사용자 계정을 Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="12864-182">In the table, click the user account that you want to enable for Enterprise Voice.</span></span>

6. <span data-ttu-id="12864-183">**편집** 메뉴에서 **세부 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-183">On the **Edit** menu, click **Show details**.</span></span>

7. <span data-ttu-id="12864-184">**Lync Server 사용자 편집** 페이지의 **전화 통신** 아래에서 **Enterprise Voice** 를 제외한 아무 옵션이나 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-184">On the **Edit Lync Server User** page, under **Telephony**, click any option except **Enterprise Voice**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="12864-185">사용자가 Lync를 사용하여 오디오 또는 화상 통화를 하지 않도록 제한하려면 전화 통신에서 오디오/비디오 사용 안 **을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="12864-185">To restrict a user from making audio or video calls by using Lync, under **Telephony**, click **Audio/video disabled**.</span></span>

8. <span data-ttu-id="12864-186">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-186">Click **Commit**.</span></span>

<span data-ttu-id="12864-187">이제 사용자가 사용자 Enterprise Voice 없습니다.</span><span class="sxs-lookup"><span data-stu-id="12864-187">The user is now unable to use the Enterprise Voice feature.</span></span> <span data-ttu-id="12864-188">관련 정보:</span><span class="sxs-lookup"><span data-stu-id="12864-188">Related information:</span></span> <br/>[<span data-ttu-id="12864-189">Enterprise Voice 및 모바일</span><span class="sxs-lookup"><span data-stu-id="12864-189">Enterprise Voice and mobility</span></span>](https://technet.microsoft.com/library/72cbe2f5-1a01-4a6f-84a5-01f3212a8992.aspx)<br/> [<span data-ttu-id="12864-190">사용자가 비즈니스용 Skype Enterprise Voice 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="12864-190">Enable users for Enterprise Voice in Skype for Business Server</span></span>](../../deploy/deploy-enterprise-voice/enable-users-for-enterprise-voice.md)<br/> [<span data-ttu-id="12864-191">비즈니스용 Skype 서버 관리 쉘</span><span class="sxs-lookup"><span data-stu-id="12864-191">Skype for Business Server Management Shell</span></span>](../management-shell.md)
## <a name="remove-a-user-account-with-the-skype-for-business-server-management-shell"></a><span data-ttu-id="12864-192">비즈니스용 Skype 서버 관리 셸을 사용하여 사용자 계정 제거</span><span class="sxs-lookup"><span data-stu-id="12864-192">Remove a user account with the Skype for Business Server Management Shell</span></span>
<span data-ttu-id="12864-193"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="12864-193"><a name="Remove"> </a></span></span>

<span data-ttu-id="12864-194">다음 절차에 따라 비즈니스용 Skype 서버에서 이전에 추가한 사용자 계정을 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12864-194">You can use the following procedure to remove a previously added user account in Skype for Business Server.</span></span>

> [!NOTE]
> <span data-ttu-id="12864-195">사용자를 제거하면 사용자 계정에 대해 구성한 모든 설정이 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="12864-195">Removing a user will cause you to lose any settings you configured for the user account.</span></span> <span data-ttu-id="12864-196">대신 사용자 계정을 일시적으로 사용하지 않도록 설정하려면 이전에 비즈니스용 Skype 서버에 대해 사용하도록 설정된 사용자 계정 사용 안 하도록 설정 또는 다시 활성화를 [참조하세요.](user-accounts.md#Disable)</span><span class="sxs-lookup"><span data-stu-id="12864-196">If you would like to temporarily disable a user account instead, see [Disable or re-enable a user account previously enabled for Skype for Business Server](user-accounts.md#Disable).</span></span>

1. <span data-ttu-id="12864-197">CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-197">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="12864-198">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="12864-198">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="12864-199">왼쪽 탐색 모음에서 **사용자** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-199">In the left navigation bar, click **Users**.</span></span>

4. <span data-ttu-id="12864-200">**사용자 검색** 상자에 사용하지 않도록 설정하거나 다시 사용하도록 설정할 사용자 계정의 표시 이름, 이름, 성, SAM(보안 계정 관리자) 계정 이름, SIP 주소 또는 줄 URI(Uniform Resource Identifier)를 모두 또는 첫 부분을 입력하고 **찾기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-200">In the **Search users** box, type all or the first portion of the display name, first name, last name, Security Accounts Manager (SAM) account name, SIP address, or line Uniform Resource Identifier (URI) of the user account that you want to disable or re-enable, and then click **Find**.</span></span>

5. <span data-ttu-id="12864-201">표에서 제거할 사용자 계정을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-201">In the table, click the user account that you want to remove.</span></span>

6. <span data-ttu-id="12864-202">**동작** 메뉴에서 **Lync Server에서 제거** 를 선택하면 대화 상자가 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="12864-202">On the **Action** menu, select **Remove from Lync Server**, and a dialog box appears.</span></span>

7. <span data-ttu-id="12864-203">대화 상자에서 **확인** 을 선택하여 사용자를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-203">From the dialog box, select **OK** to remove the user.</span></span>

### <a name="remove-user-accounts-with-windows-powershell-cmdlets"></a><span data-ttu-id="12864-204">Windows Powershell cmdlet을 사용하여 사용자 계정 제거</span><span class="sxs-lookup"><span data-stu-id="12864-204">Remove user accounts with Windows Powershell cmdlets</span></span>

<span data-ttu-id="12864-205">이 cmdlet을 사용하여 사용자 계정을 제거할 Disable-CsUser 있습니다.</span><span class="sxs-lookup"><span data-stu-id="12864-205">You can remove user accounts by using the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="12864-206">이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 원격 세션 셸에서 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="12864-206">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session Windows PowerShell.</span></span> <span data-ttu-id="12864-207">원격 서버를 사용하여 비즈니스용 Skype Windows PowerShell 연결하는 데 대한 자세한 내용은 [블로그 문서 "빠른 시작: 원격 PowerShell을 사용하여 Microsoft Lync Server 2010 관리"를](https://go.microsoft.com/fwlink/p/?linkId=255876)참조하세요.</span><span class="sxs-lookup"><span data-stu-id="12864-207">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="12864-208">이 프로세스는 비즈니스용 Skype 서버에서 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-208">The process is the same in Skype for Business Server.</span></span>

### <a name="to-remove-a-user-account"></a><span data-ttu-id="12864-209">사용자 계정을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="12864-209">To remove a user account</span></span>
<span data-ttu-id="12864-210">사용자 계정을 제거하려면 Disable-CsUser cmdlet을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="12864-210">To remove a user account, use the Disable-CsUser cmdlet.</span></span> <span data-ttu-id="12864-211">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="12864-211">For example:</span></span>

  ```PowerShell
  Disable-CsUser -Identity "Ken Myer"
  ```

    After this command has run there is no way to re-enable the account and its previous settings. Instead, you will need to use the Enable-CsUser cmdlet to create a brand-new account for Ken Myer.

<span data-ttu-id="12864-212">자세한 내용은 [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet에 대한 도움말 항목을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="12864-212">For more information, see the help topic for the [Disable-CsUser](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps) cmdlet.</span></span>

## <a name="see-also"></a><span data-ttu-id="12864-213">참고 항목</span><span class="sxs-lookup"><span data-stu-id="12864-213">See also</span></span>
<span data-ttu-id="12864-214"><a name="Remove"> </a></span><span class="sxs-lookup"><span data-stu-id="12864-214"><a name="Remove"> </a></span></span>

[<span data-ttu-id="12864-215">Enable-CsUser</span><span class="sxs-lookup"><span data-stu-id="12864-215">Enable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/enable-csuser?view=skype-ps)

[<span data-ttu-id="12864-216">Disable-CsUser</span><span class="sxs-lookup"><span data-stu-id="12864-216">Disable-CsUser</span></span>](https://docs.microsoft.com/powershell/module/skype/disable-csuser?view=skype-ps)
