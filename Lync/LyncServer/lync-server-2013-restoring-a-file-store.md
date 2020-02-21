---
title: 'Lync Server 2013: 파일 저장소 복원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b73ba97ccadcc5cb34a5dbc3963d80620da8e516
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214824"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a><span data-ttu-id="d0a8b-102">Lync Server 2013에서 파일 저장소 복원</span><span class="sxs-lookup"><span data-stu-id="d0a8b-102">Restoring a file store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d0a8b-103">_**마지막으로 수정 된 항목:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="d0a8b-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="d0a8b-104">Standard Edition에 대 한 파일 저장소는 일반적으로 Standard Edition 서버에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0a8b-104">File Stores for Standard Edition are typically located on the Standard Edition server.</span></span> <span data-ttu-id="d0a8b-105">Enterprise Edition의 파일 저장소는 일반적으로 파일 서버 또는 클러스터에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0a8b-105">File Stores for Enterprise Edition are typically located on a file server or cluster.</span></span> <span data-ttu-id="d0a8b-106">다음 절차에서는 파일 저장소를 복원 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0a8b-106">The following procedure describes how to restore a File Store.</span></span>

<div>

## <a name="to-restore-a-file-store"></a><span data-ttu-id="d0a8b-107">파일 저장소를 복원하려면</span><span class="sxs-lookup"><span data-stu-id="d0a8b-107">To restore a File Store</span></span>

1.  <span data-ttu-id="d0a8b-108">파일 저장소가 실패 하면 $Backup\\ 에서 해당 파일 저장소를 파일 서버 또는 Standard Edition 서버의 파일 저장소 위치에 복사한 다음 해당 폴더를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0a8b-108">If a File Store fails, copy the appropriate File Store from $Backup\\ to the File Store location on the file server or Standard Edition server, and then share the folder.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="d0a8b-109">복원 된 파일 저장소의 경로와 파일 이름은 백업한 파일 저장소와 정확히 동일 해야 파일을 사용 하는 구성 요소에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d0a8b-109">The path and file name for the restored File Store should be exactly the same as the backed up File Store, so that components that use the files can access them.</span></span>

    
    </div>

2.  <span data-ttu-id="d0a8b-110">필요한 경우 파일 저장소에 대 한 Acl (액세스 제어 목록)을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0a8b-110">If necessary, set the access control lists (ACLs) for the File Store.</span></span> <span data-ttu-id="d0a8b-111">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d0a8b-111">At the command line, type:</span></span>
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d0a8b-112">복원 프로세스 중에 토폴로지 작성기를 실행 하지 않은 경우에만이 단계를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d0a8b-112">You need to perform this step only if you have not otherwise run Topology Builder during your restoration process.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

