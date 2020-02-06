---
title: 페더레이션 파트너 검색을 사용하거나 사용하지 않도록 설정
ms.reviewer: ''
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
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
description: Edge 서버를 배포 하 고 조직에 대해 사용 하도록 설정한 경우 페더레이션 파트너 도메인의 자동 검색을 지원 하는지 여부를 지정 해야 합니다.
ms.openlocfilehash: a64e2056feacbee076fcaf9b0012a36f72c91523
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818399"
---
# <a name="enable-or-disable-discovery-of-federation-partners-in-skype-for-business-server"></a><span data-ttu-id="d0863-103">비즈니스용 Skype 서버에서 페더레이션 파트너의 검색 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="d0863-103">Enable or disable discovery of federation partners in Skype for Business Server</span></span>

<span data-ttu-id="d0863-104">Edge 서버를 배포 하 고 조직에 대해 사용 하도록 설정한 경우 페더레이션 파트너 도메인의 자동 검색을 지원 하는지 여부를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0863-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="d0863-105">이 항목의 절차를 사용 하 여 해당 구성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0863-105">Use the procedure in this topic to change that configuration.</span></span>

> [!NOTE]  
> <span data-ttu-id="d0863-106">다음 절차에서는 조직에 페더레이션이 이미 설정 되어 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0863-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="d0863-107">페더레이션 사용에 대 한 자세한 내용은 [원격 사용자 액세스 사용 또는 사용 안 함을](enable-or-disable-remote-user-access.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d0863-107">For details about enabling federation, see [Enable or disable remote user access](enable-or-disable-remote-user-access.md).</span></span>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="d0863-108">조직의 페더레이션 도메인 자동 검색을 사용 하거나 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d0863-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="d0863-109">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0863-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d0863-110">브라우저 창을 열고 관리자 URL을 입력 하 여 비즈니스용 Skype 서버 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d0863-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3.  <span data-ttu-id="d0863-111">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 하 고 **Edge 구성 액세스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0863-111">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="d0863-112">**액세스 경계 구성** 페이지에서 **전역**을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0863-112">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="d0863-113">**액세스에 지 구성 편집**의 **페더레이션 사용자와 통신 사용**에서 파트너 **도메인 검색** 사용 확인란을 선택 하거나 선택을 취소 하 여 파트너 도메인의 자동 검색을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0863-113">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="d0863-114">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d0863-114">Click **Commit**.</span></span>

<span data-ttu-id="d0863-115">페더레이션 사용자가 비즈니스용 Skype 서버 배포에서 사용자와 공동 작업을 할 수 있도록 하려면 하나 이상의 외부 액세스 정책이 페더레이션 사용자 액세스를 지원 하도록 구성 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0863-115">To enable federated users to collaborate with users in your Skype for Business Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="d0863-116">자세한 내용은 [페더레이션 및 공용 IM 연결 사용 또는 사용 안 함을](enable-or-disable-federation-and-public-im-connectivity.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d0863-116">For details, see [Enable or disable federation and public IM connectivity](enable-or-disable-federation-and-public-im-connectivity.md).</span></span> <span data-ttu-id="d0863-117">특정 페더레이션 도메인에 대 한 액세스 제어에 대 한 자세한 내용은 [sip 페더레이션 도메인 관리](../sip-domains/manage-sip-federated-domains-for-your-organization.md) 및 [Sip 페더레이션된 공급자 관리](../sip-providers/manage-sip-federated-providers-for-your-organization.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d0863-117">For details about controlling access for specific federated domains, see [Manage SIP federated domains](../sip-domains/manage-sip-federated-domains-for-your-organization.md) and [Manage SIP federated providers](../sip-providers/manage-sip-federated-providers-for-your-organization.md).</span></span>


## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d0863-118">Windows PowerShell cmdlet을 사용 하 여 페더레이션 파트너 검색 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="d0863-118">Enabling or disabling discovery of federation partners by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="d0863-119">페더레이션 파트너 검색은 Windows PowerShell 및 CsAccessEdgeConfiguration cmdlet을 사용 하 여 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0863-119">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="d0863-120">이 cmdlet은 비즈니스용 Skype 서버 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0863-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="d0863-121">페더레이션 파트너의 검색을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d0863-121">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="d0863-122">페더레이션 파트너의 검색을 사용 하도록 설정 하려면 **Enable함 검색** 속성 값을 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0863-122">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="d0863-123">이 속성 값을 변경 하려면 DNS SRV 라우팅 기능을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0863-123">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True


## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="d0863-124">페더레이션 파트너 검색을 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="d0863-124">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="d0863-125">페더레이션 파트너의 검색을 사용 하지 않도록 설정 하려면 **Enable함 검색** 속성 값을 False ($False)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0863-125">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

