---
title: 'Lync Server 2013: Lync 대화방 시스템 관리 웹 포털 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying the Lync Room System Administrative Web Portal
ms:assetid: ecba5b36-632e-40b9-9c2e-ab825baf7a46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn436324(v=OCS.15)
ms:contentKeyID: 56737621
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7f62a5c7fde401452744abba5f4b6dfec175da2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740808"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a><span data-ttu-id="ea07f-102">Lync Server 2013에서 Lync 채팅방 시스템 관리 웹 포털 배포</span><span class="sxs-lookup"><span data-stu-id="ea07f-102">Deploying the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ea07f-103">_**마지막으로 수정한 주제:** 2015-05-04_</span><span class="sxs-lookup"><span data-stu-id="ea07f-103">_**Topic Last Modified:** 2015-05-04_</span></span>

<span data-ttu-id="ea07f-104">Microsoft Lync Server 2013 Lync 대화방 시스템 (LRS) 관리 웹 포털은 조직에서 Lync 대화방 시스템 회의실을 유지 관리 하는 데 사용할 수 있는 웹 포털입니다.</span><span class="sxs-lookup"><span data-stu-id="ea07f-104">The Microsoft Lync Server 2013 Lync Room System (LRS) Administrative Web Portal is a web portal that organizations can use to maintain their Lync Room System conference rooms.</span></span> <span data-ttu-id="ea07f-105">관리자는 LRS 관리 웹 포털을 사용 하 여 연결 된 오디오/비디오 장치를 모니터링 하는 등의 LRS 상태를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea07f-105">Administrators can use the LRS Administrative Web Portal to monitor LRS health, for example by monitoring audio/video devices that are connected.</span></span> <span data-ttu-id="ea07f-106">이 포털을 사용 하면 관리자가 진단 정보를 원격으로 수집 하 여 회의실 상태를 모니터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea07f-106">With this portal, administrators can remotely collect diagnostic information to monitor conference room health.</span></span>

<span data-ttu-id="ea07f-107">LRS 관리 웹 포털은 모든 Lync 프런트 엔드 서버에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea07f-107">The LRS Administrative Web Portal is deployed on every Lync Front End Server.</span></span> <span data-ttu-id="ea07f-108">이 가이드에서는 LRS 관리 웹 포털을 설치 하 고 구성 하는 방법에 대 한 관리자를 위한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea07f-108">This guide provides instructions for administrators about how to install and configure the LRS Administrative Web Portal.</span></span> <span data-ttu-id="ea07f-109">Lync server 관리에 대 한 지식을 보유 하 고 있는 관리자와 Lync Server 토폴로지를 수정할 수 있는 관리자 권한이 있는 사용자를 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ea07f-109">It is intended for administrators who have knowledge of Lync Server administration, and who have administrator user rights to modify the Lync Server topology.</span></span>

<span data-ttu-id="ea07f-110">LRS 관리 웹 포털이 서버에 배포 된 후 관리자는 해당 컴퓨터 또는 랩톱에서 사이트에 로그온 하 여 모든 LRS 채팅방의 상태를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea07f-110">After LRS Administrative Web Portal is deployed on the server, administrators can check the status of all LRS rooms by logging on to the site from their own computers or laptops.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ea07f-111">Microsoft Lync Server 2013 배포에 LRS 관리 웹 포털을 설치 하는 경우 <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">Lync server 2013 용 Microsoft Lync 채팅방 시스템 관리 웹 포털</A>을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea07f-111">When you install the LRS Administrative Web Portal in a Microsoft Lync Server 2013 deployment, you should use the <A href="http://go.microsoft.com/fwlink/p/?linkid=544806">Microsoft Lync Room System Administrative Web Portal for Lync Server 2013</A>.</span></span><BR><span data-ttu-id="ea07f-112">LRS 관리 웹 포털의 새 버전은 비즈니스용 Skype Server 2015에서 사용할 수 있지만, 비즈니스용 Skype Server 2015을 배포한 경우에만 해당 버전을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea07f-112">A new version of the LRS Administrative Web Portal is available for Skype for Business Server 2015, but you should not install that version unless you have deployed Skype for Business Server 2015.</span></span> <span data-ttu-id="ea07f-113"><A href="http://go.microsoft.com/fwlink/?linkid=544807">비즈니스용 Skype 서버 2015에 대 한 Microsoft Lync 채팅방 시스템 관리 웹 포털</A>을 다운로드 하세요.</span><span class="sxs-lookup"><span data-stu-id="ea07f-113">Download the <A href="http://go.microsoft.com/fwlink/?linkid=544807">Microsoft Lync Room System Administrative Web Portal for Skype for Business Server 2015</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ea07f-114">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="ea07f-114">In This Section</span></span>

[<span data-ttu-id="ea07f-115">Lync 채팅방 시스템 관리 웹 포털에 대한 Lync Server 2013 환경 구성</span><span class="sxs-lookup"><span data-stu-id="ea07f-115">Configuring your Lync Server 2013 environment for the Lync Room System Administrative Web Portal</span></span>](lync-server-2013-configuring-your-environment-for-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="ea07f-116">Lync Server 2013에서 Lync 채팅방 시스템 관리 웹 포털 설치</span><span class="sxs-lookup"><span data-stu-id="ea07f-116">Installing the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-installing-the-lync-room-system-administrative-web-portal.md)

[<span data-ttu-id="ea07f-117">Lync Server 2013에서 Lync 채팅방 시스템 관리 웹 포털 사용</span><span class="sxs-lookup"><span data-stu-id="ea07f-117">Using the Lync Room System Administrative Web Portal in Lync Server 2013</span></span>](lync-server-2013-using-the-lync-room-system-administrative-web-portal.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ea07f-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea07f-118">See Also</span></span>


[<span data-ttu-id="ea07f-119">Lync Server 2013에서 회의 배포</span><span class="sxs-lookup"><span data-stu-id="ea07f-119">Deploying conferencing in Lync Server 2013</span></span>](lync-server-2013-deploying-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

