---
title: Enterprise Voice에 대 한 보안 및 구성 선행 조건
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
ms.openlocfilehash: d8aec487e2ef5c6f5a756305a6e44df0c31cbec0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="security-and-configuration-prerequisites-for-enterprise-voice-in-lync-server-2013"></a>Lync Server 2013의 Enterprise Voice에 대 한 보안 및 구성 필수 구성 요소

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-18_

인프라가 다음과 같은 보안, 사용자 구성 및 시나리오별 하드웨어 필수 구성 요소를 충족하는지 확인합니다.

<div>

## <a name="administrative-rights-and-certificate-infrastructure"></a>관리 권한 및 인증서 인프라

환경이 Enterprise Voice 배포 프로세스 중에 사용할 다음과 같은 관리 사용자 그룹 및 인증서 인프라로 구성되어 있는지 확인합니다.

  - Enterprise Voice를 배포하는 관리자는 RTCUniversalServerAdmins 그룹의 구성원이어야 합니다.

  - 구성 작업을 수행하는 관리자에게는 적절한 권한이 있어야 합니다.
    
      - **CsVoiceAdministrator:** 이 관리자 역할은 음성 구성 작업을 수행하고, 음성 응용 프로그램을 관리하고, 최종 사용자에게 음성 정책을 할당할 수 있습니다.
    
      - **CsUserAdministrator:** 이 관리자 역할은 사용자에 대해 Enterprise Voice를 사용하도록 설정하는 것과 같이 사용자 속성을 관리할 수 있습니다. 또한 이 관리자 역할은 사용자별 정책도 할당할 수 있습니다. 단, 보관 정책/사용자 이동/공통 영역 전화 및 아날로그 장치 관리는 예외입니다.
    
      - **CsAdministrator:** 이 관리자 역할은 CsVoiceAdministrator 및 CsUserAdministrator의 모든 작업을 수행할 수 있습니다.
    
    <div>
    

    > [!NOTE]
    > 위임 기능을 사용 하면 리소스에 대 한 불필요 한 액세스를 열지 않고도 더 많은 관리자가 Lync Server 배포에 참가할 수 있습니다.

    
    </div>

  - Microsoft 또는 타사 CA(인증 기관) 인프라를 사용하여 MKI(관리 키 인프라)가 배포 및 구성됩니다.
    
    <div>
    

    > [!NOTE]
    > Lync Server의 인증서 요구 사항에 대 한 자세한 내용은 계획 설명서에서 <A href="lync-server-2013-certificate-infrastructure-requirements.md">Lync server 2013의 인증서 인프라 요구 사항</A> 를 참조 하십시오.

    
    </div>

</div>

<div>

## <a name="user-configuration"></a>사용자 구성

프런트 엔드 배포 중에 중재 서버를 각 프런트 엔드 풀 또는 Standard Edition 서버에 배치 된 하는 경우 Enterprise Voice에 필요한 사용자 설정이 해당 서버 역할에 대 한 파일을 설치 하는 동안 자동으로 구성 됩니다.

Enterprise Voice 작업을 새로 배포하는 경우에는 배포 프로세스를 시작하기 전에 Enterprise Voice를 사용하도록 설정할 각 사용자에 대해 기본 전화 번호를 지정합니다. 관리자는 이 번호가 고유한지 확인해야 합니다. 구현 하기 전에 모든 기본 전화 번호의 형식을 올바르게 지정 하 고 Lync Server 제어판을 사용 하 여 각 사용자의 **줄 URI** 속성에 복사 해야 합니다.

<div>


> [!NOTE]
> Enterprise Voice 배포에 필요한 기본 전화 번호의 예는 계획 설명서의 <A href="lync-server-2013-dial-plans-and-normalization-rules.md">Lync server 2013에서 다이얼 플랜 및 정규화 규칙</A> 의 <A href="lync-server-2013-dial-plans-and-normalization-rules.md">lync server 2013 섹션에 있는 다이얼 플랜 및 정규화 규칙</A> 을 참조 하십시오.



</div>

</div>

<div>

## <a name="next-steps-install-files-or-configure-pstn-connectivity"></a>다음 단계: 파일 설치 또는 PSTN 연결 구성

Enterprise Voice에 대한 소프트웨어 및 환경 필수 구성 요소를 확인한 후에는 다음 콘텐츠를 참조하여 아래와 같은 작업을 수행할 수 있습니다.

  - 배치 된 때 중재 서버가 프런트 엔드 풀 또는 Standard Edition Server 배포 프로세스의 일부로 설치 된 경우에만, 독립 실행형 중재 서버 또는 풀을 배포 하려는 경우에만 [2013](lync-server-2013-install-the-files-for-mediation-server.md)에 설명 된 대로 중재 서버를 설치 합니다.

  - 또는 [Lync Server 2013에서 트렁크을 구성](lync-server-2013-configuring-trunks.md)하는 방법에 설명 된 대로 Enterprise Voice 사용자에 대 한 통화를 라우팅하도록 설정 구성을 시작 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

