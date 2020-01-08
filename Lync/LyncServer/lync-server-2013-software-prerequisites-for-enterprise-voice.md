---
title: 'Lync Server 2013: Enterprise Voice에 대한 소프트웨어 필수 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Software prerequisites for Enterprise Voice
ms:assetid: 41172119-9631-46c7-9d9f-386d951c650b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425916(v=OCS.15)
ms:contentKeyID: 48183960
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ac981d7a30a85d25d2dfb376cfa34f812e898bb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983715"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="software-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013의 Enterprise Voice에 대한 소프트웨어 필수 구성 요소

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-03_

엔터프라이즈 음성을 배포 하려는 인프라가 다음 소프트웨어 필수 구성 요소를 충족 하는지 확인 합니다.

  - Lync Server 2013 Standard Edition 또는 Enterprise Edition이 설치 되어 있고 네트워크에 작동 하 고 있습니다.

  - 모든 Edge 서버는 액세스 경계 서비스를 실행 하는 Edge 서버, A/V Edge 서비스, 웹 회의에 지 서비스, 역방향 프록시를 비롯 하 여 주변 네트워크에 배포 및 작동 합니다.

  - Microsoft exchange Server 2007 서비스 팩 3(sp3)에서 microsoft Exchange server 2010 또는 Microsoft Exchange Server 2013을 사용 하 여 Lync Server와 Exchange 통합 메시징을 통합 하 고, 다양 한 알림을 제공 하 고, 로그 정보를 다음에 게 전화 Lync 끝점.

  - 하나 이상의 사용자를 만들고 Lync Server에 대해 사용 하도록 설정 했습니다.

  - Lync 클라이언트 및 장치가 성공적으로 배포 되었습니다.

  - 토폴로지 작성기가 네트워크의 서버에 설치 되어 있습니다.

<div>

## <a name="next-steps-verify-security-and-configuration-prerequisites"></a>다음 단계: 보안 및 구성 선행 조건을 확인 합니다.

엔터프라이즈 음성에 대 한 소프트웨어 필수 구성 요소를 확인 한 후에 설명서를 사용 하 여 엔터프라이즈 음성 배포 준비를 계속할 수 있습니다.

1.  [Lync Server 2013의 엔터프라이즈 음성에 대 한 보안 및 구성 선행 조건](lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md)에서 설명한 대로 보안, 사용자 구성 및 하드웨어 perquisites 확인 합니다.

2.  Collocated 때 중재 서버가 프런트 엔드 풀 또는 Standard Edition Server 배포 프로세스의 일부로 설치 되어 있는 경우 [2013](lync-server-2013-install-the-files-for-mediation-server.md)에만 독립 실행형 중재 서버 또는 풀을 배포 하려는 경우에 *만* 조정 서버를 설치 합니다.

3.  [Lync Server 2013에서 trunks를 구성](lync-server-2013-configuring-trunks.md)하는 방법에 설명 된 대로 사용자에 게 PSTN 연결을 제공 하도록 트렁크 연결을 구성 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

