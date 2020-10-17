---
title: 'Lync Server 2013: 파일 저장소 백업'
description: 'Lync Server 2013: 파일 저장소 백업'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up file stores
ms:assetid: 1a7f4e93-aa3d-461e-878e-2c572baa1293
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202167(v=OCS.15)
ms:contentKeyID: 51541449
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba6a92d189c39242be1b2167ffc336d9eb406719
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563284"
---
# <a name="backing-up-file-stores-in-lync-server-2013"></a><span data-ttu-id="78b09-103">Lync Server 2013에서 파일 저장소 백업</span><span class="sxs-lookup"><span data-stu-id="78b09-103">Backing up file stores in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78b09-104">_**마지막으로 수정 된 항목:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="78b09-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="78b09-105">Lync Server 파일 저장소를 백업 하면 Lync Server 구성 요소에서 사용 하는 모든 파일 및 폴더가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="78b09-105">Backing up the Lync Server File Stores includes all the files and folders used by Lync Server components.</span></span>

<div>

## <a name="to-back-up-file-stores"></a><span data-ttu-id="78b09-106">파일 저장소를 백업하려면</span><span class="sxs-lookup"><span data-stu-id="78b09-106">To back up File Stores</span></span>

1.  <span data-ttu-id="78b09-107">Lync Server 파일 저장소의 특정 위치를 찾으려면 토폴로지 작성기를 열고 **파일 저장소** 노드를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="78b09-107">To find the specific locations of your Lync Server File Stores, open Topology Builder and look in the **File stores** node.</span></span>

2.  <span data-ttu-id="78b09-108">Robocopy 또는 다른 파일 시스템 관리 도구를 사용 하 여 각 파일 저장소를 $Backup 저장 \\ 합니다.</span><span class="sxs-lookup"><span data-stu-id="78b09-108">Use Robocopy or another file system management tool to copy each File Store to $Backup\\filestore.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

