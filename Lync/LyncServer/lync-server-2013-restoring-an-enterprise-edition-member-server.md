---
title: 'Lync Server 2013: Enterprise Edition 구성원 서버 복원'
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
ms.openlocfilehash: e870b68d1252ea5a203b3c334299fb65b6a56512
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-an-enterprise-edition-member-server-in-lync-server-2013"></a>Lync Server 2013에서 Enterprise Edition 구성원 서버 복원

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-18_

다음 서버 역할 중 하나를 실행 하는 서버가 실패 하는 경우이 항목의 절차에 따라 서버를 복원 합니다. 여러 서버가 독립적으로 작동 하지 않는 경우 각 서버에 대 한 절차를 따르세요.

  - 프런트 엔드 서버

  - 중재 서버

  - Director

  - 영구적 채팅 서버

  - Edge 서버

<div>


> [!TIP]  
> 복원을 시작 하기 전에 시스템의 이미지 복사본을 사용 하는 것이 좋습니다. 복원 중에 문제가 발생 하는 경우이 이미지를 롤백 시점으로 사용할 수 있습니다. 운영 체제 및 SQL Server를 설치 하 고 인증서를 복원 하거나 reenroll 이미지 복사본을 사용할 수 있습니다.



</div>

<div>

## <a name="to-restore-a-member-server"></a>구성원 서버를 복원 하려면

1.  실패 한 서버와 FQDN (정규화 된 도메인 이름)이 동일한 깨끗 한 새 서버를 사용 하 여 시작 하 고, 운영 체제를 설치한 다음, 인증서를 복원 하거나 reenroll.
    
    <div>
    

    > [!NOTE]  
    > 조직의 서버 배포 절차에 따라이 단계를 수행 합니다.

    
    </div>

2.  RTCUniversalServerAdmins 그룹의 구성원 인 사용자 계정에서 복원 하려는 서버에 로그온 합니다.

3.  Lync Server 설치 폴더 또는 미디어를 찾아 설치 \\\\Amd64\\Setup.exe에 있는 lync server 배포 마법사를 시작 합니다.

4.  배포 마법사의 지시에 따라 다음을 수행 합니다.
    
    1.  **1 단계: 로컬 구성 저장소 설치** 를 실행 하 여 로컬 구성 파일을 설치 합니다.
    
    2.  **2 단계: lync Server 구성 요소 설치 또는 제거** 를 실행 하 여 lync server 서버 역할을 설치 합니다.
    
    3.  **3 단계: 인증서 요청, 설치 또는 할당** 을 실행 하 여 인증서를 할당 합니다.
    
    4.  서버에서 서비스를 시작 하려면 **4 단계: 서비스 시작** 을 실행 합니다.
    
    배포 마법사를 실행 하는 방법에 대 한 자세한 내용은 복원할 서버 역할에 대 한 배포 설명서를 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

