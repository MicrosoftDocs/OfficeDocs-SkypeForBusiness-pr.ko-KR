---
title: 'Lync Server 2013: 파일 저장소 복원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring a file store
ms:assetid: 89916fc6-31d3-4c7f-9eaf-c02584761ef4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202180(v=OCS.15)
ms:contentKeyID: 51541491
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dc9f1bae4e1a9a84815e576267a15155bec227da
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984537"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-a-file-store-in-lync-server-2013"></a>Lync Server 2013에서 파일 저장소 복원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-18_

스탠더드 버전의 파일 저장소는 일반적으로 Standard Edition 서버에 있습니다. 엔터프라이즈 에디션에 대 한 파일 저장소는 일반적으로 파일 서버나 클러스터에 있습니다. 다음 절차에서는 파일 저장소를 복원 하는 방법을 설명 합니다.

<div>

## <a name="to-restore-a-file-store"></a>파일 저장소 복원

1.  파일 저장소에 오류가 발생 하는 경우 $Backup\\ 에서 해당 파일 저장소를 파일 서버 또는 Standard Edition 서버의 파일 저장소 위치로 복사한 다음 폴더를 공유 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 복원 된 파일 저장소의 경로와 파일 이름은 백업한 파일 저장소와 정확히 동일 해야 파일을 사용 하는 구성 요소에서 액세스할 수 있습니다.

    
    </div>

2.  필요한 경우 파일 저장소에 대 한 Acl (액세스 제어 목록)을 설정 합니다. 명령줄에 다음을 입력 합니다.
    
        Enable-CsTopology
    
    <div>
    

    > [!NOTE]  
    > 복원 프로세스 중에 토폴로지 작성기를 실행 하지 않는 경우에만이 단계를 수행 해야 합니다.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

