---
title: Lync Server 2013 파일 저장소 지원
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: File storage support
ms:assetid: ed66430d-3c19-4267-938c-956a51005073
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399073(v=OCS.15)
ms:contentKeyID: 48185743
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 000f3357c8b30b83a2d2cecf74bdbec44d867d96
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a><span data-ttu-id="9c302-102">Lync Server 2013의 파일 저장소 지원</span><span class="sxs-lookup"><span data-stu-id="9c302-102">File storage support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9c302-103">_**마지막으로 수정한 주제:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="9c302-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="9c302-104">Lync Server 2013는 모든 파일 저장소에 동일한 파일 저장소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c302-104">Lync Server 2013 uses the same file store for all file storage.</span></span> <span data-ttu-id="9c302-105">파일 저장소 지원에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9c302-105">File storage support includes the following:</span></span>

  - <span data-ttu-id="9c302-106">파일 저장소 (분산 파일 시스템) 또는 DFS (저장 영역 네트워크)를 포함 하 여 파일을 공유 하는 파일과 저장소에 대 한 독립 디스크 (RAID)의 중복 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9c302-106">A file share on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS), and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="9c302-107">저장소 요구 사항에 대 한 자세한 내용은 [Lync server 2013의 프런트 엔드 서버, 메신저 대화, 현재 상태](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) , 그리고 계획 설명서의 [lync Server 2013에서 디렉터에 대 한 하드웨어 및 소프트웨어 요구](lync-server-2013-hardware-and-software-requirements-for-the-director.md) 사항에 대해 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="9c302-107">For details about storage requirements, see [Technical requirements for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) and [Hardware and software requirements for the Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in the Planning documentation.</span></span> <span data-ttu-id="9c302-108">Windows Server 용 DFS 2008 운영 체제에 대 한 자세한 내용은 Windows Server 2008의 DFS for 단계별 가이드를 참조 하세요 [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).</span><span class="sxs-lookup"><span data-stu-id="9c302-108">For details about DFS for Windows Server 2008 operating system, see the DFS Step-by-Step Guide for Windows Server 2008 at [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835).</span></span>

  - <span data-ttu-id="9c302-109">파일 공유에 대 한 공유 클러스터</span><span class="sxs-lookup"><span data-stu-id="9c302-109">A shared cluster for the file share.</span></span> <span data-ttu-id="9c302-110">공유 클러스터를 사용 하는 경우 Windows Server 2008 또는 Windows Server 2008 R2를 실행 하는 클러스터 서버를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="9c302-110">If you use a shared cluster, you should use cluster servers running Windows Server 2008 or Windows Server 2008 R2.</span></span> <span data-ttu-id="9c302-111">이전 버전의 Windows를 실행 하는 클러스터 서버를 사용 하면 사용 권한 문제가 발생 하 여 일부 기능을 사용할 수 없게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9c302-111">Using cluster servers running an older version of Windows may result in permission issues that prevent some features from being available.</span></span> <span data-ttu-id="9c302-112">클러스터 관리자를 사용 하 여 파일 공유를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="9c302-112">Use the Cluster Administrator to create the file shares.</span></span> <span data-ttu-id="9c302-113">클러스터 관리자 사용에 대 한 자세한 내용은 Microsoft 기술 자료 문서 284838, "cluster.exe를 사용 하 여 서버 클러스터 파일 공유를 만드는 방법"을 참조 [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899)하세요.</span><span class="sxs-lookup"><span data-stu-id="9c302-113">For details about using the Cluster Administrator, see Microsoft Knowledge Base article 284838, "How to Create a Server Cluster File Share with Cluster.exe" at [http://go.microsoft.com/fwlink/p/?linkId=140899](http://go.microsoft.com/fwlink/p/?linkid=140899).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

