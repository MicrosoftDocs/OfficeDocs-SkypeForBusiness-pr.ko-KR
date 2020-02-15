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
ms.openlocfilehash: 60c4a3e1563890d64394f3a99141523cb95add38
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a>Lync Server 2013에서 파일 저장소 복원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-18_

Standard Edition에 대 한 파일 저장소는 일반적으로 Standard Edition 서버에 있습니다. Enterprise Edition의 파일 저장소는 일반적으로 파일 서버 또는 클러스터에 있습니다. 다음 절차에서는 파일 저장소를 복원 하는 방법을 설명 합니다.

<div>

## <a name="to-restore-a-file-store"></a>파일 저장소를 복원하려면

1.  파일 저장소가 실패 하면 $Backup\\ 에서 해당 파일 저장소를 파일 서버 또는 Standard Edition 서버의 파일 저장소 위치에 복사한 다음 해당 폴더를 공유 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 복원 된 파일 저장소의 경로와 파일 이름은 백업한 파일 저장소와 정확히 동일 해야 파일을 사용 하는 구성 요소에서 액세스할 수 있습니다.

    
    </div>

2.  필요한 경우 파일 저장소에 대 한 Acl (액세스 제어 목록)을 설정 합니다. 명령줄에 다음을 입력합니다.
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > 복원 프로세스 중에 토폴로지 작성기를 실행 하지 않은 경우에만이 단계를 수행 해야 합니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

