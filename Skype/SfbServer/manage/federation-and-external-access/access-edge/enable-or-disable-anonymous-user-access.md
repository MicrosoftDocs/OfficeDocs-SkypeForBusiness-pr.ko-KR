---
title: 익명 사용자 액세스 사용 또는 사용 안 함
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 40b365f25abccc05a5eb5156e1c7d79106a7537c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818409"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="10720-102">비즈니스용 Skype 서버에서 익명 사용자 액세스 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="10720-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="10720-103">익명 사용자는 조직의 Active Directory 도메인 서비스 또는 지원 되는 페더레이션 도메인에 사용자 계정이 없지만 온-프레미스 회의에 원격으로 참여 하도록 초대 받을 수 있는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="10720-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="10720-104">모임에서 익명 참가를 허용 하면 익명 사용자 (즉, 모임 또는 회의 키를 통해 id를 확인 하는 사용자)가 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10720-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="10720-105">익명 참가를 허용 하려면 조직에 대해 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10720-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="10720-106">나중에 익명 사용자의 액세스를 일시적으로 또는 영구적으로 방지 하려면 조직에 맞게 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10720-106">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="10720-107">이 섹션의 절차를 사용 하 여 조직에 대 한 익명 사용자 액세스를 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="10720-107">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="10720-108">조직에 대 한 익명 사용자 액세스를 사용 하도록 설정 하면 액세스에 지 서비스를 실행 하는 서버에서 익명 사용자의 액세스를 지원 하도록 지정할 수만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10720-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="10720-109">익명 사용자는 하나 이상의 회의 정책을 구성 하 고 하나 이상의 사용자 또는 사용자 그룹에 적용할 때까지 조직의 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="10720-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="10720-110">익명 사용자를 모임에 초대할 수 있는 유일한 사용자는 익명 사용자를 지원 하도록 구성 된 회의 정책이 할당 된 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="10720-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="10720-111">익명 사용자 초대를 지원 하도록 회의 정책을 구성 하는 방법에 대 한 자세한 내용은 [회의 정책 관리](../../conferencing/conferencing-policies.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="10720-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="10720-112">조직에 대 한 익명 사용자 액세스를 사용 하거나 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="10720-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="10720-113">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="10720-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="10720-114">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="10720-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="10720-115">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 한 다음 **액세스 경계 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="10720-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="10720-116">**액세스 경계 구성** 페이지에서 **전역**을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="10720-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="10720-117">**액세스에 지 구성 편집**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="10720-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="10720-118">조직에서 익명 사용자 액세스를 사용 하도록 설정 하려면 **익명 사용자와 통신 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="10720-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="10720-119">조직에서 익명 사용자 액세스를 사용 하지 않도록 설정 하려면 **익명 사용자와 통신 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="10720-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="10720-120">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="10720-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="10720-121">Windows PowerShell cmdlet을 사용 하 여 익명 사용자 액세스 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="10720-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="10720-122">Windows PowerShell 및 **Set-CsAccessEdgeConfiguration** cmdlet을 사용 하 여 익명 사용자 액세스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10720-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="10720-123">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10720-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="10720-124">익명 사용자 액세스를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="10720-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="10720-125">익명 사용자 액세스를 사용 하도록 설정 하려면 **AllowAnonymousUsers** 속성 값을 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="10720-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="10720-126">익명 사용자 액세스를 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="10720-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="10720-127">익명 사용자 액세스를 사용 하지 않도록 설정 하려면 **AllowAnonymousUsers** 속성 값을 False ($False)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="10720-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="10720-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="10720-128">See Also</span></span>

[<span data-ttu-id="10720-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="10720-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
