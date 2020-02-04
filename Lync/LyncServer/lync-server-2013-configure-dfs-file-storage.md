---
title: 'Lync Server 2013: 파일 저장소 구성'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bbb932a602ad1fc49907be9c5ab2777bc7a415f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739338"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a>Lync Server 2013의 파일 저장소 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2016-05-23_

Lync Server 2013는 DFS (분산 파일 시스템)에서 파일 공유 사용을 지원 합니다. Windows Server 2008의 DFS에 대 한 자세한 내용은 Windows Server 2008의 DFS for 단계별 가이드를 참조 하세요 [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835). DFS를 사용 하려면 Lync Server 2013에 다음이 필요 합니다.

  - 네임 스페이스는 도메인 기반입니다.

  - 모든 네임 스페이스 서버가 최소 Windows 2008를 실행 하 고 있습니다.

Lync Server 2013을 설정 하려면 공유 폴더에 대 한 사용 권한이 관리자에 게 모든 권한을 허용 해야 합니다. 그러면 Lync Server 2013에서 NTFS 파일 사용 권한을 사용 하 여 폴더에 ACL을 적용할 수 있습니다. 상속 된 DFS 공유 사용 권한은 액세스를 제한 하는 데 사용 되지 않습니다.

파일 공유 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync Server 2013에서 파일 저장소 지원을](lync-server-2013-file-storage-support.md) 참조 하세요.

<div>


> [!NOTE]  
> 비 DFS 공유 구성에 대 한 정보를 찾을 수 있습니다. 그렇다면 <A href="lync-server-2013-hardware-setup.md">Lync Server 2013에 대 한 하드웨어 설정을</A>확인 합니다.



</div>

다음 절차에서는 dfs 네임 스페이스 마법사를 사용 하 여 공유 폴더 권한을 올바르게 구성 하는 방법을 설명 합니다 (DFS 설정 가이드에서 설명).

<div>

## <a name="to-configure-shared-folder-permissions"></a>공유 폴더 사용 권한을 구성 하려면

1.  **시작**을 클릭 하 고 **모든 프로그램**, **관리 도구**를 차례로 가리킨 다음 **DFS 관리**를 클릭 합니다.

2.  DFS 관리 스냅인의 콘솔 트리에서 네임 스페이스 서버 (예: filesrv1.contoso.com)를 마우스 오른쪽 단추로 클릭 한 다음 **설정 편집**을 클릭 합니다.

3.  **공유 폴더 사용 권한을**선택 합니다.

4.  **사용자 지정 권한 사용**을 선택 합니다.

5.  관리자 그룹의 경우 **허용**아래에서 다음을 선택 합니다.
    
      - **모든 권한**
    
      - **바뀌지**
    
      - **자세한**

6.  **적용**을 클릭 한 다음 **확인**을 클릭 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

