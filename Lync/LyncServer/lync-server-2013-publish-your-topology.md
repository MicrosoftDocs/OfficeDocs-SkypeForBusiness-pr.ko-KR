---
title: 'Lync Server 2013: 토폴로지 게시'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bd542db6acedbec75e475045ae2ace6d63d5469
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983249"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-your-topology-in-lync-server-2013"></a>Lync Server 2013에서 토폴로지 게시

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-08_

토폴로지 작성기를 사용 하 여 토폴로지를 빌드할 때마다 중앙 관리 저장소의 데이터베이스에 토폴로지를 게시 하 여 Lync Server 2013을 배포 하는 데 데이터를 사용할 수 있도록 해야 합니다. 토폴로지를 게시 하려면 다음 절차를 사용 합니다.

<div>

## <a name="to-publish-the-topology"></a>토폴로지를 게시 하려면

1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  토폴로지 작성기의 콘솔 트리에서 **Lync 2013**을 마우스 오른쪽 단추로 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.

3.  마법사의 **시작** 페이지에서 **다음**을 클릭 합니다.

4.  **CMS 스토어 페이지를 발견 한 토폴로지 작성기** 에서 **다음**을 클릭 합니다.

5.  **다른 데이터베이스 만들기** 페이지에서 **다음**을 클릭 합니다.

6.  상태가 데이터베이스를 성공적으로 생성 했음을 나타내는 경우 다음을 수행 합니다.
    
      - 로그를 보려면 **로그 보기**를 클릭 합니다.
    
      - 마법사를 닫으려면 **마침을**클릭 합니다.
        
        <div>
        

        > [!IMPORTANT]  
        > Edge 서버 또는 Edge 풀의 새로 설치 인 경우에는 기존 프런트 엔드 서버, 프런트 엔드 풀 또는 Standard Edition 서버에서 Edge 서버 구성을 내보내야 합니다. 구성을 내보내려면 <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">Lync Server 2013 토폴로지 내보내기를 참조 하 여 edge 설치에 대 한 외부 미디어에 복사</A>합니다. Lync Server 배포 마법사를 통해 Edge 서버의 설정 및 배포 단계 중에 외부 미디어 또는 네트워크 공유에서 구성 파일을 가져옵니다.<BR>Edge 서버가 작동 중이 고 로컬 구성 관리 저장소 데이터베이스가 내부 배포로 복제 되는 경우에는 Lync Server 2013 구성에 대 한 후속 업데이트가 게시 되 고 Edge 서버에 복제 됩니다.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

