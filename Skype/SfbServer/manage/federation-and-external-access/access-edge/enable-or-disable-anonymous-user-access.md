---
title: 익명의 사용자 액세스를 사용하도록 설정 또는 해제
ms.reviewer: ''
ms:assetid: f10c19e6-b6f9-4d26-9923-0165f36e4af8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619192(v=OCS.15)
ms:contentKeyID: 49733872
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: ''
ms.openlocfilehash: 7e828745810bd49f9b8f3ea9e7bee1d023e4fc67
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817448"
---
# <a name="enable-or-disable-anonymous-user-access-in-skype-for-business-server"></a><span data-ttu-id="1cc64-102">비즈니스용 Skype 서버에서 익명 사용자 액세스 사용 또는 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="1cc64-102">Enable or disable anonymous user access in Skype for Business Server</span></span>

<span data-ttu-id="1cc64-103">익명 사용자는 조직의 Active Directory 도메인 서비스 또는 지원되는 페더타 도메인에 사용자 계정이 없는 사용자이지만, 원격으로 조직 내 회의에 참가하도록 초대할 수 있는 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="1cc64-103">Anonymous users are users who do not have a user account in your organization's Active Directory Domain Services or in a supported federated domain, but can be invited to participate remotely in an on-premises conference.</span></span> <span data-ttu-id="1cc64-104">모임에 익명 참가를 허용하면 익명 사용자(즉, 모임 또는 회의 키를 통해서만 ID가 확인된 사용자)가 모임에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cc64-104">By allowing anonymous participation in meetings you enable anonymous users (that is, users whose identity is verified through the meeting or conference key only) to join meetings.</span></span> <span data-ttu-id="1cc64-105">익명 참가를 허용하려면 조직에서 익명 참가를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc64-105">Allowing anonymous participation requires enabling it for your organization.</span></span>

<span data-ttu-id="1cc64-106">나중에 익명 사용자의 액세스를 일시적으로 또는 영구적으로 차단하려는 경우 조직에서 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cc64-106">If you later want to temporarily or permanently prevent access by anonymous users, you can disable it for your organization.</span></span> <span data-ttu-id="1cc64-107">이 섹션의 절차에 따라 조직에 대한 익명 사용자 액세스를 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cc64-107">Use the procedure in this section to enable or disable anonymous user access for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="1cc64-108">조직에 대해 익명 사용자 액세스를 사용하도록 설정하면 액세스 에지 서비스를 실행하는 서버가 익명 사용자의 액세스를 지원하도록 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc64-108">By enabling anonymous user access for your organization you are only specifying that your servers running the Access Edge service support access by anonymous users.</span></span> <span data-ttu-id="1cc64-109">또한 하나 이상의 회의 정책을 구성하고 하나 이상의 사용자 또는 사용자 그룹에 적용할 때까지는 익명 사용자가 조직의 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1cc64-109">Anonymous users cannot participate in any meetings in your organization until you also configure at least one conferencing policy and apply it to one or more users or user groups.</span></span> <span data-ttu-id="1cc64-110">익명 사용자를 모임에 초대할 수 있는 사용자는 익명 사용자를 지원하도록 구성된 회의 정책이 할당된 사용자뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="1cc64-110">The only users that can invite anonymous users to meetings are those users that are assigned a conferencing policy that is configured to support anonymous users.</span></span> <span data-ttu-id="1cc64-111">익명 사용자 선택을 지원하기 위해 회의 정책을 구성하는 데 대한 자세한 내용은 회의 정책 관리를 [참조합니다.](../../conferencing/conferencing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="1cc64-111">For details about configuring conferencing policies to support inviting anonymous users, see [Manage conferencing policies](../../conferencing/conferencing-policies.md).</span></span>

## <a name="to-enable-or-disable-anonymous-user-access-for-your-organization"></a><span data-ttu-id="1cc64-112">조직에 대해 익명 사용자 액세스를 사용하도록 설정하거나 사용하지 않도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="1cc64-112">To enable or disable anonymous user access for your organization</span></span>

1.  <span data-ttu-id="1cc64-113">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc64-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1cc64-114">브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="1cc64-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1cc64-115">왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭하고 **액세스 에지 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc64-115">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="1cc64-116">**액세스 에지 구성** 페이지에서 **전역** 을 클릭하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc64-116">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1cc64-117">**액세스 에지 구성 편집** 에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc64-117">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="1cc64-118">조직에서 익명 사용자 액세스를 사용하도록  설정하려면 익명 사용자와의 통신 사용 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc64-118">To enable anonymous user access for your organization, select the **Enable communications with anonymous users** check box.</span></span>
    
      - <span data-ttu-id="1cc64-119">조직에 대한 익명 사용자 액세스를 사용하지 않도록 설정하려면 익명 사용자와의 통신 사용 확인란의 **선택을** 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc64-119">To disable anonymous user access for your organization, clear the **Enable communications with anonymous users** check box.</span></span>

6.  <span data-ttu-id="1cc64-120">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1cc64-120">Click **Commit**.</span></span>


## <a name="enabling-or-disabling-anonymous-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1cc64-121">cmdlet을 사용하여 익명 사용자 액세스 Windows PowerShell 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="1cc64-121">Enabling or disabling anonymous user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="1cc64-122">**Set-CsAccessEdgeConfiguration** cmdlet과 Windows PowerShell 익명 사용자 액세스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1cc64-122">You can manage anonymous user access by using Windows PowerShell and the **Set-CsAccessEdgeConfiguration** cmdlet.</span></span> <span data-ttu-id="1cc64-123">이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸의 원격 세션에서 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1cc64-123">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-anonymous-user-access"></a><span data-ttu-id="1cc64-124">익명 사용자 액세스를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="1cc64-124">To enable anonymous user access</span></span>

  - <span data-ttu-id="1cc64-125">익명 사용자 액세스를 사용하도록 설정하려면 **AllowAnonymousUsers** 속성 값을 True($True)</span><span class="sxs-lookup"><span data-stu-id="1cc64-125">To enable anonymous user access, set the value of the **AllowAnonymousUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $True

## <a name="to-disable-anonymous-user-access"></a><span data-ttu-id="1cc64-126">익명 사용자 액세스를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="1cc64-126">To disable anonymous user access</span></span>

  - <span data-ttu-id="1cc64-127">익명 사용자 액세스를 사용하지 않도록 설정하기 위해 **AllowAnonymousUsers** 속성 값을 False($False)</span><span class="sxs-lookup"><span data-stu-id="1cc64-127">To disable anonymous user access, set the value of the **AllowAnonymousUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowAnonymousUsers $False


## <a name="see-also"></a><span data-ttu-id="1cc64-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1cc64-128">See Also</span></span>

[<span data-ttu-id="1cc64-129">Set-CsClientPolicy</span><span class="sxs-lookup"><span data-stu-id="1cc64-129">Set-CsClientPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy?view=skype-ps)  
  
