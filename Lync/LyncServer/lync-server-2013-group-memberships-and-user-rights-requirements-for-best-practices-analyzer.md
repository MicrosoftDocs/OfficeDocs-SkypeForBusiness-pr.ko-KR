---
title: 모범 사례 분석기에 대 한 그룹 구성원 자격 및 사용자 권한 요구 사항
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Group memberships and user rights requirements for Best Practices Analyzer
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48185869
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1a72a7fdc73aeda96a2875ac48fd51b6023ddba
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506075"
---
# <a name="group-memberships-and-user-rights-requirements-for-best-practices-analyzer-in-lync-server-2013"></a>Lync Server 2013의 모범 사례 분석기에 대 한 그룹 구성원 자격 및 사용자 권한 요구 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-21_

모범 사례 분석기를 성공적으로 실행 하려면 로그온 하는 데 사용 하는 사용자 계정이 로컬 컴퓨터에서 Administrators 그룹의 구성원 이어야 합니다. 또한 환경을 검색 하려면 사용자 계정이 다음 그룹의 구성원 이어야 합니다.

  - **도메인 관리자**     Active Directory 도메인 서비스 정보를 열거 하 고 도메인 컨트롤러 및 글로벌 카탈로그 서버에서 WMI (Windows Management Instrumentation) 공급자를 호출 합니다.

  - **관리자**     각 Lync Server 2013 내부 컴퓨터와 각에 지 서버에서 WMI (Windows Management Instrumentation) 공급자를 호출 하 고 레지스트리에 액세스 하는 데 필요 합니다.

  - **RTCUniversalReadOnlyAdmins**     전체 또는 위임 된 읽기 전용 Lync Server 2013 관리 권한

  - **보기 권한만 있는 Exchange 관리자**     Microsoft Exchange 조직에서 전체 또는 위임 된 Exchange 보기 전용 관리자입니다.

사용자 계정에 사용자 권한이 충분 하지 않은 경우 다음과 같은 두 가지 옵션을 사용할 수 있습니다.

  - 명령 프롬프트에서 **runas** 명령을 사용 하 여 사용자 권한이 충분 한 계정으로 도구를 실행 합니다. 구문은 다음과 같습니다.
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - **Active Directory에 연결** 페이지에서 모범 사례 분석기를 실행 하는 데 사용할 계정에 대 한 자격 증명을 설정 합니다. **고급 로그인 옵션 표시**를 클릭 합니다. Active Directory 도메인 서비스에 연결 하는 데 사용할 수 있는 세 가지 계정, 즉 Lync Server 2013 Edge 서버에 연결 하기 위한 계정과 Exchange 서버에 연결 하는 데 사용할 계정을 각각 하나씩 입력 합니다. 이러한 계정을 지정 하지 않으면 모범 사례 분석기를 로그온 하 고 실행 하는 데 사용한 사용자 계정이 사용 됩니다.

</div>

<span> </span>

</div>

</div>

</div>

