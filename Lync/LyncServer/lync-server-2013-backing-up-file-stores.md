---
title: 'Lync Server 2013: 파일 저장소 백업'
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
ms.openlocfilehash: cceaffb2ecf0ac1b133e01bd04f50f9950cc0dec
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backing-up-file-stores-in-lync-server-2013"></a><span data-ttu-id="f8c28-102">Lync Server 2013에서 파일 저장소 백업</span><span class="sxs-lookup"><span data-stu-id="f8c28-102">Backing up file stores in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8c28-103">_**마지막으로 수정 된 항목:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="f8c28-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="f8c28-104">Lync Server 파일 저장소를 백업 하면 Lync Server 구성 요소에서 사용 하는 모든 파일 및 폴더가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f8c28-104">Backing up the Lync Server File Stores includes all the files and folders used by Lync Server components.</span></span>

<div>

## <a name="to-back-up-file-stores"></a><span data-ttu-id="f8c28-105">파일 저장소를 백업하려면</span><span class="sxs-lookup"><span data-stu-id="f8c28-105">To back up File Stores</span></span>

1.  <span data-ttu-id="f8c28-106">Lync Server 파일 저장소의 특정 위치를 찾으려면 토폴로지 작성기를 열고 **파일 저장소** 노드를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8c28-106">To find the specific locations of your Lync Server File Stores, open Topology Builder and look in the **File stores** node.</span></span>

2.  <span data-ttu-id="f8c28-107">Robocopy 또는 다른 파일 시스템 관리 도구를 사용 하 여 각 파일 저장소를\\$Backup 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f8c28-107">Use Robocopy or another file system management tool to copy each File Store to $Backup\\filestore.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

