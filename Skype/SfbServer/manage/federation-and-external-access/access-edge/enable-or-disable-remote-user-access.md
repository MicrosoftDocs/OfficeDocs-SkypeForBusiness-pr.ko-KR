---
title: 원격 사용자 액세스 사용 또는 사용 안 함
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 원격 사용자에 대 한 원격 사용자 액세스를 사용 하도록 설정 하면 지원 되는 원격 사용자가 인터넷을 통해 연결 되며 비즈니스용 Skype 서버를 사용 하 여 내부 사용자와 공동 작업 하기 위해 VPN을 사용 하 여 연결할 필요가 없습니다.
ms.openlocfilehash: dde2bbb2d71d84bc9102683afc37208e3c4616bd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2019
ms.locfileid: "36188868"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="03001-103">비즈니스용 Skype 서버에서 원격 사용자 액세스 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="03001-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="03001-104">원격 사용자는 조직 내에서 영구 Active Directory id를 보유 하 고 있는 조직의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="03001-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="03001-105">원격 사용자는 조직의 네트워크에 연결 되어 있지 않은 경우 VPN (가상 사설망)을 사용 하 여 네트워크 외부에서 비즈니스용 Skype 서버에 로그인 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="03001-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="03001-106">원격 사용자에 게 가정에서 근무 하는 직원이 나 이동 중에도 엔터프라이즈 자격 증명을 부여 받은 신뢰할 수 있는 공급 업체와 같은 기타 원격 작업자를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="03001-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="03001-107">원격 사용자에 대 한 원격 사용자 액세스를 사용 하도록 설정 하면 지원 되는 원격 사용자가 인터넷을 통해 연결 되며 비즈니스용 Skype 서버를 사용 하 여 내부 사용자와 공동 작업 하기 위해 VPN을 사용 하 여 연결할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="03001-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="03001-108">원격 사용자 액세스를 지원 하려면 원격 사용자 액세스를 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03001-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="03001-109">원격 사용자 액세스를 사용 하도록 설정 하면 전체 조직에 대해 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="03001-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="03001-110">나중에 일시적으로 또는 영구적으로 원격 사용자 액세스를 방지 하려면 조직에 맞게 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03001-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="03001-111">이 섹션의 절차를 사용 하 여 조직에 대 한 원격 사용자 액세스를 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="03001-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="03001-112">원격 사용자 액세스를 사용 하도록 설정 하면 액세스에 지 서비스를 실행 하는 서버에서 원격 사용자와의 통신을 지원 하지만 원격 사용자가 조직에서 인스턴트 메시징 (IM) 이나 회의에 참가할 수 없는 경우에만 구성 됩니다. 원격 사용자 액세스 사용을 관리 하는 하나 이상의 정책.</span><span class="sxs-lookup"><span data-stu-id="03001-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="03001-113">한 정책 수준에서 적용 되는 비즈니스용 Skype 서버 정책 설정은 다른 정책 수준에서 적용 된 설정을 무시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03001-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="03001-114">비즈니스용 Skype 서버 정책 우선 순위: 사용자 정책 (대부분의 영향을 주지 않음)이 사이트 정책을 무시 하 고 사이트 정책이 전역 정책에 우선 합니다 (최소 영향).</span><span class="sxs-lookup"><span data-stu-id="03001-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="03001-115">즉 정책 설정이 정책에 영향을 미치는 개체에 대 한 자세한 내용은 개체에 더 많은 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="03001-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="03001-116">원격 사용자 액세스 사용에 대 한 정책을 구성 하는 방법에 대 한 자세한 내용은 비즈니스용 [Skype 서버의 원격 사용자 액세스 제어 정책 구성을](../external-access-policies/configure-policies-to-control-remote-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03001-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="03001-117">조직의 원격 사용자 액세스를 사용 하거나 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="03001-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="03001-118">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="03001-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="03001-119">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="03001-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="03001-120">왼쪽 탐색 모음에서 **페더레이션 및 외부 액세스**를 클릭 한 다음 **액세스 경계 구성을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03001-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="03001-121">**액세스 경계 구성** 페이지에서 **전역**을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="03001-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="03001-122">**액세스에 지 구성 편집**에서 다음 중 하나를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="03001-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="03001-123">조직의 원격 사용자 액세스를 사용 하도록 설정 하려면 **원격 사용자 액세스 사용** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="03001-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="03001-124">조직의 원격 사용자 액세스를 사용 하지 않도록 설정 하려면 **원격 사용자 액세스 사용** 확인란의 선택을 취소 합니다.</span><span class="sxs-lookup"><span data-stu-id="03001-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="03001-125">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="03001-125">Click **Commit**.</span></span>

<span data-ttu-id="03001-126">원격 사용자가 비즈니스용 Skype Server를 실행 하는 서버에 로그인 할 수 있도록 하려면 하나 이상의 외부 액세스 정책을 구성 하 여 원격 사용자 액세스를 지원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="03001-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="03001-127">자세한 내용은 [비즈니스용 Skype 서버에서 원격 사용자 액세스를 제어 하도록 정책 구성을](../external-access-policies/configure-policies-to-control-remote-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="03001-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="03001-128">Windows PowerShell cmdlet을 사용 하 여 원격 사용자 액세스 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="03001-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="03001-129">Windows PowerShell 및 CsAccessEdgeConfiguration cmdlet을 사용 하 여 원격 사용자 액세스를 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03001-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="03001-130">이 cmdlet은 비즈니스용 Skype 서버 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="03001-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="03001-131">원격 사용자 액세스를 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="03001-131">To enable remote user access</span></span>

  - <span data-ttu-id="03001-132">원격 사용자 액세스를 사용 하도록 설정 하려면 **Allowout 사용자** 속성 값을 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03001-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="03001-133">원격 사용자 액세스를 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="03001-133">To disable remote user access</span></span>

  - <span data-ttu-id="03001-134">원격 사용자 액세스를 사용 하지 않도록 설정 하려면 **Allowout함 사용자** 속성 값을 False ($False)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="03001-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


