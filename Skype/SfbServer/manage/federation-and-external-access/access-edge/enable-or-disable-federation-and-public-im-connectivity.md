---
title: 페더레이션 및 공개 IM 연결을 사용하도록 설정 또는 해제
ms.reviewer: ''
ms:assetid: 8ec58f4b-9f6d-47b4-a187-d18a83fe4577
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182549(v=OCS.15)
ms:contentKeyID: 48184813
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
description: 지원하는 공용 IM(인스턴트 메시징) 공급자의 사용자 및 파트너 도메인을 포함하여 신뢰할 수 있는 고객 또는 파트너 조직에 계정이 있는 사용자가 조직 내 사용자와 공동 작업할 수 있도록 하려면 페더레이션 지원이 필요합니다.
ms.openlocfilehash: 390b23a92f91d762c3703a36c063dde54dff1de1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817418"
---
# <a name="enable-or-disable-federation-and-public-im-connectivity-in-skype-for-business-server"></a><span data-ttu-id="1618d-103">비즈니스용 Skype 서버에서 페더전 및 공용 IM 연결을 사용 또는 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="1618d-103">Enable or disable federation and public IM connectivity in Skype for Business Server</span></span>

<span data-ttu-id="1618d-104">지원하는 공용 IM(인스턴트 메시징) 공급자의 사용자 및 파트너 도메인을 포함하여 신뢰할 수 있는 고객 또는 파트너 조직에 계정이 있는 사용자가 조직 내 사용자와 공동 작업할 수 있도록 하려면 페더레이션 지원이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-104">Support for federation is required to enable users who have an account with a trusted customer or partner organization, including partner domains and users of public instant messaging (IM) provider users that you support, to collaborate with users in your organization.</span></span> <span data-ttu-id="1618d-105">또한 호스팅되는 Exchange 서비스 공급자를 사용하여 Microsoft Exchange Online 등의 호스팅되는 Exchange 서비스에 사서함이 있는 Enterprise Voice 사용자에게 음성 메일을 제공하려는 경우에도 페더레이션이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-105">Federation is also required to use a hosted Exchange service provider to provide voice mail to Enterprise Voice users whose mailboxes are located on a hosted Exchange service such as Microsoft Exchange Online.</span></span> <span data-ttu-id="1618d-106">이러한 외부 도메인과 트러스트 관계를 설정한 경우 해당 도메인의 사용자에게 배포에 액세스하고 비즈니스용 Skype 서버 통신에 참여할 수 있도록 권한을 부여할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-106">When you have established a trust relationship with these external domains, you can authorize users in those domains to access your deployment and participate in Skype for Business Server communications.</span></span> <span data-ttu-id="1618d-107">이러한 신뢰 관계는 페더레이션이라고 하며, Active Directory 신뢰 관계와는 관련이 없고 해당 관계에 종속되지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-107">This trust relationship is called a federation and it is not related to, or dependent upon, an Active Directory trust relationship.</span></span>

<span data-ttu-id="1618d-p102">페더레이션 도메인 사용자의 액세스를 지원하려면 페더레이션을 사용하도록 설정해야 합니다. 조직의 페더레이션을 사용하도록 설정하는 경우 다음 옵션을 구현할지 여부도 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-p102">To support access by users of federated domains, you must enable federation. If you enable federation for your organization, you must also specify whether to implement the following options:</span></span>

  - <span data-ttu-id="1618d-110">**파트너 도메인 검색 사용**   이 옵션을 사용하도록 설정하면 비즈니스용 Skype 서버는 DNS(Domain Name System) 레코드를 사용하여 허용 도메인 목록에 없는 도메인을 검색하여 검색된 페더링 파트너의 들어오는 트래픽을 자동으로 평가하고 트러스트 수준, 트래픽 양 및 관리자 설정에 따라 해당 트래픽을 제한하거나 차단합니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-110">**Enable partner domain discovery**   If you enable this option, Skype for Business Server uses Domain Name System (DNS) records to try to discover domains not listed in the allowed domains list, automatically evaluating incoming traffic from discovered federated partners and limiting or blocking that traffic based on trust level, amount of traffic, and administrator settings.</span></span> <span data-ttu-id="1618d-111">이 옵션을 선택하지 않은 경우 허용 도메인 목록에 포함되는 도메인의 사용자에 한해 페더전 사용자 액세스가 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-111">If you do not select this option, federated user access is enabled only for users in the domains that you include on the allowed domains list.</span></span> <span data-ttu-id="1618d-112">이 옵션을 선택하는지 여부에 따라 페더링 도메인에서 액세스 에지 서비스를 실행하는 특정 서버에 대한 액세스 제한을 포함하여 개별 도메인을 차단하거나 허용하도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-112">Whether or not you select this option, you can specify that individual domains to be blocked or allowed, including restricting access to specific servers running the Access Edge service in the federated domain.</span></span> <span data-ttu-id="1618d-113">페더링 도메인의 액세스를 제어하는 데 대한 자세한 내용은 허용되는 외부 도메인에 대한 지원 [구성을 참조합니다.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="1618d-113">For details about controlling access by federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>

  - <span data-ttu-id="1618d-114">**페더링**    파트너에게 보관 고지 조항 보내기    배포에 보관이 설정 중이라 고지 조항 고지가 페더링 파트너에게 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-114">**Send an archiving disclaimer to federated partners**    Disclaimer notice is sent to federated partners that archiving in your deployment is in place.</span></span> <span data-ttu-id="1618d-115">페더레이드 파트너 도메인과의 외부 통신 보관을 지원하는 경우 보관 고지 조항 알림을 사용하도록 설정하여 파트너에게 메시지가 보관 중임에 대해 경고해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-115">If you support archiving of external communications with federated partner domains, you should enable the archiving disclaimer notification to warn partners that their messages are being archived.</span></span>

<span data-ttu-id="1618d-p105">나중에 페더레이션 도메인 사용자의 액세스를 일시적으로 또는 영구적으로 차단하려면 조직의 페더레이션을 사용하지 않도록 설정하면 됩니다. 이 섹션의 절차를 사용하여 조직에 지원할 적절한 페더레이션 옵션 지정을 비롯하여 조직의 페더레이션 사용자 액세스를 사용하거나 사용하지 않도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="1618d-p105">If you later want to temporarily or permanently prevent access by users of federated domains, you can disable federation for your organization. Use the procedure in this section to enable or disable federated user access for your organization, including specifying the appropriate federation options to be supported for your organization.</span></span>

> [!NOTE]  
> <span data-ttu-id="1618d-118">조직에 대해 페더레이션을 사용하도록 설정하면 액세스 에지 서비스를 실행하는 서버가 페더레이션 도메인으로 라우팅하는 작업만 지원하도록 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-118">Enabling federation for your organization only specifies that your servers running the Access Edge service support routing to federated domains.</span></span> <span data-ttu-id="1618d-119">페더레이션 사용자 액세스를 지원하는 정책도 하나 이상 구성해야 페더레이션 도메인의 사용자가 조직의 IM 또는 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-119">Users in federated domains cannot participate in IM or conferences in your organization until you also configure at least one policy to support federated user access.</span></span> <span data-ttu-id="1618d-120">또한 공용 IM 연결을 지원하는 정책도 하나 이상 구성해야 공용 IM 서비스 공급자의 사용자가 조직의 IM 또는 회의에 참가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-120">Users of public IM service providers cannot participate in IM or conferences in your organization until you also configure at least one policy to support public IM connectivity.</span></span> <span data-ttu-id="1618d-121">라우팅 정보를 제공하는 호스팅된 음성 메일 정책을 구성할 때까지 비즈니스용 Skype 서버는 호스팅된 Exchange 서비스를 사용하여 사서함이 호스팅된 Exchange 서비스에 있는 사용자에 대해 전화 응답, Outlook Voice Access(음성 메일 포함) 또는 자동 전화 교환 서비스를 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-121">Skype for Business Server cannot use a hosted Exchange service to provide call answering, Outlook Voice Access (including voice mail), or auto-attendant services for users whose mailboxes are located on a hosted Exchange service until you configure a hosted voice mail policy that provides routing information.</span></span> <span data-ttu-id="1618d-122">다른 조직의 페더링 도메인 사용자와의 통신에 대한 정책을 구성하는 데 대한 자세한 내용은 조직의 SIP 페더전된 도메인 [관리를 참조합니다.](../sip-domains/manage-sip-federated-domains-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="1618d-122">For details about configuring policies for communication with users of federated domains in other organizations, see [Manage SIP federated domains for your organization](../sip-domains/manage-sip-federated-domains-for-your-organization.md).</span></span> <span data-ttu-id="1618d-123">또한 IM 서비스 공급자 사용자와의 통신을 지원하려는 경우 이를 지원하는 정책을 구성하고 지원할 개별 서비스 공급자에 대한 지원도 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-123">Additionally, if you want to support communication with users of IM service providers, you must configure policies to support it and also configure support for the individual service providers that you want to support.</span></span> <span data-ttu-id="1618d-124">자세한 내용은 조직의 [SIP 페더타이트 공급자 관리를 참조합니다.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="1618d-124">For details, see   [Manage SIP federated providers for your organization](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="to-enable-or-disable-federated-user-access-for-your-organization"></a><span data-ttu-id="1618d-125">조직의 페더레이션 사용자 액세스를 사용하거나 사용하지 않도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="1618d-125">To enable or disable federated user access for your organization</span></span>

1.  <span data-ttu-id="1618d-126">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-126">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1618d-127">브라우저 창을 열고 관리자 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="1618d-128">왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭하고 **액세스 에지 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-128">In the left navigation bar, click **External User Access**, and then click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="1618d-129">**액세스 에지 구성** 페이지에서 **전역** 을 클릭하고 **편집** 을 클릭한 후에 **세부 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-129">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1618d-130">**액세스 에지 구성 편집** 에서 다음 중 하나를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-130">In **Edit Access Edge Configuration**, do one of the following:</span></span>
    
      - <span data-ttu-id="1618d-131">조직의 페더레이션 사용자 액세스를 사용하도록 설정하려면 **페더레이션 사용자와의 통신 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-131">To enable federated user access for your organization, select the **Enable communications with federated users** check box.</span></span>
    
      - <span data-ttu-id="1618d-132">조직의 페더레이션 사용자 액세스를 사용하지 않도록 설정하려면 **페더레이션 사용자와의 통신 사용** 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-132">To disable federated user access for your organization, clear the **Enable communications with federated users** check box.</span></span>

6.  <span data-ttu-id="1618d-133">**페더레이션 사용자와의 통신 사용** 확인란을 선택한 경우 다음을 수행하십시오.</span><span class="sxs-lookup"><span data-stu-id="1618d-133">If you selected the **Enable communications with federated users** check box, do the following:</span></span>
    
    1.  <span data-ttu-id="1618d-134">파트너 도메인 자동 검색을 지원하려면 **파트너 도메인 검색 사용** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-134">If you want to support automatic discovery of partner domains, select the **Enable partner domain discovery** check box.</span></span>
    
    2.  <span data-ttu-id="1618d-135">조직에서 외부 통신 보관을 지원하는 경우 **페더레이션 파트너에게 보관 고지 사항 보내기** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-135">If your organization supports archiving of external communications, select the **Send archiving disclaimer to federated partners** check box.</span></span>

7.  <span data-ttu-id="1618d-136">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-136">Click **Commit**.</span></span>

<span data-ttu-id="1618d-137">페더러가 비즈니스용 Skype 서버 배포에서 사용자와 공동 작업을 할 수 있도록 페더러가 사용자 액세스를 지원하도록 하나 이상의 외부 액세스 정책도 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-137">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must also configure at least one external access policy to support federated user access.</span></span> <span data-ttu-id="1618d-138">자세한 내용은 페더타 사용자 액세스를 제어하는 정책 구성을 [참조합니다.](../external-access-policies/configure-policies-to-control-federated-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="1618d-138">For details, see [Configure policies to control federated user access](../external-access-policies/configure-policies-to-control-federated-user-access.md).</span></span> <span data-ttu-id="1618d-139">특정 페더타 도메인에 대한 액세스를 제어하려면 허용된 외부 도메인에 대한 지원 [구성을 참조합니다.](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="1618d-139">To control access for specific federated domains, see [Configure support for allowed external domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md#configure-support-for-allowed-external-domains-in-skype-for-business-server).</span></span>


## <a name="enabling-or-disabling-federation-and-public-im-connectivity-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="1618d-140">cmdlet을 사용하여 페더링 및 공용 IM 연결 사용 Windows PowerShell 사용 안</span><span class="sxs-lookup"><span data-stu-id="1618d-140">Enabling or disabling federation and public IM connectivity by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="1618d-141">페더ation 및 공용 IM 연결은 Windows PowerShell cmdlet을 사용하여 관리할 Set-CsAccessEdgeConfiguration 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-141">Federation and public IM connectivity can also be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="1618d-142">이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1618d-142">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 

## <a name="to-enable-federation-and-public-im-connectivity"></a><span data-ttu-id="1618d-143">페더ation 및 공용 IM 연결을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="1618d-143">To enable federation and public IM connectivity</span></span>

  - <span data-ttu-id="1618d-144">페더레이션 및 공용 IM 연결을 사용하도록 설정하려면 **AllowFederatedUsers** 속성 값을 True($True)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-144">To enable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True



## <a name="to-disable-federation-and-public-im-connectivity"></a><span data-ttu-id="1618d-145">페더전 및 공용 IM 연결을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="1618d-145">To disable federation and public IM connectivity</span></span>

  - <span data-ttu-id="1618d-146">페더레이션 및 공용 IM 연결을 사용하지 않도록 설정하려면 **AllowFederatedUsers** 속성 값을 False($False)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1618d-146">To disable federation and public IM connectivity, set the value of the **AllowFederatedUsers** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $False

