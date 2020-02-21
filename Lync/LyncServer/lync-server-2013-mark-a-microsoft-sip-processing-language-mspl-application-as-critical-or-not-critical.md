---
title: 'Lync Server 2013: Microsoft MSPL (SIP Processing Language) 응용 프로그램을 중요 또는 중요 하지 않음으로 표시'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical
ms:assetid: df68fdc6-b7e6-4f07-acdc-0cd4c2c888a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182598(v=OCS.15)
ms:contentKeyID: 48185622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31b0b4e532cf79a659dfe2b216815953ab24caf1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical-in-lync-server-2013"></a><span data-ttu-id="fbb06-102">Lync Server 2013에서 Microsoft MSPL (SIP 처리 언어) 응용 프로그램을 중요 또는 중요 하지 않음으로 표시</span><span class="sxs-lookup"><span data-stu-id="fbb06-102">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbb06-103">_**마지막으로 수정 된 항목:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="fbb06-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="fbb06-104">MSPL (microsoft SIP Processing Language) 서버 응용 프로그램은 Microsoft Lync 2010 API 대신 MSPL 스크립팅 언어를 사용 하는 스크립트 전용 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="fbb06-104">Microsoft SIP Processing Language (MSPL) server applications are script-only applications that use the MSPL scripting language instead of the Microsoft Lync 2010 API.</span></span> <span data-ttu-id="fbb06-105">일부 MSPL 서버 응용 프로그램은 중요로 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fbb06-105">Some MSPL server applications are specified as critical.</span></span> <span data-ttu-id="fbb06-106">스크립트가 중요 한 경우 Lync Server 2013을 시작 하기 위해 시스템을 시작 하는 동안 스크립트가 시작 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb06-106">If a script is critical, the script must start during system startup in order for Lync Server 2013 to start.</span></span> <span data-ttu-id="fbb06-107">Lync Server가 실행 되는 동안 스크립트가 실패 하면 서버가 종료 되지 않지만 스크립트에 트래픽을 보내지 않고 이벤트 로그에 오류를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb06-107">If the script fails while Lync Server is running, the server does not shut down, but it stops sending traffic to the script, and it writes errors in the event log.</span></span>

<span data-ttu-id="fbb06-108">Lync Server 제어판을 사용 하 여 MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램을 중요 하거나 표시 하지 않는 것으로 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb06-108">You can use Lync Server Control Panel to mark Microsoft SIP Processing Language (MSPL) server applications as critical or unmark them.</span></span>

<span data-ttu-id="fbb06-p102">일부 스크립트에서는 이 옵션이 지원되지 않습니다. 예를 들어 DefaultRouting 스크립트가 중요 스크립트로 표시되었으며, DefaultRouting에 대해 이 옵션을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fbb06-p102">Not all scripts support this option. For example, the DefaultRouting script is marked as critical, and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-mark-or-unmark-an-mspl-server-application-as-critical"></a><span data-ttu-id="fbb06-111">MSPL 서버 응용 프로그램을 중요 응용 프로그램으로 표시하거나 표시 해제하려면</span><span class="sxs-lookup"><span data-stu-id="fbb06-111">To mark or unmark an MSPL server application as critical</span></span>

1.  <span data-ttu-id="fbb06-112">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb06-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="fbb06-113">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="fbb06-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="fbb06-114">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fbb06-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="fbb06-115">왼쪽 탐색 표시줄에서 **토폴로지**를 클릭한 다음 **서버 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb06-115">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="fbb06-116">**서버 응용 프로그램** 페이지에서 필요한 경우 열 머리글을 클릭하여 응용 프로그램을 정렬한 다음 수정할 서버 응용 프로그램을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb06-116">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="fbb06-117">**동작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="fbb06-117">Click **Action**.</span></span>

6.  <span data-ttu-id="fbb06-118">**중요로 표시** 또는 **중요로 선택 해제**를 클릭합니다(즉 스크립트에서 이 옵션이 지원되는 경우).</span><span class="sxs-lookup"><span data-stu-id="fbb06-118">Click **Mark as critical** or **Unselect as critical** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fbb06-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fbb06-119">See Also</span></span>


[<span data-ttu-id="fbb06-120">Lync Server 2013에서 MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램을 사용 하거나 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="fbb06-120">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>](lync-server-2013-enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application.md)  


[<span data-ttu-id="fbb06-121">Lync Server 2013에서 MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램 보기</span><span class="sxs-lookup"><span data-stu-id="fbb06-121">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="fbb06-122">Lync Server 2013 토폴로지 관리</span><span class="sxs-lookup"><span data-stu-id="fbb06-122">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

