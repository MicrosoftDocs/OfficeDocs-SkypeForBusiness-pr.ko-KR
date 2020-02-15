---
title: 'Lync Server 2013: DFS 파일 저장소 구성'
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
ms.openlocfilehash: d5ce6be2a3fce1f334e9e4b1d14ea41a3dd57a6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028649"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a>Lync Server 2013에 대해 DFS 파일 저장소 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2016-05-23_

Lync Server 2013에서는 DFS (분산 파일 시스템)에서 파일 공유를 사용할 지를 지원 합니다. Windows Server 2008 용 DFS에 대 한 자세한 내용은 Windows Server 2008에 대 한 DFS 단계별 가이드를 참조 하십시오 [http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835). DFS를 사용 하려면 Lync Server 2013에 다음이 필요 합니다.

  - 네임스페이스가 도메인 기반이어야 함

  - 모든 네임스페이스 서버가 Windows 2008 이상을 실행해야 함

Lync Server 2013을 설치 하려면 공유 폴더에 대 한 사용 권한이 관리자에 게 모든 권한을 허용 해야 합니다. 그러면 Lync Server 2013에서 NTFS 파일 권한을 사용 하 여 폴더에 ACL을 부여 합니다. 상속된 DFS 공유 사용 권한은 액세스를 제한하는 데 사용되지 않습니다.

파일 공유 요구 사항에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync Server 2013의 파일 저장소 지원을](lync-server-2013-file-storage-support.md) 참조 하십시오.

<div>


> [!NOTE]  
> 비 DFS 공유 구성에 대 한 정보를 볼 수 있습니다. 그렇다면 <A href="lync-server-2013-hardware-setup.md">Lync Server 2013에 대 한 하드웨어 설정을</A>확인 하세요.



</div>

다음 절차에서는 DFS 설정 가이드에 설명된 대로 DFS 네임스페이스 마법사를 사용하여 공유 폴더 사용 권한을 올바르게 구성하는 방법에 대해 설명합니다.

<div>

## <a name="to-configure-shared-folder-permissions"></a>공유 폴더 사용 권한을 구성하려면

1.  **시작**을 클릭하고 **모든 프로그램**, **관리 도구**를 차례로 가리킨 다음 **DFS 관리**를 클릭합니다.

2.  DFS 관리 스냅인의 콘솔 트리에서 해당 네임스페이스 서버(예: filesrv1.contoso.com)를 마우스 오른쪽 단추로 클릭한 다음 **설정 편집**을 클릭합니다.

3.  **공유 폴더 사용 권한**을 선택합니다.

4.  **사용자 지정 권한 사용**을 선택합니다.

5.  관리자 그룹에 대해 **허용** 아래에서 다음을 선택합니다.
    
      - **모든 권한**
    
      - **변경 사항**
    
      - **읽기**

6.  **적용**을 클릭한 다음 **확인**을 클릭합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

