---
title: 익명 사용자 지원을 위한 회의 정책 할당
ms.reviewer: ''
ms:assetid: 662de022-1111-40f7-bad4-f2b686f30973
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521007(v=OCS.15)
ms:contentKeyID: 48184333
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
description: 익명 사용자를 지원 하도록 회의 정책을 구성 하 고 특정 사용자에 게 해당 회의 정책을 적용 하 여 익명 사용자를 초대할 수 있는 사용자를 제어 합니다.
ms.openlocfilehash: b5427ec96d3593cf87656f562acf0afc183b92d6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818419"
---
# <a name="assign-conferencing-policies-to-support-anonymous-users-in-skype-for-business-server"></a><span data-ttu-id="b190d-103">비즈니스용 Skype 서버에서 익명 사용자를 지원 하도록 회의 정책 할당</span><span class="sxs-lookup"><span data-stu-id="b190d-103">Assign conferencing policies to support anonymous users in Skype for Business Server</span></span> 


<span data-ttu-id="b190d-104">기본적으로 모든 사용자는 익명 사용자를 초대 하 여 모임에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b190d-104">By default, all users are prevented from inviting anonymous users to participate in a meeting.</span></span> <span data-ttu-id="b190d-105">익명 사용자를 지원 하도록 회의 정책을 구성 하 고 특정 사용자에 게 해당 회의 정책을 적용 하 여 익명 사용자를 초대할 수 있는 사용자를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="b190d-105">You control who can invite anonymous users by configuring a conferencing policy to support anonymous users, and applying that conferencing policy to specific users.</span></span> <span data-ttu-id="b190d-106">익명 사용자를 지원 하도록 회의 정책을 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버에서 회의 정책 만들기](../../conferencing/create-policies.md) 및 비즈니스용 skype server에 대 한 [페더레이션 및 외부 액세스 관리](../managing-federation-and-external-access.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b190d-106">For details about how to configure a conferencing policies to support anonymous users, see [Create conferencing policies in Skype for Business Server](../../conferencing/create-policies.md) and [Managing federation and external access to Skype for Business Server](../managing-federation-and-external-access.md).</span></span>

<span data-ttu-id="b190d-107">이 섹션의 절차를 사용 하 여 이미 만든 회의 정책을 하나 이상의 사용자 또는 사용자 그룹에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b190d-107">Use the procedure in this section to apply a conferencing policy that you have already created to one or more users or user groups.</span></span>

> [!NOTE]  
> <span data-ttu-id="b190d-108">사용자가 익명 사용자를 초대할 수 있도록 하는 정책을 구성 하 고 적용 하는 것 외에도 조직의 익명 사용자에 대 한 지원을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b190d-108">In addition to configuring and applying a policy to enable users to invite anonymous users, you must also enable support for anonymous users for your organization.</span></span> <span data-ttu-id="b190d-109">자세한 내용은 [비즈니스용 Skype 서버에서 공용 사용자 액세스를 제어 하는 정책 구성을](../external-access-policies/configure-policies-to-control-public-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b190d-109">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>


## <a name="to-configure-a-user-policy-for-anonymous-participation-in-meetings"></a><span data-ttu-id="b190d-110">모임에서 익명 참가에 대 한 사용자 정책을 구성 하려면</span><span class="sxs-lookup"><span data-stu-id="b190d-110">To configure a user policy for anonymous participation in meetings</span></span>

1.  <span data-ttu-id="b190d-111">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b190d-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b190d-112">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b190d-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="b190d-113">왼쪽 탐색 모음에서 **회의**를 클릭 하 고 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b190d-113">In the left navigation bar, click **Conferencing**, and then do one of the following:</span></span>
    
    1.  <span data-ttu-id="b190d-114">새 사용자 정책을 만들려면 **새로 만들기**를 클릭 한 다음 **사용자 정책을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b190d-114">To create a new user policy, click **New**, and then click **User policy**.</span></span> <span data-ttu-id="b190d-115">사용자 정책이 어떤 역할을 하는지 나타내는 **이름** 필드에 고유한 이름을 만듭니다 (예: 익명 사용자와의 통신을 가능 하 게 하는 사용자 정책에 **익명** 허용).</span><span class="sxs-lookup"><span data-stu-id="b190d-115">Create a unique name in the **Name** field that indicates what the user policy covers (for example, **EnableAnonymous** for a user policy that enables communications with anonymous users).</span></span>
    
    2.  <span data-ttu-id="b190d-116">기존 사용자 정책을 구성 하려면 표에 나열 된 적절 한 정책을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b190d-116">To configure an existing user policy, click the appropriate policy listed in the table, click **Edit**, and then click **Show details**.</span></span>

4.  <span data-ttu-id="b190d-117">**회의 정책** 대화 상자에서 **참가자가 익명 사용자 초대를 허용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b190d-117">In the **Conferencing Policies** dialog box, select the **Allow participants to invite anonymous users** check box.</span></span>

5.  <span data-ttu-id="b190d-118">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b190d-118">Click **Commit**.</span></span>

6.  <span data-ttu-id="b190d-119">왼쪽 탐색 모음에서 **사용자**를 클릭 하 고 구성 하려는 사용자 계정에서 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="b190d-119">In the left navigation bar, click **Users**, search on the user account that you want to configure.</span></span>

7.  <span data-ttu-id="b190d-120">검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b190d-120">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

8.  <span data-ttu-id="b190d-121">**회의 정책**에서 **비즈니스용 Skype 서버 사용자 편집** 에서이 사용자에 게 적용 하려는 익명 사용자 액세스 구성이 있는 사용자 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b190d-121">In **Edit Skype for Business Server User** under **Conferencing policy**, select the user policy with the anonymous user access configuration that you want to apply to this user.</span></span>  

    > [!NOTE]  
    > <span data-ttu-id="b190d-122">자동 설정은 기본 서버 설치 설정을 적용 하 고 서버에 의해 자동으로 적용 됩니다. <STRONG> &lt;&gt; </STRONG></span><span class="sxs-lookup"><span data-stu-id="b190d-122">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings and are applied automatically by the server.</span></span>


<span data-ttu-id="b190d-123">사용자가 회의에 익명 사용자를 초대할 수 있도록 하려면 조직의 익명 사용자에 대 한 지원도 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b190d-123">To enable users to invite anonymous users to conferences, you must also enable support for anonymous users in your organization.</span></span> <span data-ttu-id="b190d-124">자세한 내용은 [비즈니스용 Skype 서버에서 공용 사용자 액세스를 제어 하는 정책 구성을](../external-access-policies/configure-policies-to-control-public-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b190d-124">For details, see [Configure policies to control public user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-public-user-access.md).</span></span>

