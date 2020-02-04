---
title: 'Lync Server 2013: 설치 권한 위임'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delegate setup permissions
ms:assetid: 9dca1683-4c69-4534-8ebe-6bd635cbae49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412735(v=OCS.15)
ms:contentKeyID: 48184997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 245fa0cb3bb5393f1d0f09a3f3b9c10176c015ce
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delegate-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="6d918-102">Lync Server 2013에서 설치 권한 위임</span><span class="sxs-lookup"><span data-stu-id="6d918-102">Delegate setup permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d918-103">_**마지막으로 수정한 주제:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="6d918-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="6d918-104">Lync server 2013를 배포 하는 사용자 또는 그룹에 Domain Admins 그룹의 구성원 자격을 부여 하지 않으려는 경우 RTCUniversalServerAdmins 그룹의 구성원을 사용 하도록 설정 하 여 lync server 2013를 실행 하는 서버에서 **enable-CsTopology** Windows PowerShell cmdlet을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d918-104">If you do not want to grant membership in the Domain Admins group to users or groups who are deploying Lync Server 2013, you can enable members of the RTCUniversalServerAdmins group to run the **Enable-CsTopology** Windows PowerShell cmdlet on servers running Lync Server 2013.</span></span> <span data-ttu-id="6d918-105">기본적으로 RTCUniversalServerAdmins 그룹의 구성원은이 cmdlet을 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d918-105">By default, members of the RTCUniversalServerAdmins group do not have the ability to run this cmdlet.</span></span> <span data-ttu-id="6d918-106">**허용-CsSetupPermission** cmdlet을 사용 하 고 lync server 2013를 실행 하는 서버에 대 한 컴퓨터 개체가 있는 OU (조직 구성 단위)를 지정 하 여 lync server를 실행 하는 서버에서 **CsTopology** 를 실행 하려면 관리자 권한 및 사용 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d918-106">You grant administrator rights and permissions to run **Enable-CsTopology** on servers running Lync Server by using the **Grant-CsSetupPermission** cmdlet and specifying an organizational unit (OU) where computer objects for the server running Lync Server 2013 are located.</span></span>

<span data-ttu-id="6d918-107">Lync Server를 설치할 때 발생 하는 도메인 준비는 RTCUniversalServerAdmins 그룹의 멤버가 Enable-CsTopology cmdlet을 실행할 수 있도록 허용 하는 사용 권한을 자동으로 추가 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d918-107">The domain preparation that takes place when you install Lync Server does not automatically add the permissions that enable members of the RTCUniversalServerAdmins group to run the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="6d918-108">즉, 토폴로지를 활성화 하기 위해 기본적으로 도메인 관리자 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d918-108">That means that, by default, you must be a domain administrator in order to enable a topology.</span></span> <span data-ttu-id="6d918-109">RTCUniversalServerAdmins 그룹의 구성원에 게 토폴로지를 사용 하도록 설정 하는 권한을 부여 하려면 부여-CsSetupPermissions 사용 권한 cmdlet을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d918-109">To give members of the RTCUniversalServerAdmins group the right to enable a topology you must run the Grant-CsSetupPermissions cmdlet.</span></span> <span data-ttu-id="6d918-110">또한 Lync Server를 실행 하는 컴퓨터를 포함 하는 각 Active Directory 컨테이너에 대해이 cmdlet을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d918-110">In addition, you will need to run this cmdlet against each Active Directory container that houses computers running Lync Server.</span></span>

<span data-ttu-id="6d918-111">이 cmdlet은 RTCUniversalServerAdmins 그룹에 대 한 권한만 부여 합니다. cmdlet은 다른 보안 그룹 또는 개별 사용자에 게 사용 권한을 부여 하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d918-111">Keep in mind that this cmdlet only grants permissions to the RTCUniversalServerAdmins group; the cmdlet cannot be used to grant permissions to other security groups or to individual users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6d918-112"><STRONG>Enable-CsTopology</STRONG> 는 RTCUniversalServerAdmins 그룹 구성원이 Lync Server 2013를 설정 하 고 배포 하는 데 사용할 수 있는 키 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="6d918-112"><STRONG>Enable-CsTopology</STRONG> is the key cmdlet to allow the RTCUniversalServerAdmins group members to set up and deploy Lync Server 2013.</span></span>



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a><span data-ttu-id="6d918-113">RTCUniversalServerAdmins 그룹에 Enable-CsTopology를 실행 하는 기능을 추가 하려면</span><span class="sxs-lookup"><span data-stu-id="6d918-113">To add the ability to run Enable-CsTopology to the RTCUniversalServerAdmins group</span></span>

1.  <span data-ttu-id="6d918-114">위임 된 사용자가 **CsTopology**를 실행할 도메인에 대 한 domain Admins 그룹의 구성원으로 서버에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d918-114">Log on to a server as a member of the Domain Admins group for the domain on which the delegated user will run **Enable-CsTopology**.</span></span>

2.  <span data-ttu-id="6d918-115">Lync Server 2013 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6d918-115">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="6d918-116">Lync Server 2013 관리 셸은 각 프런트 엔드 서버 또는 Lync Server 2013 관리 도구가 설치 된 컴퓨터에 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d918-116">The Lync Server 2013 Management Shell is automatically installed on each Front End Server or any computer where the Lync Server 2013 administrative tools have been installed.</span></span> <span data-ttu-id="6d918-117">Lync Server 2013 관리 셸에 대 한 자세한 내용은 운영 설명서의 [Lync server 2013 관리 셸을](lync-server-2013-lync-server-management-shell.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d918-117">For details about the Lync Server 2013 Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation.</span></span>

3.  <span data-ttu-id="6d918-118">Lync Server 2013 관리 셸에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d918-118">Run the following cmdlet from the Lync Server 2013 Management Shell:</span></span>
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6d918-119">OU가 최상위 수준이 아니면 전체 도메인 이름을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d918-119">If the OU is not top level, you must provide the full domain name.</span></span>

    
    </div>
    
    <span data-ttu-id="6d918-120">다음 예제에서 OU는 contoso.com 도메인에 "Lync 서버"입니다.</span><span class="sxs-lookup"><span data-stu-id="6d918-120">In the following example, the OU is “Lync Servers,” which is in the contoso.com domain.</span></span>
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

