---
title: 페더레이션 파트너 검색을 사용하도록 설정 또는 해제
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
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
description: 에지 서버를 배포하고 조직에 대해 페더레이션을 사용하도록 설정하는 시점에 페더레이션 파트너 도메인의 자동 검색 지원 여부를 지정해야 합니다.
ms.openlocfilehash: e1f076b725dff149f024a3fd59f9f7d52da4e6a8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817428"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="9e55a-103">비즈니스용 Skype 서버에서 페더전 파트너 검색을 사용하도록 설정하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="9e55a-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="9e55a-p101">에지 서버를 배포하고 조직에 대해 페더레이션을 사용하도록 설정하는 시점에 페더레이션 파트너 도메인의 자동 검색 지원 여부를 지정해야 합니다. 해당 구성을 변경하려면 이 항목의 절차를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9e55a-p101">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains. Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="9e55a-106">다음 절차에서는 이미 조직에 대해 페더레이션이 사용하도록 설정되어 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e55a-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="9e55a-107">페더링을 사용하도록 설정하는 데 대한 자세한 내용은 원격 사용자 액세스 사용 또는 사용 [안 을 참조합니다.](enable-or-disable-remote-user-access.md)</span><span class="sxs-lookup"><span data-stu-id="9e55a-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="9e55a-108">조직에 대해 페더레이션 도메인의 자동 검색을 사용하거나 사용하지 않도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="9e55a-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="9e55a-109">RTCUniversalServerAdmins 그룹의 구성원 또는 이와 동등한 사용자 권한을 가졌다는 사용자 계정 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포의 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="9e55a-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9e55a-110">브라우저 창을 열고 관리 URL을 입력하여 비즈니스용 Skype 서버 제어판을 니다.</span><span class="sxs-lookup"><span data-stu-id="9e55a-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="9e55a-111">왼쪽 탐색 모음에서 **외부 사용자 액세스** 를 클릭한 다음 **액세스 에지 구성** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e55a-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="9e55a-112">**액세스 에지 구성** 페이지에서 **전역** 을 클릭하고 **편집** 을 클릭한 후에 **자세한 정보 표시** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e55a-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="9e55a-113">**페더레이션 사용자와의 통신 사용** 아래의 **액세스 에지 구성 편집** 에서 **파트너 도메인 검색 사용** 확인란을 선택 또는 선택 취소하여 파트너 도메인의 자동 검색을 사용하거나 사용하지 않도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e55a-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="9e55a-114">**커밋** 을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="9e55a-114">Click **Commit**.</span></span>

<span data-ttu-id="9e55a-115">페더러가 비즈니스용 Skype 서버 배포에서 사용자와 공동 작업을 할 수 있도록 페더러가 사용자 액세스를 지원하도록 하나 이상의 외부 액세스 정책도 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e55a-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="9e55a-116">자세한 내용은 페더ation 및 공용 IM 연결 사용 또는 사용 안 [하도록 설정 을 참조 합니다.](enable-or-disable-federation-and-public-im-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="9e55a-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="9e55a-117">특정 페더링 도메인에 대한 액세스를 제어하는 데 대한 자세한 내용은 SIP 페더링 도메인 관리 및 [SIP](../sip-domains/manage-sip-federated-domains-for-your-organization.md) 페더링 공급자 [관리를 참조합니다.](../sip-providers/manage-sip-federated-providers-for-your-organization.md)</span><span class="sxs-lookup"><span data-stu-id="9e55a-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="9e55a-118">cmdlet을 사용하여 페더링 파트너 검색을 설정하거나 Windows PowerShell 설정</span><span class="sxs-lookup"><span data-stu-id="9e55a-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="9e55a-119">페더전 파트너 검색은 Windows PowerShell cmdlet을 사용하여 관리할 Set-CsAccessEdgeConfiguration 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e55a-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="9e55a-120">이 cmdlet은 비즈니스용 Skype 서버 관리 셸 또는 비즈니스용 Skype 서버 관리 셸에서 실행할 수 Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e55a-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="9e55a-121">페더전 파트너 검색을 사용하도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="9e55a-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="9e55a-p105">페더레이션 파트너 검색을 사용하도록 설정하려면 **EnablePartnerDiscovery** 속성의 값을 True($True)로 설정합니다. 이 속성 값을 변경하려면 DNS SRV 라우팅을 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9e55a-p105">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True). Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="9e55a-124">페더전 파트너 검색을 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="9e55a-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="9e55a-125">페더레이션 파트너 검색을 사용하지 않도록 설정하려면 **EnablePartnerDiscovery** 속성의 값을 False($False)로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="9e55a-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

