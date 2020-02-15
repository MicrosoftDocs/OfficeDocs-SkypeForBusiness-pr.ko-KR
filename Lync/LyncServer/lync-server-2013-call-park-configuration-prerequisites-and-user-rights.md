---
title: 'Lync Server 2013: 통화 대기 구성 필요 조건 및 사용자 권한'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Call Park configuration prerequisites and user rights
ms:assetid: 25b8cfe0-e4e7-487c-9e78-8c040f629059
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425730(v=OCS.15)
ms:contentKeyID: 48183648
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19a677b7b1a76c0956b5edc663e8932716ce5fb6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-park-configuration-prerequisites-and-user-rights-in-lync-server-2013"></a>Lync Server 2013의 통화 대기 구성 선행 조건 및 사용자 권한

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-10_

통화 대기는 Enterprise Voice를 배포할 때 기본적으로 설치 되는 통화 관리 기능입니다. 이 항목에서는 통화 대기를 구성 하 고 구성 작업을 수행 하는 데 필요한 사용자 권한을 설정 하기 위해 필요한 사항에 대해 설명 합니다.

<div>


> [!IMPORTANT]  
> 통화 대기 응용 프로그램에 대 한 사용자 지정 음악 저장 파일은 Lync Server 2013 재해 복구 프로세스의 일부로 백업 되지 않으며, 풀에 업로드 된 파일이 손상 되거나 손상 되거나 지워진 경우 파일이 손실 됩니다. 통화 대기를 위해 업로드하는 사용자 지정 대기 음악 파일의 별도 백업 복사본을 항상 유지하십시오.



</div>

이 섹션에서는 통화 대기와 관련 된 계획 설명서 ( [Lync Server 2013의 통화 관리 기능 계획](lync-server-2013-planning-for-call-management-features.md)참조)를 확인 한 것으로 가정 합니다.

<div>

## <a name="call-park-configuration-prerequisites"></a>통화 대기 구성 필요 조건

통화 대기에는 다음 구성 요소가 필요 합니다.

  - 응용 프로그램 서비스

  - 통화 대기 응용 프로그램

이러한 구성 요소는 Enterprise Voice를 배포할 때 자동으로 설치 됩니다.

통화를 대기 하는 동안 발신자가 음악을 들으려면 필요한 음악 파일에도 입력 해야 합니다. 기본 음악 보존 파일은 Enterprise Voice를 배포할 때 자동으로 설치 됩니다. 기본 파일을 해당 사용자의 음악 보존 파일로 대체할 수 있습니다. 통화 대기는 파일 저장소를 사용 하 여 오디오 파일을 저장 합니다.

</div>

<div>

## <a name="call-park-configuration-user-rights"></a>통화 대기 구성 사용자 권한

다음 관리 도구를 사용 하 여 통화 대기를 구성할 수 있습니다.

  - Lync Server 제어판

  - Lync Server 관리 셸

이러한 도구를 사용 하 여 통화 대기 궤도 테이블을 설정 하 고 통화 대기에서 사용 되는 다른 설정을 구성할 수 있습니다.

통화 대기를 구성 하려면 작업에 따라 다음과 같은 관리 역할이 필요 합니다.

  - **CsVoiceAdministrator:** 이 관리자 역할은 모든 음성 관련 설정 및 정책을 만들고 구성 하 고 관리할 수 있습니다.

  - **Csuseradministrator:** 이 관리자 역할은 음성 정책에서 통화 대기를 사용 하도록 설정할 수 있습니다. 또한이 관리자 역할은 모든 음성 구성에 대 한 읽기 전용 보기 액세스 권한을 갖습니다.

  - **Csserveradministrator:** 이 관리자 역할은 서버 및 서비스를 관리, 모니터링 및 문제 해결할 수 있습니다.

  - **Csadministrator:** 이 관리자 역할은 CsVoiceAdministrator, CsServerAdministrator 및 Csserveradministrator의 모든 작업을 수행할 수 있습니다.

<div>


> [!NOTE]  
> 관리 권한에 대 한 자세한 내용은 계획 설명서의 <A href="lync-server-2013-planning-for-role-based-access-control.md">Lync Server 2013에서 역할 기반 액세스 제어에 대 한 계획</A> 을 참조 하십시오.



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

