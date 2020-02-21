---
title: 'Lync Server 2013: 네트워크 미디어 바이패스 사용 안 함'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Disabling network media bypass
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49733741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: eaad239f320f498378498f9b3e373592d487c0c8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197541"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="disabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="dcbbf-102">Lync Server 2013에서 네트워크 미디어 바이패스 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="dcbbf-102">Disabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dcbbf-103">_**마지막으로 수정 된 항목:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="dcbbf-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="dcbbf-104">미디어 바이패스 설정은 Microsoft Lync Server 2013 배포 전체에서 전역적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbf-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="dcbbf-105">미디어 바이패스는 통화가 중재 서버를 바이패스하도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbf-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="dcbbf-106">미디어 바이패스를 사용 하는 경우에 대 한 자세한 내용은 계획 섹션에서 [Lync Server 2013의 미디어 바이패스 계획](lync-server-2013-planning-for-media-bypass.md) 을 참조 하십시오. Lync Server 제어판에서 미디어 바이패스를 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbf-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.You can disable media bypass from the Lync Server Control Panel.</span></span> <span data-ttu-id="dcbbf-107">Medial bypass 사용 및 구성에 대 한 자세한 내용은 [Lync Server 2013에서 네트워크 미디어 바이패스 사용](lync-server-2013-enabling-network-media-bypass.md) 을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dcbbf-107">For details on enabling and configuring medial bypass, see [Enabling network media bypass in Lync Server 2013](lync-server-2013-enabling-network-media-bypass.md)</span></span>

<div>

## <a name="to-disable-media-bypass"></a><span data-ttu-id="dcbbf-108">미디어 바이패스를 사용하지 않도록 설정하려면</span><span class="sxs-lookup"><span data-stu-id="dcbbf-108">To disable media bypass</span></span>

1.  <span data-ttu-id="dcbbf-109">RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정 (또는 이와 동등한 사용자 권한 포함) 또는 CsAdministrator 역할이 할당 되 면 내부 배포의 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbf-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="dcbbf-110">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbf-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="dcbbf-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="dcbbf-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="dcbbf-112">왼쪽 탐색 모음에서 **네트워크 구성**을 클릭하고 **전역**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbf-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="dcbbf-p103">**전역** 페이지에서 **전역** 구성을 클릭합니다. 구성은 항상 하나뿐이며 이름은 항상 전역입니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbf-p103">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="dcbbf-115">**편집** 메뉴에서 **자세히 보기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbf-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="dcbbf-116">**전역 설정 편집** 페이지에서 **미디어 바이패스 사용** 확인란의 선택을 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbf-116">On the **Edit Global Setting** page, clear the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="dcbbf-117">**커밋**을 클릭하여 변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="dcbbf-117">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dcbbf-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dcbbf-118">See Also</span></span>


[<span data-ttu-id="dcbbf-119">Lync Server 2013에서 네트워크 미디어 바이패스 사용</span><span class="sxs-lookup"><span data-stu-id="dcbbf-119">Enabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-network-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

