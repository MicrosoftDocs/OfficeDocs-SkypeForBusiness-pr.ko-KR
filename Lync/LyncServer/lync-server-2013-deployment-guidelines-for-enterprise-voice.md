---
title: 'Lync Server 2013: Enterprise Voice 배포 지침'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 05cde2a845dd6314d8822e6b58445eed5c6a1d19
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531075"
---
# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013의 Enterprise Voice에 대 한 배포 지침

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-21_

이 항목에서는 Lync Server 2013 및 Enterprise Voice 워크 로드를 배포할 때 고려해 야 할 필수 구성 요소 및 기타 지침에 대해 설명 합니다.

<div>

## <a name="deployment-prerequisites"></a>배포 필수 구성 요소

Enterprise Voice를 배포할 때 최적의 환경을 유지 하려면 IT 인프라, 네트워크 및 시스템이 다음 필수 구성 요소를 충족 하는지 확인 합니다.

  - Lync Server 2013 Standard Edition 또는 Enterprise Edition이 설치 되어 있고 네트워크에 작동 합니다.

  - 모든에 지 서버는 액세스에 지 서비스, A/V에 지 서비스, 웹 회의에 지 서비스 및 역방향 프록시를 포함 하는 경계 네트워크에 배포 되 고 작동 합니다.

  - Lync Server에 대해 하나 이상의 사용자를 만들고 사용할 수 있습니다.

  - Microsoft Exchange Server 2007 SP1 (서비스 팩 1) 또는 최신 서비스 팩 또는 Microsoft Exchange Server 2010가 설치 되어 있어야 합니다. Exchange UM (통합 메시징)과 Lync Server를 통합 하 고 다양 한 알림을 제공 하 고 클라이언트 끝점에 대 한 로그 정보를 호출 하려면 이러한 방법 중 하나를 사용 해야 합니다.

  - Enterprise Voice를 사용 하도록 설정 하려는 각 사용자에 대해 고유한 기본 전화 번호가 지정 되 고 정규화 되며 **msrtcsip-gateways** 특성에 복사 됩니다.
    
    <div>
    

    > [!NOTE]  
    > Lync Server에서는 E. 164 개의 번호와 직접 연결 되지 않은 (연결 되지 않은) 번호를 지원 합니다. 비가상 번호는 <STRONG> &lt; E. 164 &gt; ; ext = &lt; extension &gt; </STRONG> 형식으로 표현 될 수도 있고, 개인 내선 번호가 엔터프라이즈 전체에서 고유 해야 한다는 요구 사항을 충족 하는 숫자의 문자열입니다. 예를 들어 전용 번호 1001는 <STRONG>+ 1425550100, ext = 1001</STRONG>또는 <STRONG>1001</STRONG>로 나타낼 수 있습니다. <STRONG>1001</STRONG>로 표시 된 경우이 전용 번호는 기업 전체에서 고유 합니다.

    
    </div>

  - Enterprise Voice를 배포 하는 관리자는 RTCUniversalServerAdmins 그룹의 구성원 이어야 합니다.

  - 최소한 Office Communicator 2007이 배포 되었습니다. 이 릴리스에 새로 제공 되는 기능을 사용 하려면 Lync 2013이 배포 됩니다.

  - Microsoft 또는 타사 CA(인증 기관) 인프라를 사용하여 MKI(관리 키 인프라)가 배포 및 구성되었습니다.

  - 중재 서버를 설치하는 각 컴퓨터는 다음 요구 사항을 충족해야 합니다.
    
      - 도메인의 구성원 서버 및 Active Directory 도메인 서비스 준비 Active Directory 도메인 서비스 준비 절차에 대 한 자세한 내용은 배포 설명서에서 [Active Directory 도메인 서비스에 대 한 Lync Server 2013 준비](lync-server-2013-preparing-active-directory-domain-services.md) 를 참조 하십시오.
    
      - 다음 운영 체제 중 하나를 실행합니다.
        
          - <span></span>  
            Windows Server 2008 Standard 운영 체제 64비트 버전
        
          - <span></span>  
            Windows Server 2008 Enterprise 운영 체제 64비트 버전

  - TDM(Time Division Multiplexing) 연결을 통해 PSTN(공중 전화망) 또는 PBX(Private Branch Exchange)에 연결된 경우에는 하나 이상의 PSTN 게이트웨이를 배포에 사용할 수 있습니다. SIP 트렁크를 통해 연결된 경우에는 PSTN 게이트웨이가 필요하지 않습니다.

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a>전원, 네트워크 또는 전화 서비스 중단

해당 위치에서 전원, 네트워크 또는 전화 서비스가 중단, 중단 또는 기타 성능 저하 인 경우 Lync Server의 음성, 인스턴트 메시징, 현재 상태 및 기타 기능과 lync server에 연결 된 모든 장치가 제대로 작동 하지 않을 수 있습니다.

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a>Enterprise Voice는 서버 가용성과 음성 클라이언트 및 하드웨어 운용성에 의존함

Lync Server를 사용한 음성 통신은 서버 소프트웨어의 가용성, 서버 소프트웨어에 연결 된 하드웨어 전화 장치 또는 음성 클라이언트의 적절 한 작동에 따라 달라 집니다.

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a>긴급 서비스에 액세스하기 위한 대체 수단

음성 클라이언트 (예: Lync 클라이언트나 Lync Phone Edition 장치를 실행 하는 PC)를 설치 하는 경우에는 사용자가 전원 오류, 네트워크 연결 저하, 전화 서비스 중단 또는 Lync Server의 작동을 방해할 수 있는 기타 문제가 발생 하는 경우 응급 서비스를 호출 하는 백업 옵션 (예: 911 또는 999)을 유지 하는 것이 좋습니다. , Lync 또는 Lync Phone Edition 장치 이러한 대체 옵션은 표준 PSTN(공중 전화망) 회선이나 휴대폰에 연결된 전화기를 포함할 수 있습니다.

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a>긴급 통화 및 다중 회선 전화 시스템

MLTS (다중 지역 전화 시스템) 사용에는 U가 적용 될 수 있습니다. 온라인 발신자가 비상 서비스 (예: 911 또는 999와 같은 비상 액세스 번호에 전화를 거는 경우)에 게 해당 응급 서비스에 대 한 발신자의 전화 번호, 확장 및/또는 실제 위치를 제공 하기 위해 MLTS가 필요로 하는 S 또는 연방 법률 또는 기타 국가/지역의 법 이 릴리스에서는 [lync server 2013의 응급 서비스 계획 (E9-1-1)](lync-server-2013-planning-for-emergency-services-e9-1-1.md)에 설명 된 대로 전화 건 사람의 실제 위치를 긴급 서비스 공급자에 게 제공 하도록 lync server를 구성할 수 있습니다. MLTS 법을 준수 하는 것은 Lync Server, Lync 클라이언트 및 Lync Phone Edition 장치의 구매자에 게 유일한 책임입니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

