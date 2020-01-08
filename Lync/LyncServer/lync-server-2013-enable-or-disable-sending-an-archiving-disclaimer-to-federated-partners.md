---
title: 페더레이션 파트너에게 보관 고지 사항 보내기를 사용하거나 사용하지 않도록 설정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable or disable sending an Archiving disclaimer to federated partners
ms:assetid: c8e9a2fa-9dc1-4e4d-919f-56ece8004864
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182584(v=OCS.15)
ms:contentKeyID: 48185391
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9364f3562c837b949ef589fc7c5cbd2bc4a2b4cb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-or-disable-sending-an-archiving-disclaimer-to-federated-partners-in-lync-server-2013"></a><span data-ttu-id="650f5-102">Lync Server 2013에서 페더레이션 파트너에게 보관 고지 사항 보내기를 사용하거나 사용하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="650f5-102">Enable or disable sending an Archiving disclaimer to federated partners in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="650f5-103">_**마지막으로 수정한 주제:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="650f5-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="650f5-104">Edge 서버를 배포 하 고 조직에 대해 페더레이션을 사용 하도록 설정한 경우에는 페더레이션 파트너에 게 자동으로 보관 거부를 보낼지 여부를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="650f5-104">At the time you deployed your Edge Servers and enabled federation for your organization, you should have specified whether to automatically send the archiving disclaimer to federated partners.</span></span> <span data-ttu-id="650f5-105">외부 통신을 보관 하는 경우 보관 고 지 사항을 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="650f5-105">If you archive external communications, you should enable the sending of an archiving disclaimer.</span></span> <span data-ttu-id="650f5-106">이 항목의 절차를 사용 하 여 해당 구성을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="650f5-106">Use the procedure in this topic to change that configuration.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="650f5-107">다음 절차에서는 조직에 페더레이션이 이미 설정 되어 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="650f5-107">The following procedure assumes that you have already enabled federation for your organization.</span></span> <span data-ttu-id="650f5-108">페더레이션 사용에 대 한 자세한 내용은 배포 설명서 또는 운영 설명서의 <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Lync Server 2013에서 원격 사용자 액세스 사용 또는 사용 안 함을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="650f5-108">For details about enabling federation, see <A href="lync-server-2013-enable-or-disable-remote-user-access.md">Enable or disable remote user access in Lync Server 2013</A> in the Deployment documentation or the Operations documentation.</span></span>



</div>

<div>

## <a name="to-enable-or-disable-sending-of-an-archiving-disclaimer-to-federated-partners"></a><span data-ttu-id="650f5-109">페더레이션 파트너에 게 보관 고 지 사항 보내기를 사용 하거나 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="650f5-109">To enable or disable sending of an archiving disclaimer to federated partners</span></span>

1.  <span data-ttu-id="650f5-110">RTCUniversalServerAdmins 그룹의 구성원 이거나 해당 사용자 권한이 있는 사용자 계정에서 또는 CsAdministrator 역할에 할당 된 경우 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="650f5-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="650f5-111">브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="650f5-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="650f5-112">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="650f5-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="650f5-113">왼쪽 탐색 모음에서 **외부 사용자 액세스**를 클릭 하 고 **Edge 구성 액세스**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="650f5-113">In the left navigation bar, click **External User Access**, click **Access Edge Configuration**.</span></span>

4.  <span data-ttu-id="650f5-114">**액세스 경계 구성** 탭에서 **전역**을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="650f5-114">On the **Access Edge Configuration** tab, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="650f5-115">**액세스에 지 구성 편집**의 **페더레이션 사용자와 통신 사용**에서 페더레이션 **파트너에 게 보관** 고 지 사항 보내기 확인란을 선택 하거나 선택을 취소 하 여 보관 거부를 자동으로 보내는 기능을 설정 하거나 해제 합니다.</span><span class="sxs-lookup"><span data-stu-id="650f5-115">In **Edit Access Edge Configuration**, under **Enable communications with federated users**, select or clear the **Send archiving disclaimer to federated partners** check box to enable or disable automatically sending the archiving disclaimer.</span></span>

6.  <span data-ttu-id="650f5-116">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="650f5-116">Click **Commit**.</span></span>

<span data-ttu-id="650f5-117">페더레이션 사용자가 Lync Server 2013 배포에서 사용자와 공동 작업할 수 있도록 하려면 하나 이상의 외부 액세스 정책이 페더레이션 사용자 액세스를 지원 하도록 구성 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="650f5-117">To enable federated users to collaborate with users in your Lync Server 2013 deployment, you must have also configured at least one external access policy to support federated user access.</span></span> <span data-ttu-id="650f5-118">자세한 내용은 배포 설명서 또는 운영 설명서의 [Lync Server 2013에서 XMPP 페더레이션된 파트너 관리](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="650f5-118">For details, see [Manage XMPP federated partners in Lync Server 2013](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md) in the Deployment documentation or the Operations documentation.</span></span> <span data-ttu-id="650f5-119">특정 페더레이션 도메인에 대 한 액세스 제어에 대 한 자세한 내용은 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 허용 되는 외부 도메인에 대 한 지원 구성을](lync-server-2013-configure-support-for-allowed-external-domains.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="650f5-119">For details about controlling access for specific federated domains, see [Configure support for allowed external domains in Lync Server 2013](lync-server-2013-configure-support-for-allowed-external-domains.md) in the Deployment documentation or Operations documentation.</span></span>

</div>

<div>

## <a name="enabling-or-disabling-the-archiving-disclaimer-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="650f5-120">Windows PowerShell Cmdlet을 사용 하 여 보관 고 지 사항 사용 또는 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="650f5-120">Enabling or Disabling the Archiving Disclaimer by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="650f5-121">보관 고 지 사항 사용은 Windows PowerShell 및 CsAccessEdgeConfiguration cmdlet을 사용 하 여 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="650f5-121">The use of the archiving disclaimer can be managed by using Windows PowerShell and the Set-CsAccessEdgeConfiguration cmdlet.</span></span> <span data-ttu-id="650f5-122">이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="650f5-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="650f5-123">원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="650f5-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-enable-the-archiving-disclaimer"></a><span data-ttu-id="650f5-124">보관 고 지 사항을 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="650f5-124">To enable the archiving disclaimer</span></span>

  - <span data-ttu-id="650f5-125">보관 부인를 사용 하도록 설정 하려면 **EnableArchivingDisclaimer** 속성 값을 True ($True)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="650f5-125">To enable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to True ($True):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $True

</div>

<div>

## <a name="to-disable-the-archiving-disclaimer"></a><span data-ttu-id="650f5-126">보관 고 지 사항을 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="650f5-126">To disable the archiving disclaimer</span></span>

  - <span data-ttu-id="650f5-127">보관 고 지 사항을 사용 하지 않으려면 **EnableArchivingDisclaimer** 속성 값을 False ($False)로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="650f5-127">To disable the archiving disclaimer, set the value of the **EnableArchivingDisclaimer** property to False ($False):</span></span>
    
        Set-CsAccessEdgeConfiguration -EnableArchivingDisclaimer $False

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

