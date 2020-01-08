---
title: 'Lync Server 2013: 파일 저장소 백업'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Backing up file stores
ms:assetid: 1a7f4e93-aa3d-461e-878e-2c572baa1293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202167(v=OCS.15)
ms:contentKeyID: 51541449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6facef86481e247d1f51d3ec567c8a4ee4bfde8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984058"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-file-stores-in-lync-server-2013"></a><span data-ttu-id="b2ef8-102">Lync Server 2013에서 파일 저장소 백업</span><span class="sxs-lookup"><span data-stu-id="b2ef8-102">Backing up file stores in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2ef8-103">_**마지막으로 수정한 주제:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="b2ef8-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="b2ef8-104">Lync Server 파일 저장소를 백업 하려면 Lync Server 구성 요소에서 사용 하는 모든 파일과 폴더가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-104">Backing up the Lync Server File Stores includes all the files and folders used by Lync Server components.</span></span>

<div>

## <a name="to-back-up-file-stores"></a><span data-ttu-id="b2ef8-105">파일 저장소를 백업 하려면</span><span class="sxs-lookup"><span data-stu-id="b2ef8-105">To back up File Stores</span></span>

1.  <span data-ttu-id="b2ef8-106">Lync Server 파일 저장소의 특정 위치를 찾으려면 토폴로지 작성기를 열고 **파일 저장소** 노드를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-106">To find the specific locations of your Lync Server File Stores, open Topology Builder and look in the **File stores** node.</span></span>

2.  <span data-ttu-id="b2ef8-107">Robocopy 또는 다른 파일 시스템 관리 도구를 사용 하 여 각 파일 저장소를\\$Backup 대상 저장소에 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="b2ef8-107">Use Robocopy or another file system management tool to copy each File Store to $Backup\\filestore.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

