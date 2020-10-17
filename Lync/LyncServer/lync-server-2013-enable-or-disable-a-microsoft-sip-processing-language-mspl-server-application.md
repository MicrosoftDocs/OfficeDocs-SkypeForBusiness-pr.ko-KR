---
title: 'Lync Server 2013: MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램을 사용 하거나 사용 하지 않도록 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable a Microsoft SIP Processing Language (MSPL) server application
ms:assetid: b20af38d-224a-4459-991d-0b7eabb3ca7c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182573(v=OCS.15)
ms:contentKeyID: 48185145
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98dce0363a031a2d56c7d8a7cc479452f4fb0382
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528635"
---
# <a name="enable-or-disable-a-microsoft-sip-processing-language-mspl-server-application-in-lync-server-2013"></a><span data-ttu-id="74cf1-102">Lync Server 2013에서 MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램을 사용 하거나 사용 하지 않도록 설정</span><span class="sxs-lookup"><span data-stu-id="74cf1-102">Enable or disable a Microsoft SIP Processing Language (MSPL) server application in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74cf1-103">_**마지막으로 수정 된 항목:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="74cf1-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="74cf1-104">Lync Server 제어판을 사용 하 여 Lync Server 2013 환경에서 실행 되는 MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="74cf1-104">You can use Lync Server Control Panel to enable or disable Microsoft SIP Processing Language (MSPL) server applications that run in your Lync Server 2013 environment.</span></span> <span data-ttu-id="74cf1-105">이러한 응용 프로그램은 Microsoft Lync 2013 Preview API 대신 스크립트 언어를 사용 하는 스크립트 전용 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="74cf1-105">These applications are script-only applications that use a scripting language instead of the Microsoft Lync 2013 Preview API.</span></span>

<span data-ttu-id="74cf1-106">모든 스크립트를 사용 하거나 사용 하지 않도록 설정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74cf1-106">Not all scripts can be enabled or disabled.</span></span> <span data-ttu-id="74cf1-107">예를 들어 DefaultRouting 스크립트를 사용할 수 있으며 DefaultRouting에 대해이 옵션을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="74cf1-107">For instance, the DefaultRouting script is enabled and this option cannot be changed for DefaultRouting.</span></span>

<div>

## <a name="to-enable-or-disable-an-mspl-server-application"></a><span data-ttu-id="74cf1-108">MSPL 서버 응용 프로그램을 사용 하거나 사용 하지 않도록 설정 하려면</span><span class="sxs-lookup"><span data-stu-id="74cf1-108">To enable or disable an MSPL server application</span></span>

1.  <span data-ttu-id="74cf1-109">RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="74cf1-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="74cf1-110">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="74cf1-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="74cf1-111">Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="74cf1-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="74cf1-112">왼쪽 탐색 표시줄에서 **토폴로지**를 클릭한 다음 **서버 응용 프로그램**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74cf1-112">In the left navigation bar, click **Topology** and then click **Server Application**.</span></span>

4.  <span data-ttu-id="74cf1-113">**서버 응용 프로그램** 페이지에서 필요한 경우 열 머리글을 클릭하여 응용 프로그램을 정렬한 다음 수정할 서버 응용 프로그램을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74cf1-113">On the **Server Application** page, click a column heading to sort the applications, if needed, and then click the server application that you want to modify.</span></span>

5.  <span data-ttu-id="74cf1-114">**동작**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="74cf1-114">Click **Action**.</span></span>

6.  <span data-ttu-id="74cf1-115">**응용 프로그램 사용** 또는 **응용 프로그램 사용 안 함** (스크립트에서이 옵션을 지 원하는 경우)을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="74cf1-115">Click **Enable application** or **Disable application** (that is, if the script supports this option).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="74cf1-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="74cf1-116">See Also</span></span>


[<span data-ttu-id="74cf1-117">Lync Server 2013에서 Microsoft MSPL (SIP 처리 언어) 응용 프로그램을 중요 또는 중요 하지 않음으로 표시</span><span class="sxs-lookup"><span data-stu-id="74cf1-117">Mark a Microsoft SIP Processing Language (MSPL) application as critical or not critical in Lync Server 2013</span></span>](lync-server-2013-mark-a-microsoft-sip-processing-language-mspl-application-as-critical-or-not-critical.md)  


[<span data-ttu-id="74cf1-118">Lync Server 2013에서 MSPL (Microsoft SIP Processing Language) 서버 응용 프로그램 보기</span><span class="sxs-lookup"><span data-stu-id="74cf1-118">View Microsoft SIP Processing Language (MSPL) server applications in Lync Server 2013</span></span>](lync-server-2013-view-microsoft-sip-processing-language-mspl-server-applications.md)  


[<span data-ttu-id="74cf1-119">Lync Server 2013 토폴로지 관리</span><span class="sxs-lookup"><span data-stu-id="74cf1-119">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

