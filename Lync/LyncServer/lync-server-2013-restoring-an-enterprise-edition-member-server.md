---
title: 'Lync Server 2013: Enterprise Edition 구성원 서버 복원'
description: 'Lync Server 2013: Enterprise Edition 구성원 서버를 복원 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring an Enterprise Edition member server
ms:assetid: d960b19c-2104-4719-b736-0d940f254d42
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202191(v=OCS.15)
ms:contentKeyID: 51541523
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f9838f030205d92988e185798d982f835122c9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576054"
---
# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a>Lync Server 2013에서 Enterprise Edition 구성원 서버 복원

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-18_

다음 서버 역할 중 하나를 실행 하는 서버가 실패 하면이 항목의 절차에 따라 서버를 복원 합니다. 여러 서버가 개별적으로 실패하면 각 서버에 대해 절차를 수행합니다.

  - Front End Server(프런트 엔드 서버)

  - 중재 서버

  - Director

  - 영구적 채팅 서버

  - 에지 서버

<div>


> [!TIP]  
> 복원을 시작 하기 전에 시스템의 이미지 복사본을 사용 하는 것이 좋습니다. 복원 중에 문제가 발생 하는 경우를 대비 하 여이 이미지를 롤백 지점으로 사용할 수 있습니다. 운영 체제 및 SQL Server를 설치 하 고 인증서를 복원 하거나 reenroll 후 이미지 복사본을 사용할 수 있습니다.



</div>

<div>

## <a name="to-restore-a-member-server"></a>구성원 서버를 복원하려면

1.  오류가 발생 한 서버와 FQDN (정규화 된 도메인 이름)이 동일한 깨끗 한 서버 또는 새 서버로 시작 하 고, 운영 체제를 설치한 후 인증서를 복원 하거나 reenroll 합니다.
    
    <div>
    

    > [!NOTE]  
    > 조직의 서버 배포 절차에 따라 이 단계를 수행합니다.

    
    </div>

2.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 복원 중인 서버에 로그온 합니다.

3.  Lync Server 설치 폴더 또는 미디어로 이동 하 여 \\ setup amd64Setup.exe에 있는 Lync Server 배포 마법사를 시작 합니다 \\ \\ .

4.  배포 마법사에 따라 다음을 수행합니다.
    
    1.  **1단계: 로컬 구성 저장소 설치**를 실행하여 로컬 구성 파일을 설치합니다.
    
    2.  **2 단계: lync Server 구성 요소 설치 또는 제거** 를 실행 하 여 lync server 서버 역할을 설치 합니다.
    
    3.  **3단계: 인증서 요청, 설치 또는 지정**을 실행하여 인증서를 지정합니다.
    
    4.  **4단계: 서비스 시작**을 실행하여 서버에서 서비스를 시작합니다.
    
    배포 마법사를 실행 하는 방법에 대 한 자세한 내용은 복원 중인 서버 역할에 대 한 배포 설명서를 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

