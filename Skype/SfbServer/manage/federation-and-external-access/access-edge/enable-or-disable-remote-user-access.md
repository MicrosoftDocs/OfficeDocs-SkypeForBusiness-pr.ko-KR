---
title: 원격 사용자 액세스를 사용하도록 설정 또는 해제
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
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
description: 원격 사용자에 대해 원격 사용자 액세스를 사용하도록 설정하는 경우 지원되는 원격 사용자는 인터넷을 통해 연결하며, 비즈니스용 Skype 서버를 사용하여 내부 사용자와 공동 작업을 하기 위해 VPN을 사용하여 연결할 필요는 없습니다.
ms.openlocfilehash: 9e5ba5828e129c6fed5dd892b1a7bb8e6bd64707
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817398"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a><span data-ttu-id="71632-103">비즈니스용 Skype 서버에서 원격 사용자 액세스를 사용 또는 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="71632-103">Enable or disable remote user access in Skype for Business Server</span></span>

<span data-ttu-id="71632-104">원격 사용자는 조직 내에서 영구 Active Directory ID를 가지는 조직의 사용자입니다.</span><span class="sxs-lookup"><span data-stu-id="71632-104">Remote users are users in your organization who have a persistent Active Directory identity within the organization.</span></span> <span data-ttu-id="71632-105">원격 사용자는 조직의 네트워크에 연결되지 않은 경우 VPN(가상 사설망)을 사용하여 네트워크 외부에서 비즈니스용 Skype 서버에 로그인하는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71632-105">Remote users often sign in to Skype for Business Server from outside your network by using a virtual private network (VPN) when they are not connected to your organization’s network.</span></span> <span data-ttu-id="71632-106">원격 사용자에는 회사 자격 증명이 부여된 신뢰할 수 있는 공급업체와 같은 집이나 외근에 근무하는 직원과 기타 원격 작업자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="71632-106">Remote users include employees working at home or on the road and other remote workers, such as trusted vendors, who have been granted enterprise credentials.</span></span> <span data-ttu-id="71632-107">원격 사용자에 대해 원격 사용자 액세스를 사용하도록 설정하는 경우 지원되는 원격 사용자는 인터넷을 통해 연결하며, 비즈니스용 Skype 서버를 사용하여 내부 사용자와 공동 작업을 하기 위해 VPN을 사용하여 연결할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71632-107">If you enable remote user access for remote users, supported remote users connect over the Internet and do not have to connect using a VPN in order to collaborate with internal users using Skype for Business Server.</span></span>

<span data-ttu-id="71632-108">원격 사용자 액세스를 지원하려면 원격 사용자 액세스를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71632-108">To support remote user access, you must enable remote user access.</span></span> <span data-ttu-id="71632-109">원격 사용자 액세스를 사용하도록 설정하면 전체 조직에 대해 원격 사용자 액세스를 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71632-109">When you enable remote user access, you enable it for your entire organization.</span></span> <span data-ttu-id="71632-110">나중에 원격 사용자 액세스를 일시적으로 또는 영구적으로 차단하려는 경우 조직에서 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71632-110">If you later want to temporarily or permanently prevent remote user access, you can disable it for your organization.</span></span> <span data-ttu-id="71632-111">이 섹션의 절차에 따라 조직에 대한 원격 사용자 액세스를 사용하도록 설정하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71632-111">Use the procedure in this section to enable or disable remote user access for your organization.</span></span>


> [!NOTE]  
> <span data-ttu-id="71632-112">원격 사용자 액세스를 사용하도록 설정하는 것은 액세스 에지 서비스를 실행하는 서버가 원격 사용자와의 통신을 지원하도록 지정하기만 하지만 원격 사용자는 원격 사용자 액세스 사용을 관리하기 위한 정책도 하나 이상 구성할 때까지 조직의 IM(인스턴트 메시징) 또는 회의에 참가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="71632-112">Enabling remote user access only specifies that your servers running the Access Edge service support communications with remote users, but remote users cannot participate in instant messaging (IM) or conferences in your organization until you also configure at least one policy to manage the use of remote user access.</span></span> <span data-ttu-id="71632-113">한 정책 수준에서 적용되는 비즈니스용 Skype 서버 정책 설정은 다른 정책 수준에서 적용되는 설정을 다시 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71632-113">Skype for Business Server policy settings that are applied at one policy level can override settings that are applied at another policy level.</span></span> <span data-ttu-id="71632-114">비즈니스용 Skype 서버 정책 우선 순위는 다음과 같습니다. 사용자 정책(가장 큰 영향)이 사이트 정책을 재정의한 다음 사이트 정책이 글로벌 정책 (가장 큰 영향)을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="71632-114">Skype for Business Server policy precedence is: User policy (most influence) overrides a Site policy, and then a Site policy overrides a Global policy (least influence).</span></span> <span data-ttu-id="71632-115">즉, 정책 설정이 정책이 영향을 주는 개체에 가까울수록 개체에 미치는 영향이 커집니다.</span><span class="sxs-lookup"><span data-stu-id="71632-115">This means that the closer the policy setting is to the object that the policy is affecting, the more influence it has on the object.</span></span> <span data-ttu-id="71632-116">원격 사용자 액세스 사용에 대한 정책을 구성하는 자세한 내용은 비즈니스용 Skype 서버에서 원격 사용자 액세스를 제어하는 정책 [구성을 참조하세요.](../external-access-policies/configure-policies-to-control-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="71632-116">For details about configuring policies for the use of remote user access, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a><span data-ttu-id="71632-117">조직에 대한 원격 사용자 액세스를 사용하도록 설정하거나 사용하지 않도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="71632-117">To enable or disable remote user access for your organization</span></span>

1.  <span data-ttu-id="71632-118">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="71632-118">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="71632-119">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="71632-119">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="71632-120">왼쪽 탐색 모음에서 연결 및 외부 액세스를 클릭한 다음 **액세스 에지 구성을 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="71632-120">In the left navigation bar, click **Federation and External Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="71632-121">**액세스 에지 구성** 페이지에서 **전역** 을 클릭하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="71632-121">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="71632-122">**액세스 에지 구성 편집** 에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="71632-122">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="71632-123">조직에 대한 원격 사용자 액세스를 사용하도록 설정하려면 원격 사용자 액세스 사용 **확인란을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="71632-123">To enable remote user access for your organization, select the **Enable remote user access** check box.</span></span>
    
      - <span data-ttu-id="71632-124">조직에 대한 원격 사용자 액세스를 사용하지 않도록 설정하려면 원격 사용자 액세스 사용 **확인란의** 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="71632-124">To disable remote user access for your organization, clear the **Enable remote user access** check box.</span></span>

6.  <span data-ttu-id="71632-125">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="71632-125">Click **Commit**.</span></span>

<span data-ttu-id="71632-126">원격 사용자가 비즈니스용 Skype 서버를 실행하는 서버에 로그인할 수 있도록 설정하려면 원격 사용자 액세스를 지원하도록 하나 이상의 외부 액세스 정책도 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="71632-126">To enable remote users to sign in to your servers running Skype for Business Server, you must also configure at least one external access policy to support remote user access.</span></span> <span data-ttu-id="71632-127">자세한 내용은 비즈니스용 Skype 서버에서 원격 사용자 액세스를 제어하는 [정책 구성을 참조하세요.](../external-access-policies/configure-policies-to-control-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="71632-127">For details, see [Configure policies to control remote user access in Skype for Business Server](../external-access-policies/configure-policies-to-control-remote-user-access.md).</span></span>


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="71632-128">cmdlet을 사용하여 원격 사용자 액세스 Windows PowerShell 사용 안 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="71632-128">Enabling or disabling remote user access by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="71632-129">원격 사용자 액세스는 원격 Windows PowerShell cmdlet을 사용하여 관리할 Set-CsAccessEdgeConfiguration 있습니다.</span><span class="sxs-lookup"><span data-stu-id="71632-129">Remote user access can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="71632-130">이 cmdlet은 비즈니스용 Skype 서버 2013 관리 셸 또는 비즈니스용 Skype 서버의 원격 세션에서 실행할 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="71632-130">This cmdlet can be run either from the Skype for Business Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-remote-user-access"></a><span data-ttu-id="71632-131">원격 사용자 액세스를 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="71632-131">To enable remote user access</span></span>

  - <span data-ttu-id="71632-132">원격 사용자 액세스를 사용하도록 설정하려면 **AllowOutsideUsers** 속성 값을 True($True).</span><span class="sxs-lookup"><span data-stu-id="71632-132">To enable remote user access, set the value of the **AllowOutsideUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a><span data-ttu-id="71632-133">원격 사용자 액세스를 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="71632-133">To disable remote user access</span></span>

  - <span data-ttu-id="71632-134">원격 사용자 액세스를 사용하지 않도록 설정하기 위해 **AllowOutsideUsers** 속성 값을 False($False).</span><span class="sxs-lookup"><span data-stu-id="71632-134">To disable remote user access, set the value of the **AllowOutsideUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


