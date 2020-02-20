---
title: 'Lync Server 2013: 알림의 구성 필수 구성 요소 및 역할'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Announcement configuration prerequisites and roles
ms:assetid: 82f2dfe9-4c5e-4d65-96a1-96495d506ea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398658(v=OCS.15)
ms:contentKeyID: 48184674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8dde28cac806b517a410f5edfa7ecbcf19176ed4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146901"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="announcement-configuration-prerequisites-and-roles-in-lync-server-2013"></a>Lync Server 2013의 알림 구성 선행 조건 및 역할

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-25_

공지는 Enterprise Voice 통화 관리 기능입니다. 이 항목에서는 알림 및 구성 작업을 수행 하는 데 필요한 역할 할당을 구성 하기 전에 필요한 사항에 대해 설명 합니다.

이 섹션에서는 공지 사항 관련 계획 설명서를 읽어야 하는 것으로 가정 합니다 ( [Lync Server 2013의 통화 관리 기능 계획](lync-server-2013-planning-for-call-management-features.md)참조).

<div>

## <a name="announcement-configuration-prerequisites"></a>알림 구성 필수 구성 요소

알림 응용 프로그램을 사용 하려면 다음 구성 요소가 필요 합니다.

  - 응용 프로그램 서비스

  - 응답 그룹 응용 프로그램

  - 오디오 파일을 보관할 파일 저장소

이러한 구성 요소는 모두 Enterprise Voice를 배포할 때 기본적으로 설치됩니다.

</div>

<div>

## <a name="announcement-configuration-roles"></a>알림 구성 역할

다음 관리 도구를 사용하여 알림을 구성할 수 있습니다.

  - Lync Server 제어판

  - Lync Server 관리 셸

알림 응용 프로그램을 구성 하려면 다음 관리 역할 중 하나가 필요 합니다.

  - **CsVoiceAdministrator**   이 관리자 역할은 알림 설정을 비롯 한 모든 음성 관련 설정 및 정책을 만들고 구성 하 고 관리할 수 있습니다.

  - **Csserveradministrator**   이 관리자 역할은 서버 및 서비스를 관리 및 모니터링 하 고 문제를 해결 하 고 모든 알림 설정을 구성할 수 있습니다.

  - **Csadministrator**   이 관리자 역할은 모든 관리 작업을 수행 하 고 모든 설정을 수정할 수 있습니다.

  - **Csviewonly 관리자**   이 관리자 역할은 배포를 보고 배포 상태를 모니터링할 수 있습니다.

<div>


> [!NOTE]  
> 관리 사용자 권한에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013에서 역할 기반 액세스 제어 계획</A> 을 참조 하십시오.



</div>

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 Enterprise Voice 배포](lync-server-2013-deploying-enterprise-voice.md)  


[Lync Server 2013의 통화 관리 기능 계획](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

