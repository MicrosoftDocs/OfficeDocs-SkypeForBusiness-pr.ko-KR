---
title: 'Lync Server 2013: 기존 Lync Server 2013 Enterprise에 Lync Server 2013 Standard Edition 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6467ae9eb3c4d5159181a2d022c060b0b9f1fec9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758022"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a>기존 Lync Server 2013 Enterprise에 Lync Server 2013 Standard Edition 배포

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-01_

기존 엔터프라이즈 버전 배포에 표준 버전 서버를 배포 하는 것은 추가 서버 역할 배포와 유사 합니다. 스탠더드 버전 서버는 다른 사이트에 배포 되어 해당 사이트의 사용자를 WAN (광역 네트워크)의 프런트 엔드 풀 보다는 표준 버전 서버에서 공유할 수 있습니다. 이 사이트에 새 사이트와 서버를 설치 하는 절차는 [Lync Server 2013 설명서 배포](lync-server-2013-deploying-lync-server.md) 의 다른 섹션에 이미 정의 되어 있습니다.

<div id="sectionSection0" class="section">

**새 사이트를 정의 하려면**

1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft Lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  콘솔 트리에서 **Lync Server 2013**을 마우스 오른쪽 단추로 클릭 한 다음 **새 중앙 사이트**를 클릭 합니다.

3.  **사이트 확인** 페이지에서 사이트에 이름을 지정 하 고 원하는 경우 설명을 입력 합니다.

4.  나머지 사이트 토폴로지를 정의 하는 절차를 따릅니다. 자세한 내용은 [Lync Server 2013에서 토폴로지 정의 및 구성을](lync-server-2013-defining-and-configuring-the-topology.md)참조 하세요.

5.  업데이트 된 토폴로지를 게시 합니다. 자세한 내용은 [Lync Server 2013에서 토폴로지 게시](lync-server-2013-publish-the-topology.md)를 참조 하세요.

6.  스탠더드 버전 서버 설정 및 설치
    
    <div>
    

    > [!Caution]  
    > Standard Edition server만 사용 하 여 환경을 배포한 경우에는 Lync Server 배포 마법사에서 <STRONG>첫 번째 Standard edition Server 준비</STRONG> 링크를 사용 하 여 초기 데이터베이스 파일을 새 Standard edition 서버에 설치 하 여 설치 프로세스를 시작 합니다. 기존 Lync Server 2013 배포에 Standard Edition server를 설치할 때는 해당 프로세스를 따르지 <STRONG>마세요</STRONG> .

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

