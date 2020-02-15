---
title: 'Lync Server 2013: Enterprise Voice 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Enterprise Voice
ms:assetid: b5b593a6-ac30-461c-8c8c-0041e2c9ab04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412876(v=OCS.15)
ms:contentKeyID: 48185207
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c49eeb26e17b337dae3f8b6944f25f2d41906f3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013에서 Enterprise Voice 배포

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-03_

Lync Server 2013, Enterprise Voice는 Lync Server 2013 인프라의 일부입니다.

Enterprise Voice를 배포 하려면 다음을 수행 해야 합니다.

<div id="sectionSection0" class="section">

1.  계획 설명서의 [Lync Server 2013에서 Enterprise Voice 계획](lync-server-2013-planning-for-enterprise-voice.md) 을 검토 합니다.

2.  이 작업을 통해 배포할 기능 및 구성 요소에 대 한 계획을 완성 합니다.

3.  계획 도구를 실행 하 여 배포 결정 사항을 반영 하는 토폴로지를 디자인 합니다.

4.  배포 설명서의 [Lync Server 2013에서 토폴로지 정의 및 구성](lync-server-2013-defining-and-configuring-the-topology.md) 에 설명 된 대로 토폴로지 작성기에서 토폴로지 디자인을 엽니다.
    
    <div>
    

    > [!NOTE]  
    > 토폴로지 작성기 설치는 내부 풀에 대 한 배포 프로세스의 일부입니다. 자세한 내용은 배포 설명서의 <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 관리 도구</A> 를 참조 하십시오.

    
    </div>

또한 배포 하도록 선택한 참조 토폴로지에 해당 하는 중앙 사이트 및 분기 사이트에 Lync Server, Enterprise Edition이 이미 배포 되어 있어야 합니다. 하나 이상의 내부 풀에 대해 파일을 정의, 게시 및 설치한 후에 Enterprise Voice 구성 요소를 배포할 수 있으며, 토폴로지 작성기를 사용 하 여 내부 풀을 정의 하 고 게시 해야 합니다.

</div>

<div id="sectionSection1" class="section">

<div class="subSection">

Enterprise Voice 서버 역할을 배포할 수 있는 위치 (및 서로 다른 Lync Server 2013 서버 역할에 대 한 해당 관계)의 예를 포함 하는 참조 토폴로지를 보려면 계획 설명서에서 [Lync server 2013의 참조 토폴로지](lync-server-2013-reference-topologies.md) 를 참조 하십시오.

네트워크 지역, 네트워크 사이트 및 서브넷을 비롯 한 샘플 통화 허용 제어 배포를 보여 주고 설명 하는 참조 토폴로지를 보려면 계획 설명서에서 [예제: Lync Server 2013의 통화 허용 제어에 대 한 요구 사항 수집](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) 을 참조 하십시오.

</div>

</div>

<div id="sectionSection2" class="section">

<div>


> [!IMPORTANT]  
> 중앙 사이트에서 Enterprise Voice를 배포 하려면이 섹션의 항목을 계속 읽어 보십시오. 분기 사이트에서 Enterprise Voice를 배포 하려면 배포 설명서에서 <A href="lync-server-2013-deploying-branch-sites.md">Lync Server 2013에서 분기 사이트를 배포</A> 하는 방법을 건너뛰십시오.



</div>

이 섹션에는 각 프런트 엔드 서버 또는 Standard Edition Server에서 권장 되는 중재 서버를 배치 된 하는 배포 및 독립 실행형 중재 서버 풀을 사용 하는 배포에 대 한 절차가 포함 되어 있습니다.

배포 마법사에서 각 프런트 엔드 서버 또는 Standard Edition Server에서 중재 서버를 찾은 토폴로지를 정의한 후 게시 하는 경우 다음 콘텐츠를 건너뛸 수 있습니다. 중재 서버: 프런트 엔드 서버 풀 또는 Standard Edition Server에 대 한 파일을 설치할 때 다음을 수행 합니다.

  - [Lync Server 2013에서 트렁크 구성](lync-server-2013-configuring-trunks.md)

토폴로지 작성기를 사용 하 여 독립 실행형 풀에 중재 서버를 정의 하 고 게시 한 경우 다음 콘텐츠를 사용할 수 있습니다.

  - [Lync Server 2013에 대 한 Enterprise Voice 필수 구성 요소](lync-server-2013-enterprise-voice-prerequisites.md)에 설명 된 대로 토폴로지가 소프트웨어 및 환경 필수 구성 요소를 충족 하는지 확인 합니다.

</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - <span></span>  
    [Lync Server 2013에 대 한 Enterprise Voice 필수 구성 요소](lync-server-2013-enterprise-voice-prerequisites.md)

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
    [Lync Server 2013의 음성 라우팅 구성에 보류 중인 변경 내용 게시](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)

  - <span></span>  
    [Lync Server 2013 음성 메일을 제공 하도록 온-프레미스 Exchange UM 배포](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)

  - <span></span>  
    [Lync Server 2013 users 사용자에 게 호스팅된 Exchange UM에 대 한 음성 메일 제공](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)

  - <span></span>  
    [Exchange Online과 온-프레미스 Lync Server 2013의 통합 구성](lync-server-2013-configuring-on-premises-lync-server-integration-with-exchange-online.md)

  - <span></span>  
    [Lync Server 2013에서 고급 Enterprise Voice 기능 배포](lync-server-2013-deploying-advanced-enterprise-voice-features.md)
    
      - [Lync Server 2013의 네트워크 지역, 사이트 및 서브넷 정보](lync-server-2013-about-network-regions-sites-and-subnets.md)
    
      - [Lync Server 2013에서 네트워크 지역 만들기 또는 수정](lync-server-2013-create-or-modify-a-network-region.md)
    
      - [Lync Server 2013에서 네트워크 사이트 만들기 또는 수정](lync-server-2013-create-or-modify-a-network-site.md)
    
      - [Lync Server 2013에서 서브넷을 네트워크 사이트에 연결](lync-server-2013-associate-a-subnet-with-a-network-site.md)
    
      - [Lync Server 2013에서 통화 허용 제어 구성](lync-server-2013-configure-call-admission-control.md)
    
      - [Lync Server 2013에서 향상 된 9-1-1 구성](lync-server-2013-configure-enhanced-9-1-1.md)
    
      - [Lync Server 2013에서 미디어 바이패스 구성](lync-server-2013-configure-media-bypass.md)

  - <span></span>  
    [Lync Server 2013에서 Enterprise Voice를 사용할 수 있도록 사용자 설정](lync-server-2013-enable-users-for-enterprise-voice.md)

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 분기 사이트 배포](lync-server-2013-deploying-branch-sites.md)  
[Lync Server 2013에서 전화 접속 회의 구성](lync-server-2013-configuring-dial-in-conferencing.md)  
[Lync Server 2013에서 통화 대기 구성](lync-server-2013-configuring-call-park.md)  
[Lync Server 2013에서 할당 되지 않은 번호에 대 한 알림 구성](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)  
[Lync Server 2013에서 모니터링 배포](lync-server-2013-deploying-monitoring.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

