---
title: Lync Server 2013 파일럿 풀 배포
description: Lync Server 2013 파일럿 풀을 배포 합니다.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: a81aba1e-e636-434b-8c56-4150435bb55d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205144(v=OCS.15)
ms:contentKeyID: 48185028
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a599cee1719f773ebbf3cf5a71405aa9b7259261
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550794"
---
# <a name="deploy-lync-server-2013-pilot-pool"></a>Lync Server 2013 파일럿 풀 배포

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-11-22_

Lync Server 2013로 마이그레이션하는 데 필요한 첫 단계 중 하나는 파일럿 풀을 배포 하는 것입니다. 파일럿 풀은 lync Server 2010 배포와 함께 Lync Server 2013의 공존 성을 테스트 합니다. 동시 사용은 모든 사용자와 풀을 Lync Server 2013로 이동할 때까지 지속 되는 임시 상태입니다.

파일럿 풀을 배포할 때는 새 프런트 엔드 풀 정의 마법사를 사용합니다. Lync Server 2010 풀에 있는 것과 동일한 기능 및 작업을 Lync Server 2013 파일럿 풀에 배포 해야 합니다. Lync Server 2010 환경을 보관 또는 모니터링 하기 위해 보관 서버, 모니터링 서버 또는 System Center Operations Manager를 배포한 경우 마이그레이션 전체에서 보관 또는 모니터링을 계속 하려면 파일럿 환경에 이러한 기능을 배포 해야 합니다. Lync Server 2010 환경을 배포 하거나 모니터링 하기 위해 배포한 버전은 Lync Server 2013 환경에서 데이터를 캡처하지 않습니다.

<div>


> [!NOTE]  
> 다음 절차에서는 전체 파일럿 풀 배포 프로세스에서 고려해야 하는 기능 및 설정에 대해 설명합니다. 이 섹션에서는 파일럿 풀 배포 중에 고려해야 하는 핵심 사항들에 대해서만 설명합니다. 자세한 단계는 <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> 배포 가이드 배포를 참조 하십시오.



</div>

**Lync Server 2013 파일럿 풀을 배포 하려면**

1.  토폴로지 작성기가 Domain Admins 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 설치되어 있는 컴퓨터에 로그온합니다.

2.  **Lync Server 2013** **Enterprise Edition 프런트 엔드 풀**에 도달할 때까지 트리를 확장 합니다.

3.  **Enterprise Edition 프런트 엔드 풀**을 마우스 오른쪽 단추로 클릭하고 **새 프런트 엔드 풀**을 선택합니다.
    
    ![토폴로지 작성기 서버 풀 선택 하위 메뉴](images/JJ205144.c2feed27-3418-42a6-a254-76e83607db9c(OCS.15).jpg "토폴로지 작성기 서버 풀 선택 하위 메뉴")

4.  풀의 FQDN을 입력합니다. 파일럿 풀을 정의할 때는 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 서버를 배포 하도록 선택할 수 있습니다. Lync Server 2013에서는 파일럿 풀 기능이 레거시 풀에 배포 된 것과 일치 하지 않아도 됩니다.
    
    <div>
    

    > [!WARNING]  
    > 파일럿 풀에 대해 정의하는 풀 또는 서버의 FQDN(정규화된 도메인 이름)은 고유해야 합니다. 현재 배포 된 Lync Server 2010 풀 또는 현재 배포 되어 있는 다른 서버 이름과 일치 시킬 수 없습니다.

    
    </div>
    
    ![새 프런트 엔드 풀 마법사 FQDN 정의 페이지](images/JJ205144.c5fd138c-e75a-413a-827f-b1461c996d40(OCS.15).jpg "새 프런트 엔드 풀 마법사 FQDN 정의 페이지")

5.  **기능 선택** 페이지에서 이 프런트 엔드 풀에 필요한 기능의 확인란을 선택합니다. 예를 들어 IM(인스턴트 메시징) 및 현재 상태 기능만 배포하려면 회의 확인란을 선택하여 단체 IM을 허용하고 음성, 화상 및 공동 작업 회의 기능을 나타내는 전화 접속(PSTN) 회의, Enterprise Voice 또는 통화 허용 제어는 선택하지 않습니다. 기능을 선택 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync server 2013에서 프런트 엔드 풀 또는 Standard Edition 서버 정의 및 구성을](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) 참조 하십시오.
    
    ![프런트 엔드 풀 기능 선택 페이지](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "프런트 엔드 풀 기능 선택 페이지")

6.  **배치 된 서버 역할 선택** 페이지에서 Lync server 2013의 중재 서버를 함께 배치할 것이 좋습니다. Lync Server 2013을 사용 하 여 레거시 토폴로지를 병합 하는 경우 먼저 Lync Server 2010 중재 서버를 함께 배치할 합니다. 토폴로지를 병합 하 고 Lync Server 2013 중재 서버를 구성한 후에는 배포 프로세스에서 나중에 중재 서버 역할을 Lync Server 2013로 이동할 때 배치 된 중재 서버를 유지할지 아니면 독립 실행형 서버로 변경할 것인지 결정할 수 있습니다.
    
    ![프런트 엔드 풀 배치 된 서버 역할 선택 페이지](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "프런트 엔드 풀 배치 된 서버 역할 선택 페이지")

7.  파일럿 풀 배포 중에는 **이 프런트 엔드 풀과 서버 역할 연결**에서 **에지 풀을 이 프런트 엔드 풀의 미디어 구성 요소에서 사용하도록 설정** 옵션을 선택하지 마십시오. 이 기능은 나중에 마이그레이션 중에 사용하고 온라인으로 설정합니다. 현재는 이 설정을 해제한 상태로 둡니다.
    
    ![프런트 엔드 풀과 서버 역할 연결 페이지](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "프런트 엔드 풀과 서버 역할 연결 페이지")

8.  **Office Web Apps 서버 선택** 페이지에서 **새로 만들기**를 클릭한 다음 응용 프로그램 서버의 FQDN을 지정합니다.
    
    ![새 Office Web Apps 서버 FQDN 속성 정의](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "새 Office Web Apps 서버 FQDN 속성 정의")

9.  **보관 Sql server 저장소 정의** 페이지에서 Lync server 보관 및 모니터링에 대 한 sql server 저장소를 정의할 때 lync server 2013에 대해 이전에 만든 sql server 인스턴스를 선택 합니다.
    
    ![보관 SQL Server 저장소 정의 페이지](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "보관 SQL Server 저장소 정의 페이지")

10. 토폴로지를 게시하려면 **Lync Server** 노드를 마우스 오른쪽 단추로 클릭한 후 **토폴로지 게시**를 클릭합니다.
    
    ![구성 된 토폴로지를 표시 하는 토폴로지 작성기](images/JJ205144.c3eafa20-159e-4355-a23d-9f72aeb26037(OCS.15).jpg "구성 된 토폴로지를 표시 하는 토폴로지 작성기")

11. 게시 프로세스를 완료했으면 **마침**을 클릭합니다.

구성 저장소의 로컬 복사본을 설치 하 고 필요한 서비스를 시작 하려면 배포 설명서에서 [Lync Server 2013의 설정 업 프런트 엔드 서버 및 프런트 엔드 풀 설정을](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) 참조 하십시오.


</div>

<span> </span>

</div>

</div>

</div>

