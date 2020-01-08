---
title: 그룹 통화 픽업 구성 필수 조건 및 사용자 권한
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Group Call Pickup configuration prerequisites and user rights
ms:assetid: 8757b1d3-751d-49c3-b1b8-b678f663f18e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945641(v=OCS.15)
ms:contentKeyID: 51541495
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2eb0af5b78d5d391ba055e557ad71da79484b5c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="group-call-pickup-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Lync Server 2013의 그룹 통화 픽업 구성 선행 조건 및 사용자 권한

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-01-30_

그룹 통화 픽업 기능은 엔터프라이즈 음성을 구축할 때 기본적으로 설치 되는 통화 관리 기능입니다. 이 항목에서는 그룹 통화 픽업 및 구성 작업을 수행 하는 데 필요한 사용자 권한을 구성할 수 있도록 하기 위해 필요한 사항에 대해 설명 합니다.

이 섹션에서는 그룹 통화 픽업 관련 계획 설명서를 읽은 것으로 가정 합니다 ( [Lync Server 2013의 그룹 통화 픽업 계획](lync-server-2013-planning-for-group-call-pickup.md)참조).

<div>

## <a name="group-call-pickup-configuration-prerequisites"></a>그룹 통화 픽업 구성 필수 조건

그룹 통화 픽업에는 다음 구성 요소가 필요 합니다.

  - 응용 프로그램 서비스

  - 통화 공원 응용 프로그램

이러한 구성 요소는 엔터프라이즈 음성을 배포할 때 자동으로 설치 됩니다.

</div>

<div>

## <a name="group-call-pickup-configuration-user-rights"></a>그룹 통화 픽업 구성 사용자 권한

다음 관리 도구를 사용 하 여 그룹 통화 픽업을 구성 합니다.

  - Lync Server Management Shell

  - SEFAUtil 리소스 키트 도구

Lync Server Management Shell을 사용 하 여 통화 공원 궤도 테이블에서 통화 픽업 그룹을 만들고 관리할 수 있습니다. SEFAUtil 리소스 키트 도구를 사용 하 여 통화 픽업 그룹을 할당 하 고 사용자 용 그룹 통화 픽업 기능을 사용 하도록 설정 하거나 사용자를 위한 그룹 통화 픽업 설정을 사용 하지 않도록 설정 합니다.

그룹 통화 픽업 구성은 작업에 따라 다음 관리 역할이 필요 합니다.

  - **CsVoiceAdministrator:** 이 관리자 역할은 모든 음성 관련 설정 및 정책을 만들고, 구성 하 고, 관리할 수 있습니다.

  - **Csuseradministrator:** 이 관리자 역할은 사용자 용 그룹 통화 픽업 기능을 사용 하도록 설정할 수 있습니다. 또한이 관리자 역할에는 모든 음성 구성에 대 한 읽기 전용 보기 액세스 권한이 있습니다.

  - **Csserveradministrator:** 이 관리자 역할은 서버 및 서비스를 관리 하 고 모니터링 하 고 문제를 해결할 수 있습니다.

  - **Csadministrator:** 이 관리자 역할은 CsVoiceAdministrator, CsServerAdministrator 및 Csserveradministrator의 모든 작업을 수행할 수 있습니다.

<div>


> [!NOTE]
> 관리 권한에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013의 역할 기반 액세스 제어 계획</A> 을 참조 하세요.



</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 엔터프라이즈 음성 배포](lync-server-2013-deploying-enterprise-voice.md)  


[Lync Server 2013의 통화 관리 기능 계획](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

