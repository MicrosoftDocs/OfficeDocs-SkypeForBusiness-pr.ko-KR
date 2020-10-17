---
title: 'Lync Server 2013: 설치 권한 위임'
description: 'Lync Server 2013: 설치 권한을 위임 합니다.'
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
ms.openlocfilehash: a7038cf729bad459dbcd2a84a308b14aa56b68dd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545344"
---
# <a name="delegate-setup-permissions-in-lync-server-2013"></a><span data-ttu-id="beac1-103">Lync Server 2013에서 설치 권한 위임</span><span class="sxs-lookup"><span data-stu-id="beac1-103">Delegate setup permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="beac1-104">_**마지막으로 수정 된 항목:** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="beac1-104">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="beac1-105">Lync Server 2013을 배포 하는 사용자 또는 그룹에 Domain Admins 그룹의 구성원 자격을 부여 하지 않으려면 RTCUniversalServerAdmins 그룹의 구성원이 **Enable-CsTopology**   lync server 2013를 실행 하는 서버에서 enable-cstopology Windows PowerShell cmdlet을 실행할 수 있도록 설정 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="beac1-105">If you do not want to grant membership in the Domain Admins group to users or groups who are deploying Lync Server 2013, you can enable members of the RTCUniversalServerAdmins group to run the **Enable-CsTopology** Windows PowerShell cmdlet on servers running Lync Server 2013.</span></span> <span data-ttu-id="beac1-106">기본적으로 RTCUniversalServerAdmins 그룹의 구성원은 이 cmdlet을 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="beac1-106">By default, members of the RTCUniversalServerAdmins group do not have the ability to run this cmdlet.</span></span> <span data-ttu-id="beac1-107">**부여-CsSetupPermission** cmdlet을 사용 하 고 lync server 2013을 실행 하는 서버에 대 한 컴퓨터 개체가 있는 OU (조직 구성 단위)를 지정 하 여 lync server를 실행 하는 서버에서 **enable-cstopology** 를 실행 하는 관리자 권한 및 사용 권한을 부여 합니다.</span><span class="sxs-lookup"><span data-stu-id="beac1-107">You grant administrator rights and permissions to run **Enable-CsTopology** on servers running Lync Server by using the **Grant-CsSetupPermission** cmdlet and specifying an organizational unit (OU) where computer objects for the server running Lync Server 2013 are located.</span></span>

<span data-ttu-id="beac1-108">Lync Server를 설치할 때 수행 되는 도메인 준비에는 RTCUniversalServerAdmins 그룹의 구성원이 Enable-CsTopology cmdlet을 실행할 수 있도록 하는 권한이 자동으로 추가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="beac1-108">The domain preparation that takes place when you install Lync Server does not automatically add the permissions that enable members of the RTCUniversalServerAdmins group to run the Enable-CsTopology cmdlet.</span></span> <span data-ttu-id="beac1-109">이는 기본적으로 토폴로지를 사용하려면 도메인 관리자여야 함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="beac1-109">That means that, by default, you must be a domain administrator in order to enable a topology.</span></span> <span data-ttu-id="beac1-110">RTCUniversalServerAdmins 그룹의 구성원에게 토폴로지를 사용할 수 있는 권한을 부여하려면 Grant-CsSetupPermissions cmdlet을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="beac1-110">To give members of the RTCUniversalServerAdmins group the right to enable a topology you must run the Grant-CsSetupPermissions cmdlet.</span></span> <span data-ttu-id="beac1-111">또한 Lync Server를 실행 하는 컴퓨터가 있는 각 Active Directory 컨테이너에 대해이 cmdlet을 실행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="beac1-111">In addition, you will need to run this cmdlet against each Active Directory container that houses computers running Lync Server.</span></span>

<span data-ttu-id="beac1-112">이 cmdlet은 RTCUniversalServerAdmins 그룹에만 사용 권한을 부여하며, 다른 보안 그룹 또는 개별 사용자에게 사용 권한을 부여하는 데는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="beac1-112">Keep in mind that this cmdlet only grants permissions to the RTCUniversalServerAdmins group; the cmdlet cannot be used to grant permissions to other security groups or to individual users.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="beac1-113"><STRONG>Enable-enable-cstopology</STRONG> 은 RTCUniversalServerAdmins 그룹 구성원이 Lync Server 2013을 설정 및 배포할 수 있도록 하는 키 cmdlet입니다.</span><span class="sxs-lookup"><span data-stu-id="beac1-113"><STRONG>Enable-CsTopology</STRONG> is the key cmdlet to allow the RTCUniversalServerAdmins group members to set up and deploy Lync Server 2013.</span></span>



</div>

<div>

## <a name="to-add-the-ability-to-run-enable-cstopology-to-the-rtcuniversalserveradmins-group"></a><span data-ttu-id="beac1-114">RTCUniversalServerAdmins 그룹에 Enable-CsTopology를 실행할 수 있는 권한을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="beac1-114">To add the ability to run Enable-CsTopology to the RTCUniversalServerAdmins group</span></span>

1.  <span data-ttu-id="beac1-115">위임된 사용자가 **Enable-CsTopology**를 실행하는 도메인에 대한 Domain Admins 그룹의 구성원으로 서버에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="beac1-115">Log on to a server as a member of the Domain Admins group for the domain on which the delegated user will run **Enable-CsTopology**.</span></span>

2.  <span data-ttu-id="beac1-116">Lync Server 2013 관리 셸을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="beac1-116">Open the Lync Server 2013 Management Shell.</span></span> <span data-ttu-id="beac1-117">Lync Server 2013 관리 셸은 각 프런트 엔드 서버 또는 Lync Server 2013 관리 도구가 설치 된 컴퓨터에 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="beac1-117">The Lync Server 2013 Management Shell is automatically installed on each Front End Server or any computer where the Lync Server 2013 administrative tools have been installed.</span></span> <span data-ttu-id="beac1-118">Lync Server 2013 관리 셸에 대 한 자세한 내용은 작업 설명서에서 [Lync server 2013 Management shell](lync-server-2013-lync-server-management-shell.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="beac1-118">For details about the Lync Server 2013 Management Shell, see [Lync Server 2013 Management Shell](lync-server-2013-lync-server-management-shell.md) in the Operations documentation.</span></span>

3.  <span data-ttu-id="beac1-119">Lync Server 2013 관리 셸에서 다음 cmdlet을 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="beac1-119">Run the following cmdlet from the Lync Server 2013 Management Shell:</span></span>
    
        Grant-CsSetupPermission -ComputerOU <DN of the OU> -Domain <Domain FQDN>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="beac1-120">OU가 최상위 수준이 아닌 경우 전체 도메인 이름을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="beac1-120">If the OU is not top level, you must provide the full domain name.</span></span>

    
    </div>
    
    <span data-ttu-id="beac1-121">다음 예에서 OU는 contoso.com 도메인에 있는 "Lync Server"입니다.</span><span class="sxs-lookup"><span data-stu-id="beac1-121">In the following example, the OU is “Lync Servers,” which is in the contoso.com domain.</span></span>
    
        Grant-CsSetupPermission -ComputerOU "OU=Lync Servers" -Domain contoso.com

</div>

</div>

<span> </span>

</div>

</div>

</div>

