---
title: 'Lync Server 2013: Enterprise Voice 배포 지침'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0f4f6198f8fb82720834d112bcf363554aaf84d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013의 Enterprise Voice 배포 지침

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-09-21_

이 항목에서는 Lync Server 2013 및 Enterprise Voice 작업 부하를 배포 하려고 할 때 고려해 야 할 선행 조건과 기타 지침에 대해 설명 합니다.

<div>

## <a name="deployment-prerequisites"></a>배포 필수 구성 요소

엔터프라이즈 음성을 구축할 때 최적의 환경을 위해 IT 인프라, 네트워크 및 시스템이 다음 필수 조건을 충족 하는지 확인 합니다.

  - Lync Server 2013 Standard Edition 또는 Enterprise Edition이 설치 되어 있고 네트워크에 작동 하 고 있습니다.

  - 모든 Edge 서버는 액세스에 지 서비스, A/V Edge 서비스, 웹 회의 Edge 서비스, 역방향 프록시가 있는 Edge 서버를 포함 하 여 주변 네트워크에 배포 및 작동 합니다.

  - 하나 이상의 사용자를 만들고 Lync Server에 대해 사용 하도록 설정 했습니다.

  - Microsoft Exchange Server 2007 SP1(서비스 팩 1) 또는 최신 서비스 팩 또는 Microsoft Exchange Server 2010이 설치 되어 있습니다. 이 중 하나는 Exchange UM (통합 메시징)을 Lync Server와 통합 하 고 풍부한 알림을 제공 하 고 클라이언트 끝점에 로그 정보를 호출 하는 데 필요 합니다.

  - 고유한 기본 전화 번호를 지정 하 고 표준화 한 다음 Enterprise Voice에 사용할 각 사용자의 **msRTCSIP** 특성에 복사 합니다.
    
    <div>
    

    > [!NOTE]  
    > Lync Server는 전자 164 개의 번호 및 직접 수행 되지 않은 내부 전화 걸기 (a) 번호를 지원 합니다. 비 번호는 개인 확장이 엔터프라이즈에서 고유한 요구 사항이 적용 된 <STRONG> &lt;E&gt;: 164,&lt;ext&gt; = extension</STRONG> 또는 string 형식의 숫자로 표현할 수 있습니다. 예를 들어 전용 번호 1001는 <STRONG>+ 1425550100, ext = 1001</STRONG>또는 <STRONG>1001</STRONG>로 표현할 수 있습니다. <STRONG>1001</STRONG>로 표시 되는 경우에는이 개인 번호가 엔터프라이즈에서 고유 하다는 것을 기대 합니다.

    
    </div>

  - 엔터프라이즈 음성을 배포 하는 관리자는 RTCUniversalServerAdmins 그룹의 구성원 이어야 합니다.

  - 최소한 Office Communicator 2007를 배포 했습니다. 이 릴리스에 새로 제공 되는 기능을 사용 하려면 Lync 2013이 배포 됩니다.

  - Microsoft 또는 타사 CA (인증 기관) 인프라를 사용 하 여 MKI (관리 키 인프라)를 배포 하 고 구성 합니다.

  - 중재 서버를 설치 하는 각 컴퓨터에는 다음이 필요 합니다.
    
      - Active Directory 도메인 서비스에 대 한 도메인의 구성원 서버 및 준비. Active Directory 도메인 서비스 준비 절차는 배포 설명서에서 [Lync Server 2013에 대 한 Active Directory 도메인 서비스 준비](lync-server-2013-preparing-active-directory-domain-services.md) 를 참조 하세요.
    
      - 다음 운영 체제 중 하나를 실행 합니다.
        
          - <span></span>  
            64 비트 버전의 Windows Server 2008 표준 운영 체제
        
          - <span></span>  
            64 비트 버전의 Windows Server 2008 엔터프라이즈 운영 체제

  - PSTN (공개 교환 통신망) 또는 PBX (개인 브랜치 교환) 연결을 사용 하는 경우 TDM (시간 분할) 연결이 있으면 하나 이상의 PSTN 게이트웨이를 배포에 사용할 수 있습니다. (연결이 SIP 트렁크를 사용 하는 경우에는 PSTN 게이트웨이가 필요 하지 않습니다.)

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a>전원, 네트워크 또는 전화 서비스 중단

현재 위치에서 전원, 네트워크 또는 전화 서비스에 대 한 작동 중지, 중단 또는 기타 성능이 저하 되는 경우 Lync Server의 음성, 인스턴트 메시지, 현재 상태, 기타 기능 및 lync Server에 연결 된 모든 장치가 제대로 작동 하지 않을 수 있습니다.

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a>엔터프라이즈 음성은 서버 가용성, 음성 클라이언트 및 하드웨어 운용성에 따라 다릅니다.

Lync Server와의 음성 통신은 서버 소프트웨어의 사용 가능성 및 서버 소프트웨어에 연결 하는 하드웨어 전화 장치 또는 음성 클라이언트의 적절 한 작동에 따라 달라 집니다.

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a>응급 서비스에 액세스 하는 다른 방법

음성 클라이언트를 설치 하는 위치 (예: Lync 클라이언트 또는 Lync Phone Edition 장치를 실행 하는 PC)의 경우 정전 서비스를 위해 사용자가 비상 서비스 (예: 911 또는 999)를 호출 하는 백업 옵션을 유지 관리 하는 것이 좋습니다. , 네트워크 연결 저하, 전화 서비스 중단 또는 Lync Server, Lync 또는 Lync Phone Edition 장치의 작동을 방해할 수 있는 기타 문제 이러한 대체 옵션에는 표준 공공 교환 전화 네트워크 회선 또는 휴대 전화에 연결 된 전화기가 포함 될 수 있습니다.

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a>비상 전화 및 여러 회선 전화 시스템

MLTS (다중 회선 전화 시스템) 사용에는 미국에 적용 될 수 있습니다. 온라인에서 비상 서비스 (예: 911 또는 999와 같은 긴급 액세스 번호를 사용 하는 경우)에 호출자의 전화 번호, 확장 및/또는 실제 위치를 해당 응급 서비스에 제공 해야 하는 다른 국가/지역의 법률 또는 미국 연방 법률 이 릴리스에서 lync Server는 [Lync server 2013의 응급 서비스 계획 (E9-1-1)](lync-server-2013-planning-for-emergency-services-e9-1-1.md)에 설명 된 대로, 긴급 서비스 공급자에 게 발신자의 실제 위치를 제공 하도록 구성할 수 있습니다. MLTS 법을 준수 하는 것은 Lync Server, Lync 클라이언트, Lync Phone Edition 디바이스의 구매자의 유일한 책임입니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

