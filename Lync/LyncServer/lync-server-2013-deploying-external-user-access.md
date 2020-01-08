---
title: 'Lync Server 2013: 외부 사용자 액세스 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying external user access
ms:assetid: d40c9574-c16b-4fe6-b848-21ae0b7e4f0e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398918(v=OCS.15)
ms:contentKeyID: 48185495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e8522eac5ace72f615cc3cb7b9271981d1b84c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983496"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-external-user-access-in-lync-server-2013"></a>Lync Server 2013에서 외부 사용자 액세스 배포

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-09-23_

Microsoft Lync Server 2013에 대 한 edge 구성 요소를 배포 하면 인증 및 익명 원격 사용자, 페더레이션 파트너 (XMPP 파트너 포함)를 포함 하 여 조직의 내부 네트워크에 로그인 하지 않은 외부 사용자가 가능 합니다. Lync Server를 사용 하 여 조직의 다른 사용자와 통신 하는 모바일 클라이언트 및 IM (공개 메신저) 서비스 사용자 Lync Server 2013의 배포 및 구성 프로세스는 Lync Server 2010와 크게 다릅니다. 설치 및 관리 도구는 Lync Server 2010와 거의 동일 합니다.

<div>


> [!IMPORTANT]  
> Microsoft Lync Server 2013&nbsp;Edge 서버 설치 및 구성은 내부 팀과의 상당한 양의 계획과 조정이 필요한 복잡 한 프로세스 (예를 들어, – 보안, 네트워킹, 방화벽, DNS (domain name system), 부하 분산 장치 및 PKI (공개 키 인프라) 고려 사항) 일 수 있습니다. 외부 액세스 구성 요소를 배포 하기 전에 제공 되는 계획 프로세스와 설명서를 검토 하 고 사용 하는 것이 좋습니다. 이렇게 하면 배포 프로세스를 진행할 때 원치 않는 변경 및 문제의 횟수와 빈도를 제한 하는 데 도움이 됩니다. 외부 사용자 액세스 계획에 대 한 자세한 내용은 <A href="lync-server-2013-planning-for-external-user-access.md">Lync Server 2013에서 외부 사용자 액세스 계획 수립</A>을 참조 하세요.



</div>

<div>

## <a name="in-this-section"></a>이 섹션의 내용

  - [Lync Server 2013의 외부 사용자 액세스를 위한 배포 검사 목록](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [Lync Server 2013의 외부 사용자 액세스 구성 요소에 대한 시스템 요구 사항](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Lync Server 2013의 경계 네트워크에 서버 설치 준비](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [Lync Server 2013에서 에지 및 디렉터 토폴로지 구성](lync-server-2013-building-an-edge-and-director-topology.md)

  - [Lync Server 2013에서 디렉터 설정](lync-server-2013-setting-up-the-director.md) (선택 사항)

  - [Lync Server 2013에서 에지 서버 설정](lync-server-2013-setting-up-edge-servers.md)

  - [Lync Server 2013에 대한 역방향 프록시 서버 설치](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [Lync Server 2013에서 외부 사용자 액세스에 대한 지원 구성](lync-server-2013-configuring-support-for-external-user-access.md)

  - [Lync Server 2013의 Lync-Skype 연결에 대한 프로비전 가이드](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [Lync Server 2013에서 SIP 페더레이션, XMPP 페더레이션 및 공용 메신저 구성](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [Lync Server 2013에서 모바일 기능 배포](lync-server-2013-deploying-mobility.md)

  - [Lync Server 2013에서 에지 배포 확인](lync-server-2013-verifying-your-edge-deployment.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

