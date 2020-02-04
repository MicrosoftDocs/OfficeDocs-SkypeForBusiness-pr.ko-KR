---
title: 'Lync Server 2013: 페더레이션 파트너 검색을 사용하거나 사용하지 않도록 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable discovery of federation partners
ms:assetid: 91fd036b-b1af-47cf-b1cf-0aa0a783c2aa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182550(v=OCS.15)
ms:contentKeyID: 48184857
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f97a6ab26a3b8b3f011a62cd92bbd0271f781a1a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736078"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-discovery-of-federation-partners-in-lync-server-2013"></a><span data-ttu-id="b21b7-102">Lync Server 2013에서 페더레이션 파트너 검색을 사용하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="b21b7-102">Enable or disable discovery of federation partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b21b7-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="b21b7-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="b21b7-104">Edge 서버를 배포 하 고 조직에 대해 사용 하도록 설정한 경우 페더레이션 파트너 도메인의 자동 검색을 지원 하는지 여부를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b21b7-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to support automatic discovery of federated partner domains.</span></span> <span data-ttu-id="b21b7-105">이 항목의 절차를 사용 하 여 해당 구성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b21b7-105">Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b21b7-106">다음 절차에서는 조직에 페더레이션이 이미 설정 되어 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b21b7-106">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="b21b7-107">페더레이션 사용에 대 한 자세한 내용은 배포 설명서 또는 운영 설명서의 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b21b7-107">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-automatic-discovery-of-federated-domains-for-your-organization"></a><span data-ttu-id="b21b7-108">조직의 페더레이션 도메인 자동 검색을 사용 하거나 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="b21b7-108">To enable or disable automatic discovery of federated domains for your organization</span></span>

1.  <span data-ttu-id="b21b7-109">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b21b7-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b21b7-110">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b21b7-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="b21b7-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b21b7-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="b21b7-112">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 하 고 **Edge 구성 액세스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b21b7-112">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="b21b7-113">**액세스 경계 구성** 페이지에서 **전역**을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b21b7-113">On the **Access Edge Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="b21b7-114">**액세스에 지 구성 편집**의 **페더레이션 사용자와 통신 사용**에서 파트너 **도메인 검색** 사용 확인란을 선택 하거나 선택을 취소 하 여 파트너 도메인의 자동 검색을 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b21b7-114">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Enable partner domain discovery** check box to enable or disable automatic discovery of partner domains.</span></span>

6.  <span data-ttu-id="b21b7-115">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b21b7-115">Click **Commit**.</span></span>

<span data-ttu-id="b21b7-116">페더레이션 사용자가 Lync Server 배포의 사용자와 공동 작업을 할 수 있도록 하려면 하나 이상의 외부 액세스 정책이 페더레이션 사용자 액세스를 지원 하도록 구성 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b21b7-116">To enable federated users to collaborate with users in your Lync Server deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="b21b7-117">자세한 내용은 배포 설명서 또는 운영 설명서의 [Lync Server 2013에서 페더레이션 및 공용 IM 연결을 사용 하거나 사용 하지 않도록 설정을](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b21b7-117">For details, see [Enable or disable federation and public IM connectivity in Lync Server 2013](lync-server-2013-enable-or-disable-federation-and-public-im-connectivity.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="b21b7-118">특정 페더레이션 도메인에 대 한 액세스를 제어 하는 방법에 대 한 자세한 내용은 [Lync server 2013에서 조직의 sip 페더레이션 도메인 관리](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [lync server 2013에서 조직의 sip 페더레이션 공급자](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) 관리 및 운영 설명서의 [lync server 2013 xmpp 페더레이션된 파트너 관리](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b21b7-118">For details about controlling access for specific federated domains, see [Manage SIP federated domains for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-domains-for-your-organization.md), [Manage SIP federated providers for your organization in Lync Server 2013](lync-server-2013-manage-sip-federated-providers-for-your-organization.md) and [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-discovery-of-federation-partners-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="b21b7-119">Windows PowerShell Cmdlet을 사용 하 여 페더레이션 파트너 검색 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="b21b7-119">Enabling or Disabling Discovery of Federation Partners by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="b21b7-120">페더레이션 파트너 검색은 Windows PowerShell 및 CsAccessEdgeConfiguration cmdlet을 사용 하 여 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b21b7-120">Discovery of federation partners can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="b21b7-121">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b21b7-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="b21b7-122">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b21b7-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-discovery-of-federation-partners"></a><span data-ttu-id="b21b7-123">페더레이션 파트너의 검색을 사용 하도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="b21b7-123">To enable discovery of federation partners</span></span>

  - <span data-ttu-id="b21b7-124">페더레이션 파트너의 검색을 사용 하도록 설정 하려면 **Enable함 검색** 속성 값을 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b21b7-124">To enable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to True ($True).</span></span> <span data-ttu-id="b21b7-125">이 속성 값을 변경 하려면 DNS SRV 라우팅 기능을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b21b7-125">Note that you must enable DNS SRV routing in order to change this property value.</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $True

</div>

<div>

## <a name="to-disable-discovery-of-federation-partners"></a><span data-ttu-id="b21b7-126">페더레이션 파트너 검색을 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="b21b7-126">To disable discovery of federation partners</span></span>

  - <span data-ttu-id="b21b7-127">페더레이션 파트너의 검색을 사용 하지 않도록 설정 하려면 **Enable함 검색** 속성 값을 False ($False)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b21b7-127">To disable discovery of federation partners, set the value of the **EnablePartnerDiscovery** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -UseDnsSrvRouting -EnablePartnerDiscovery $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

