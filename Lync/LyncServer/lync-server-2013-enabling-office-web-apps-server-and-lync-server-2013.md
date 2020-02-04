---
title: 'Lync Server 2013: Office Online Server 및 Lync Server 2013 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Office Web Apps Server and Lync Server 2013
ms:assetid: 3370ab55-9949-4f32-b88b-5cffed6aaad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204792(v=OCS.15)
ms:contentKeyID: 48183790
ms.date: 08/19/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37715182ba704f71bad463044ec9b47cea8f777b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735788"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a><span data-ttu-id="ac744-102">Office Online Server 및 Lync Server 2013과 통합 구성</span><span class="sxs-lookup"><span data-stu-id="ac744-102">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac744-103">_**마지막으로 수정한 주제:** 2016-08-19_</span><span class="sxs-lookup"><span data-stu-id="ac744-103">_**Topic Last Modified:** 2016-08-19_</span></span>

<span data-ttu-id="ac744-104">Lync Server 2013는 Office Web Apps 서버를 활용 하 여 PowerPoint 프레젠테이션을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac744-104">Lync Server 2013 employs Office Web Apps Server to handle PowerPoint presentations.</span></span> <span data-ttu-id="ac744-105">이 방법의 이점에 대 한 자세한 내용은 [Lync Server 2013의 웹 회의 개요](lync-server-2013-web-conferencing-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ac744-105">For information about the advantages to this approach, see [Overview of web conferencing in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span></span>

<span data-ttu-id="ac744-106">이러한 새 기능을 사용 하려면 관리자가 Office Web Apps 서버를 설치 하 고 Office Web Apps 서버와 통신 하도록 Lync Server 2013를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac744-106">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="ac744-107">이 문서는 Office Web Apps 서버에서 작동 하도록 Lync Server 2013를 구성 하는 방법에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac744-107">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="ac744-108">이 설명서에는 Office Web Apps 서버 자체를 설치 하는 방법에 대 한 정보가 나와 있지 않습니다. 해당 정보는의 Microsoft Office Web Apps 배포 웹 사이트를 참조 <http://go.microsoft.com/fwlink/p/?linkid=257525>하세요.</span><span class="sxs-lookup"><span data-stu-id="ac744-108">What this documentation does not provide is information on how to install Office Web Apps Server itself; for that information, see the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="ac744-109">이 가이드에는 Office Web Apps 서버에 대 한 전체 필수 구성 요소 정보가 포함 되어 있습니다. Office Web Apps 서버는 Lync Server, Microsoft SQL Server 또는 기타 서버 응용 프로그램을 실행 하지 않는 독립 실행형 컴퓨터에 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac744-109">That guide includes complete prerequisite information for Office Web Apps Server; note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, Microsoft SQL Server, or any other server application.</span></span> <span data-ttu-id="ac744-110">(해당 컴퓨터에 Microsoft Office 버전을 설치 하지 않아야 합니다.) Office Web Apps Server를 실행 하는 데 사용 되는 컴퓨터에는 .NET Framework 4.5 및 Windows PowerShell 3.0을 포함 하 여 특정 소프트웨어 집합도 설치 되어 있어야 합니다. 이러한 요구 사항은 인증서와 IIS (인터넷 정보 서비스)를 구성 하는 방법에 대 한 자세한 내용은 Microsoft Office Web Apps 배포 웹 사이트에서 자세히 <http://go.microsoft.com/fwlink/p/?linkid=257525>설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac744-110">(You must not have any version of Microsoft Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0); these requirements, along with information on configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ac744-111">Office Web Apps Server의 최신 이터레이션에는 Lync Server 2013에서 지원 되는 Office Online Server 라는 이름이 지정 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac744-111">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Lync Server 2013.</span></span> <span data-ttu-id="ac744-112">자세한 내용은 <A href="https://technet.microsoft.com/en-us/library/jj219456(v=office.16).aspx">Office Online 서버 설명서</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ac744-112">For more detail, refer to the <A href="https://technet.microsoft.com/en-us/library/jj219456(v=office.16).aspx">Office Online Server documentation</A>.</span></span>



</div>

<span data-ttu-id="ac744-113">이 문서에서는 다음 항목 영역에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac744-113">This document covers the following topic areas:</span></span>

  - [<span data-ttu-id="ac744-114">Office Web Apps 서버에서 작동 하도록 Lync Server 2013 구성</span><span class="sxs-lookup"><span data-stu-id="ac744-114">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [<span data-ttu-id="ac744-115">리버스 프록시 서버를 사용 하 여 Lync Server 2013에서 Office Web Apps 서버 게시</span><span class="sxs-lookup"><span data-stu-id="ac744-115">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [<span data-ttu-id="ac744-116">Lync Server 2013에서 Office Web Apps 서버의 구성 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="ac744-116">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [<span data-ttu-id="ac744-117">Office Web Apps 서버에서 사용할 Lync Server 2013의 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="ac744-117">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

