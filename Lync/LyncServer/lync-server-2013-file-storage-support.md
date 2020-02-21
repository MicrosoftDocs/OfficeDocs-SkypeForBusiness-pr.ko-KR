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
ms.openlocfilehash: 8b870aa22d9dea13e84f045af8fc6fe800fb3d55
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207264"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="file-storage-support-in-lync-server-2013"></a><span data-ttu-id="5919a-102">Lync Server 2013의 파일 저장소 지원</span><span class="sxs-lookup"><span data-stu-id="5919a-102">File storage support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5919a-103">_**마지막으로 수정 된 항목:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="5919a-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="5919a-104">Lync Server 2013에서는 모든 파일 저장소에 대해 동일한 파일 저장소를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="5919a-104">Lync Server 2013 uses the same file store for all file storage.</span></span> <span data-ttu-id="5919a-105">파일 저장소 지원에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5919a-105">File storage support includes the following:</span></span>

  - <span data-ttu-id="5919a-106">DFS (분산 파일 시스템)를 포함 하는 DAS (직접 연결 된 저장소) 또는 SAN (저장 영역 네트워크), 파일 저장용 RAID (독립 디스크)에 있는 파일 공유</span><span class="sxs-lookup"><span data-stu-id="5919a-106">A file share on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS), and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="5919a-107">저장소 요구 사항에 대 한 자세한 내용은 계획 설명서에서 lync server [2013의 디렉터](lync-server-2013-hardware-and-software-requirements-for-the-director.md) 에 대 한 [프런트 엔드 서버, 인스턴트 메시징 및 현재 2013 상태에 대 한 기술 요구 사항을](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5919a-107">For details about storage requirements, see [Technical requirements for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-technical-requirements-for-front-end-servers-instant-messaging-and-presence.md) and [Hardware and software requirements for the Director in Lync Server 2013](lync-server-2013-hardware-and-software-requirements-for-the-director.md) in the Planning documentation.</span></span> <span data-ttu-id="5919a-108">Windows Server 용 DFS 2008 운영 체제에 대 한 자세한 내용은 Windows Server 2008에 대 한 DFS 단계별 가이드를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835).</span><span class="sxs-lookup"><span data-stu-id="5919a-108">For details about DFS for Windows Server 2008 operating system, see the DFS Step-by-Step Guide for Windows Server 2008 at [https://go.microsoft.com/fwlink/p/?linkId=202835](https://go.microsoft.com/fwlink/p/?linkid=202835).</span></span>

  - <span data-ttu-id="5919a-109">파일 공유에 대 한 공유 클러스터</span><span class="sxs-lookup"><span data-stu-id="5919a-109">A shared cluster for the file share.</span></span> <span data-ttu-id="5919a-110">공유 클러스터를 사용 하는 경우 Windows Server 2008 또는 Windows Server 2008 R2를 실행 하는 클러스터 서버를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5919a-110">If you use a shared cluster, you should use cluster servers running Windows Server 2008 or Windows Server 2008 R2.</span></span> <span data-ttu-id="5919a-111">이전 버전의 Windows를 실행 하는 클러스터 서버를 사용 하면 사용 권한 문제가 발생 하 여 일부 기능을 사용 하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5919a-111">Using cluster servers running an older version of Windows may result in permission issues that prevent some features from being available.</span></span> <span data-ttu-id="5919a-112">클러스터 관리자를 사용 하 여 파일 공유를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="5919a-112">Use the Cluster Administrator to create the file shares.</span></span> <span data-ttu-id="5919a-113">클러스터 관리자 사용에 대 한 자세한 내용은 Microsoft 기술 자료 문서 284838, "cluster.exe를 사용 하 여 서버 클러스터 파일 공유를 만드는 방법"을 참조 [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899)하십시오.</span><span class="sxs-lookup"><span data-stu-id="5919a-113">For details about using the Cluster Administrator, see Microsoft Knowledge Base article 284838, "How to Create a Server Cluster File Share with Cluster.exe" at [https://go.microsoft.com/fwlink/p/?linkId=140899](https://go.microsoft.com/fwlink/p/?linkid=140899).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

