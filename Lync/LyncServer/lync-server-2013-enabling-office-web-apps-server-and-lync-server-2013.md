---
title: 'Lync Server 2013: Office Web Apps 서버 및 Lync Server 2013 사용'
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
ms.openlocfilehash: fb7e35b9347cc38239df7d2e28ddeda05e86cda5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-integration-with-office-web-apps-server-and-lync-server-2013"></a><span data-ttu-id="31eaa-102">Office Web Apps 서버 및 Lync Server 2013 통합 구성</span><span class="sxs-lookup"><span data-stu-id="31eaa-102">Configuring integration with Office Web Apps Server and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31eaa-103">_**마지막으로 수정 된 항목:** 2016-08-19_</span><span class="sxs-lookup"><span data-stu-id="31eaa-103">_**Topic Last Modified:** 2016-08-19_</span></span>

<span data-ttu-id="31eaa-104">Lync Server 2013에서는 Office Web Apps 서버를 활용 하 여 PowerPoint 프레젠테이션을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="31eaa-104">Lync Server 2013 employs Office Web Apps Server to handle PowerPoint presentations.</span></span> <span data-ttu-id="31eaa-105">이 방법의 이점에 대 한 자세한 내용은 [Lync Server 2013의 웹 회의 개요](lync-server-2013-web-conferencing-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="31eaa-105">For information about the advantages to this approach, see [Overview of web conferencing in Lync Server 2013](lync-server-2013-web-conferencing-overview.md).</span></span>

<span data-ttu-id="31eaa-106">이러한 새 기능을 사용 하려면 관리자는 Office Web apps 서버를 설치 하 고 Office Web Apps 서버와 통신 하도록 Lync Server 2013을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31eaa-106">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="31eaa-107">이 문서에서는 Office Web Apps 서버에서 작동 하도록 Lync Server 2013을 구성 하는 방법에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="31eaa-107">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="31eaa-108">이 설명서에서 제공 하지 않는 것은 Office Web Apps 서버를 설치 하는 방법에 대 한 정보입니다. 해당 정보는에서 <http://go.microsoft.com/fwlink/p/?linkid=257525>Microsoft Office Web Apps 배포 웹 사이트를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="31eaa-108">What this documentation does not provide is information on how to install Office Web Apps Server itself; for that information, see the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="31eaa-109">이 가이드에는 Office Web Apps 서버에 대 한 전체 필수 구성 요소 정보가 포함 되어 있습니다. Office Web Apps 서버는 Lync Server, Microsoft SQL Server 또는 다른 서버 응용 프로그램이 실행 되 고 있지 않은 독립 실행형 컴퓨터에 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="31eaa-109">That guide includes complete prerequisite information for Office Web Apps Server; note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, Microsoft SQL Server, or any other server application.</span></span> <span data-ttu-id="31eaa-110">(해당 컴퓨터에 설치 된 Microsoft Office의 버전은 포함 하지 않아야 합니다.) Office Web Apps 서버를 실행 하는 데 사용 되는 모든 컴퓨터에는 .NET Framework 4.5 및 Windows PowerShell 3.0를 비롯 한 특정 소프트웨어 집합도 설치 되어 있어야 합니다. 이러한 요구 사항은 인증서 및 IIS (인터넷 정보 서비스) 구성에 대 한 정보와 함께 Microsoft Office Web Apps 배포 웹 사이트에 자세히 설명 되어 <http://go.microsoft.com/fwlink/p/?linkid=257525>있습니다.</span><span class="sxs-lookup"><span data-stu-id="31eaa-110">(You must not have any version of Microsoft Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0); these requirements, along with information on configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="31eaa-111">Office Web Apps 서버의 최신 반복은 Lync Server 2013에서 지원 되는 Office Online Server 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="31eaa-111">The latest iteration of Office Web Apps Server is named Office Online Server, which is supported by Lync Server 2013.</span></span> <span data-ttu-id="31eaa-112">자세한 내용은 <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">Office Online Server 설명서</A>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="31eaa-112">For more detail, refer to the <A href="https://technet.microsoft.com/library/jj219456(v=office.16).aspx">Office Online Server documentation</A>.</span></span>



</div>

<span data-ttu-id="31eaa-113">이 문서에서는 다음과 같은 내용을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="31eaa-113">This document covers the following topic areas:</span></span>

  - [<span data-ttu-id="31eaa-114">Office Web Apps 서버에서 작동 하도록 Lync Server 2013 구성</span><span class="sxs-lookup"><span data-stu-id="31eaa-114">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>](lync-server-2013-configuring-lync-server-2013-to-work-with-office-web-apps-server.md)

  - [<span data-ttu-id="31eaa-115">역방향 프록시 서버를 사용 하 여 Lync Server 2013에서 Office Web Apps 서버 게시</span><span class="sxs-lookup"><span data-stu-id="31eaa-115">Publishing Office Web Apps Server in Lync Server 2013 using a reverse proxy server</span></span>](lync-server-2013-publishing-office-web-apps-server-using-a-reverse-proxy-server.md)

  - [<span data-ttu-id="31eaa-116">Lync Server 2013에서 Office Web Apps 서버의 구성 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="31eaa-116">Validating the configuration of Office Web Apps Server in Lync Server 2013</span></span>](lync-server-2013-validating-the-configuration-of-office-web-apps-server.md)

  - [<span data-ttu-id="31eaa-117">Office Web Apps 서버에서 사용할 Lync Server 2013의 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="31eaa-117">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>](lync-server-2013-configuring-clients-for-use-with-office-web-apps-server.md)

</div>

<span> </span>

</div>

</div>

</div>

