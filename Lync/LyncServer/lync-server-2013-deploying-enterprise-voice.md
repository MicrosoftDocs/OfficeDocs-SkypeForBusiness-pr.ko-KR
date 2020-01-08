---
title: 'Lync Server 2013: 엔터프라이즈 음성 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae445d954bd1be7c956d76aa48da2ad7854c6a54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985347"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013에서 엔터프라이즈 음성 배포

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-03_

Lync Server 2013, Enterprise Voice는 Lync Server 2013 인프라의 일부입니다.

엔터프라이즈 음성을 배포 하려면 다음이 필요 합니다.

<div id="sectionSection0" class="section">

1.  계획 설명서의 [Lync Server 2013 섹션에서 엔터프라이즈 음성에 대 한 계획](lync-server-2013-planning-for-enterprise-voice.md) 을 검토 합니다.

2.  이 작업 부하와 함께 배포할 기능 및 구성 요소에 대 한 계획을 완성 합니다.

3.  계획 도구를 실행 하 여 배포 결정 사항을 반영 하는 토폴로지를 디자인 합니다.

4.  배포 설명서의 [Lync Server 2013에서 토폴로지를 정의 하 고 구성](lync-server-2013-defining-and-configuring-the-topology.md) 하는 방법에 설명 된 대로 토폴로지 작성기에서 토폴로지 디자인을 엽니다.
    
    <div>
    

    > [!NOTE]  
    > 토폴로지 작성기 설치는 내부 풀에 대 한 배포 프로세스의 일부입니다. 자세한 내용은 배포 설명서에서 <A href="lync-server-2013-install-lync-server-administrative-tools.md">Lync Server 2013 관리 도구 설치</A> 를 참조 하세요.

    
    </div>

또한 중앙 사이트 및 배포 하기로 선택한 참조 토폴로지에 해당 하는 지점 사이트에 Lync Server Enterprise Edition을 이미 배포 해야 합니다. 하나 이상의 내부 풀에 대해 파일을 정의 하 고, 게시 하 고, 설치할 때까지 Enterprise Voice 구성 요소를 배포할 수 없으며, 토폴로지 작성기를 사용 하 여 내부 풀을 정의 하 고 게시 해야 합니다.

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

엔터프라이즈 음성 서버 역할을 배포할 수 있는 사용자 (및 다른 Lync Server 2013 서버 역할에 대 한 관계)의 예를 사용 하 여 참조 토폴로지를 보려면 계획 설명서의 [Lync server 2013에서 참조 토폴로지](lync-server-2013-reference-topologies.md) 를 참조 하세요.

네트워크 지역, 네트워크 사이트 및 서브넷을 포함 하 여 샘플 호출 허용 제어 배포를 설명 하는 참조 토폴로지를 보려면 계획 설명서의 [Lync Server 2013에서 통화 허용 제어에 대 한 요구 사항 수집](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 을 참조 하세요.

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> 중앙 사이트에서 엔터프라이즈 음성을 배포 하려면이 섹션의 항목을 계속 읽습니다. 지점 사이트에서 엔터프라이즈 음성을 배포 하려면 배포 설명서의 <A href="lync-server-2013-deploying-branch-sites.md">Lync Server 2013에서 분기 사이트 배포</A> 를 건너뛰십시오.



</div>

이 섹션에는 각 프런트 엔드 서버 또는 스탠더드 버전 서버에서 중재 서버를 collocated 하는 배포에 대 한 절차와 함께, 독립 실행형 중재 서버 풀을 사용 하 여 배포 하기 위한 절차가 포함 되어 있습니다.

배포 마법사가 각 프런트 엔드 서버 또는 Standard Edition 서버에서 중재 서버를 찾는 토폴로지를 정의 하 고 게시 하는 경우 다음 콘텐츠를 건너뛸 수 있습니다. 프런트 엔드 서버 풀 또는 Standard Edition Server 용 파일을 설치할 때 중재 서버:

  - [Lync Server 2013에서 트렁크 구성](lync-server-2013-configuring-trunks.md)

토폴로지 작성기를 사용 하 여 독립 실행형 풀에 중재 서버를 정의 하 고 게시 한 경우 다음 콘텐츠를 사용할 수 있습니다.

  - 사용자의 토폴로지가 [Lync Server 2013의 Enterprise Voice 전제 조건](lync-server-2013-enterprise-voice-prerequisites.md)에 설명 된 대로 소프트웨어 및 환경 선행 조건을 충족 하는지 확인 합니다.

</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - <span></span>  
    [Lync Server 2013에 대한 Enterprise Voice 필수 구성 요소](lync-server-2013-enterprise-voice-prerequisites.md)

  - <span></span>  
    [Lync Server 2013에서 중재 서버 배포 및 피어 정의](lync-server-2013-deploying-mediation-servers-and-defining-peers.md)

  - <span></span>  
    [Lync Server 2013에서 트렁크 구성](lync-server-2013-configuring-trunks.md)

  - <span></span>  
    [Lync Server 2013에서 다이얼 플랜 구성](lync-server-2013-configuring-dial-plans.md)

  - <span></span>  
    [Lync Server 2013에서 음성 정책, PSTN 사용 레코드 및 음성 경로 구성](lync-server-2013-configuring-voice-policies-pstn-usage-records-and-voice-routes.md)

  - <span></span>  
    [Lync Server 2013에서 음성 라우팅 구성 내보내기 및 가져오기](lync-server-2013-exporting-and-importing-voice-routing-configuration.md)

  - <span></span>  
    [Lync Server 2013에서 음성 라우팅 테스트](lync-server-2013-test-voice-routing.md)

  - <span></span>  
    [Lync Server 2013에서 음성 라우팅 구성에 보류 중인 변경 내용 게시](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [Lync Server 2013 음성 메일을 제공하도록 온-프레미스 Exchange UM 배포](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [호스팅된 Exchange UM에서 Lync Server 2013 사용자 음성 메일 제공](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [Exchange Online과 온-프레미스 Lync Server 2013 통합 구성](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [Lync Server 2013에서 고급 엔터프라이즈 음성 기능 배포](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [Lync Server 2013의 네트워크 지역, 사이트 및 서브넷 정보](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [Lync Server 2013에서 네트워크 영역 만들기 또는 수정](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [Lync Server 2013에서 네트워크 사이트 만들기 또는 수정](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [Lync Server 2013 에서 네트워크 사이트에 서브넷 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [Lync Server 2013에서 통화 허용 제어 구성](lync-server-2013-configure-call-admission-control.md)
    
      - [Lync Server 2013에서 고급 9-1-1 구성](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [Lync Server 2013에서 미디어 바이패스 구성](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [Lync Server 2013에서 엔터프라이즈 음성에 대 한 사용자 활성화](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 분기 사이트 배포](lync-server-2013-deploying-branch-sites.md)  
[Lync Server 2013에서 전화 접속 회의 구성](lync-server-2013-configuring-dial-in-conferencing.md)  
[Lync Server 2013에서 통화 대기 구성](lync-server-2013-configuring-call-park.md)  
[Lync Server 2013에서 지정되지 않은 번호에 대한 알림 구성](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[Lync Server 2013에서 모니터링 배포](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

