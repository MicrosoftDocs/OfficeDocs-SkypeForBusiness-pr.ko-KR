---
title: Enterprise Voice에 대한 보안 및 구성 필수 구성 요소
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security and configuration prerequisites for Enterprise Voice
ms:assetid: 15354abe-733e-466b-bcd4-a6cfbf58caf8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398221(v=OCS.15)
ms:contentKeyID: 48183495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6530e00a942e2e839eaf4bc2d069212b746e2504
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732578"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013의 엔터프라이즈 음성에 대 한 보안 및 구성 선행 조건

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-18_

인프라가 다음 보안, 사용자 구성 및 시나리오 관련 하드웨어 필수 구성 요소를 충족 하는지 확인 합니다.

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a>관리 권한 및 인증서 인프라

환경이 엔터프라이즈 음성 배포 프로세스 중에 사용할 수 있도록 다음 관리 사용자 그룹 및 인증서 인프라로 구성 되어 있는지 확인 합니다.

  - 엔터프라이즈 음성을 배포 하는 관리자는 RTCUniversalServerAdmins 그룹의 구성원 이어야 합니다.

  - 구성 작업을 수행 하는 관리자에 게 적절 한 권한이 있어야 합니다.
    
      - **CsVoiceAdministrator:** 이 관리자 역할은 음성 구성 작업을 수행 하 고, 음성 응용 프로그램을 관리 하 고, 최종 사용자에 게 음성 정책을 할당할 수 있습니다.
    
      - **Csuseradministrator:** 이 관리자 역할은 사용자의 엔터프라이즈 보이스 사용 등의 사용자 속성을 관리할 수 있습니다. 이 관리자 역할은 또한 보관 정책의 예외를 사용 하 여 사용자별 정책을 할당할 수 있습니다. 사용자 이동 공통 영역 전화 및 아날로그 장치를 관리 합니다.
    
      - **Csadministrator:** 이 관리자 역할은 CsVoiceAdministrator 및 CsUserAdministrator의 모든 작업을 수행할 수 있습니다.
    
    <div>
    

    > [!NOTE]
    > 위임을 사용 하면 더 많은 관리자가 리소스에 대 한 불필요 한 액세스를 열지 않고도 Lync Server 배포에 참가할 수 있습니다.

    
    </div>

  - Microsoft 또는 타사 CA (인증 기관) 인프라를 사용 하 여 MKI (관리 키 인프라)를 배포 하 고 구성 합니다.
    
    <div>
    

    > [!NOTE]
    > Lync Server의 인증서 요구 사항에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-certificate-infrastructure-requirements.md">Lync server 2013에 대 한 인증서 인프라 요구 사항을</A> 참조 하세요.

    
    </div>

</div>

<div>

## <a name="user-configuration"></a>사용자 구성

프런트 엔드 배포 중에 각 프런트 엔드 풀 또는 Standard Edition 서버와 중재 서버를 collocated 경우 Enterprise Voice에 필요한 사용자 설정이 해당 서버 역할에 대 한 파일을 설치 하는 동안 자동으로 구성 됩니다.

지금 엔터프라이즈 음성 작업 부하를 새로 배포 하는 경우 배포 프로세스를 시작 하기 전에 엔터프라이즈 음성을 사용할 수 있도록 계획 하는 각 사용자의 기본 전화 번호를 지정 합니다. 관리자는이 번호가 고유 하다는 것을 책임 집니다. 구현 하기 전에 모든 주 전화 번호의 형식을 올바르게 지정 하 고 Lync Server 제어판을 사용 하 여 각 사용자의 **줄 URI** 속성에 복사 해야 합니다.

<div>


> [!NOTE]
> 엔터프라이즈 음성 배포에 필요한 기본 전화 번호의 예는 계획 설명서의 <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync server 2013에서 다이얼</A> 플랜 및 정규화 규칙의 <A href="lync-server-2013-dial-plans-and-normalization-rules.md">lync server 2013 섹션에 있는 다이얼 플랜 및 정규화</A> 규칙을 참조 하세요.



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>다음 단계: 파일 설치 또는 PSTN 연결 구성

엔터프라이즈 음성에 대 한 소프트웨어 및 환경 선행 조건을 확인 한 후 다음 콘텐츠를 사용 하 여 다음 중 하나를 수행할 수 있습니다.

  - Collocated 때 중재 서버가 프런트 엔드 풀 또는 Standard Edition Server 배포 프로세스의 일부로 설치 되어 있는 경우 [2013](lync-server-2013-install-the-files-for-mediation-server.md)에만 독립 실행형 중재 서버 또는 풀을 배포 하려는 경우에만 조정 서버를 설치 합니다.

  - 또는 [Lync Server 2013에서 trunks를 구성](lync-server-2013-configuring-trunks.md)하는 방법에 설명 된 대로 엔터프라이즈 음성 사용자에 대 한 통화를 라우팅하도록 설정 구성을 시작 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

