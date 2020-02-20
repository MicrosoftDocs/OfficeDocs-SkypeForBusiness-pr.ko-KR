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
ms.openlocfilehash: 76d7183e60c09729758d7297fd3b6db2cd6622d9
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147571"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a>Lync Server 2013 Standard Edition을 기존 Lync Server 2013 Enterprise에 배포

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-01_

Standard Edition 서버를 기존 Enterprise Edition 배포에 배포 하는 것은 추가 서버 역할을 배포 하는 것과 비슷합니다. Standard Edition 서버를 다른 사이트에 배포 하 여 해당 사이트의 사용자가 WAN (광역 네트워크)을 통해 프런트 엔드 풀이 아닌 Standard Edition 서버에 배치할 수 있도록 할 수 있습니다. 해당 사이트에서 새 사이트 및 서버를 설치 하는 절차는 [Lync Server 2013 설명서 배포](lync-server-2013-deploying-lync-server.md) 의 다른 섹션에 이미 정의 되어 있습니다.

<div id="sectionSection0" class="section">

**새 사이트를 정의하려면**

1.  토폴로지 작성기 시작: **시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.

2.  콘솔 트리에서 **Lync Server 2013**를 마우스 오른쪽 단추로 클릭 한 다음 **새 중앙 사이트**를 클릭 합니다.

3.  **사이트 지정** 페이지에서 사이트 이름을 지정하고 원하는 경우 설명을 입력합니다.

4.  절차에 따라 사이트 토폴로지의 나머지 부분을 정의합니다. 자세한 내용은 [Lync Server 2013에서 토폴로지 정의 및 구성을](lync-server-2013-defining-and-configuring-the-topology.md)참조 하십시오.

5.  업데이트된 토폴로지를 게시합니다. 자세한 내용은 Publish the [topology in The Lync Server 2013](lync-server-2013-publish-the-topology.md)을 참조 하십시오.

6.  Standard Edition 서버를 설정 하 고 설치 합니다.
    
    <div>
    

    > [!Caution]  
    > Standard Edition server만을 사용 하 여 환경을 배포한 경우에는 <STRONG>첫 번째 Standard edition Server 준비</STRONG> 링크를 사용 하 여 새 Standard edition 서버에 초기 데이터베이스 파일을 설치 하는 방법으로 Lync Server 배포 마법사에서 설치 프로세스를 시작 해야 합니다. 기존 Lync Server 2013 배포에 Standard Edition server를 설치할 때는 해당 프로세스를 수행 <STRONG>하지 마십시오</STRONG> .

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

