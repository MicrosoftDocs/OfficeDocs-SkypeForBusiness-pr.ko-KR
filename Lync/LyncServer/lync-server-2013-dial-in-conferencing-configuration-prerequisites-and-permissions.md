---
title: 전화 접속 회의 구성 필수 구성 요소 및 권한
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Dial-in conferencing configuration prerequisites and permissions
ms:assetid: b3b251e5-78ac-44a2-8c36-2a061c9b2314
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412865(v=OCS.15)
ms:contentKeyID: 48185165
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6610272c39583b70c1ab20d8271551796f65372
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762306"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dial-in-conferencing-configuration-prerequisites-and-permissions-in-lync-server-2013"></a>Lync Server 2013의 전화 접속 회의 구성 필수 구성 요소 및 권한

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-06-20_

전화 접속 회의는 Lync Server 2013 회의 작업 부하의 선택적 구성 요소입니다. 토폴로지 작성기를 사용 하 여 토폴로지를 디자인 한 다음 프런트 엔드 풀 또는 Standard Edition 서버를 설정 하는 경우 전화 접속 회의를 구성 하기 전에 설치 해야 하는 구성 요소를 배포할 수 있습니다. 이 항목에서는 전화 접속 회의를 구성 하기 전에 수행 해야 하는 작업에 대해 설명 합니다.

이 섹션에서는 회의 작업 부하 및 전화 접속 회의와 관련 된 계획 섹션을 특별히 읽은 것으로 가정 합니다.

<div>

## <a name="dial-in-conferencing-configuration-prerequisites"></a>전화 접속 회의 구성 필수 조건

전화 접속 회의에는 다음과 같은 Lync Server 2013 구성 요소가 필요 합니다.

  - 통합 커뮤니케이션 응용 프로그램 서비스 (c) ( *응용 프로그램 서비스*라고 함)

  - 회의 수행자 응용 프로그램

  - 회의 알림 신청

  - 전화 접속 회의 설정 웹 페이지

  - 하나 이상의 Lync Server 2013 중재 서버와 하나 이상의 PSTN 게이트웨이

토폴로지 작성기를 사용 하 여 토폴로지를 정의 하 고 게시 한 다음 프런트 엔드 풀 또는 Standard Edition 서버를 배포 하는 경우 이러한 구성 요소를 배포 합니다. 엔터프라이즈 음성을 배포 하는 경우 전화 접속 회의를 구성 하기 전에 배포 해야 합니다. 엔터프라이즈 음성을 배포 하지 않는 경우에는 프런트 엔드 풀 또는 Standard Edition 서버를 배포할 때 중재 서버와 PSTN (공용 전환 통신 네트워크) 게이트웨이를 배포할 수 있습니다.

<div>


> [!NOTE]
> Office Communications Server 2007 R2에서 Lync Server 2013으로 업그레이드 하는 경우 Lync Server 2013 회의를 호스트 하는 데 사용할 모든 풀에 전화 접속 회의를 배포 합니다. 전화 접속 회의를 마이그레이션하는 방법에 대 한 자세한 내용은 <A href="migration-from-office-communications-server-2007-r2-to-lync-server-2013.md">Office Communications Server 2007 R2에서 Lync Server 2013로 마이그레이션을</A>참조 하세요.



</div>

이 섹션에서는 다음을 완료 했다고 가정 합니다.

  - Lync Server 2013로 마이그레이션하는 경우 Office Communications Server 2007 R2 환경에 최신 업데이트를 적용 했습니다.

  - 토폴로지 작성기를 사용 하 여 토폴로지를 디자인 하 고 구성 합니다. 회의 작업을 지정 하는 동안 전화 접속 회의 옵션을 선택 했습니다. 토폴로지를 정의 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 토폴로지 정의 및 구성을](lync-server-2013-defining-and-configuring-the-topology.md) 참조 하세요.

  - 토폴로지를 게시 하 고 프런트 엔드 풀 또는 Standard Edition 서버를 설정 했습니다. 토폴로지 게시 및 Lync Server 2013 설치에 대 한 자세한 내용은 배포 설명서에서 [Lync server 2013 배포](lync-server-2013-deploying-lync-server.md) 를 참조 하세요.
    
    <div>
    

    > [!NOTE]
    > 게시 된 토폴로지를 설치할 때 전화 접속 회의 설정 웹 페이지가 프런트 엔드 서버 또는 Standard Edition 서버에 웹 서비스의 일부로 설치 됩니다.

    
    </div>
    
    <div>
    

    > [!IMPORTANT]
    > Lync Server 2013을 배포한 후 토폴로지 작성기에서 파일 저장소의 경로를 변경 하는 경우에는 새 경로를 사용 하기 위해 회의 수행자와 회의 알림 응용 프로그램을 다시 시작 해야 합니다.

    
    </div>

  - 엔터프라이즈 보이스을 배포 했습니다. 엔터프라이즈 음성을 배포 하지 않는 경우 Enterprise Edition 프런트 엔드 서버 또는 스탠더드 버전 서버에서 중재 서버를 collocated, 독립 실행형 중재 서버를 배포 했으며 PSTN 게이트웨이를 배포 했습니다. 엔터프라이즈 음성을 배포 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 Enterprise Voice 배포](lync-server-2013-deploying-enterprise-voice.md) 를 참조 하세요. 독립 실행형 중재 서버 및 PSTN 게이트웨이를 설치 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 중재 서버 배포 및 피어 정의](lync-server-2013-deploying-mediation-servers-and-defining-peers.md) 를 참조 하세요.

다음 순서도는 전화 접속 회의를 구성 하기 전에 수행 해야 하는 단계와 전화 접속 회의를 구성 하기 위해 수행 하는 단계를 보여 줍니다.

**전화 접속 회의 배포**

![전화 접속 회의 배포 순서도](images/Gg412865.fde8c246-b5ed-4323-a6e7-af1983a5ec86(OCS.15).jpg "전화 접속 회의 배포 순서도")

</div>

<div>

## <a name="dial-in-conferencing-permissions"></a>전화 접속 회의 권한

전화 접속 회의를 구성 하려면 다음 관리 도구를 사용 해야 합니다.

  - Lync Server 2013 제어판

  - Lync Server Management Shell

이러한 관리 도구를 사용 하 여 전화 접속 회의 설정을 구성 하 고 전화 접속 회의에 필요한 다이얼 플랜, 정책 및 기타 설정을 구성할 수 있습니다.

전화 접속 회의를 구성 하려면 작업에 따라 다음 관리 역할이 필요 합니다.

  - ****   이 관리자 역할이 음성 관련 설정 및 정책을 만들고, 구성 하 고, 관리할 수 CsVoiceAdministrator.

  - **Csuseradministrator**   이 관리자 역할은 Lync Server의 사용자를 사용 하거나 사용 하지 않도록 설정 하 고, 사용자에 게 회의 정책 및 PIN 정책 등의 기존 정책을 할당할 수 있습니다.

  - **Csadministrator**   이 관리자 역할은 CsVoiceAdministrator 및 csuseruseradministrator의 모든 작업을 수행할 수 있습니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 엔터프라이즈 음성 배포](lync-server-2013-deploying-enterprise-voice.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

