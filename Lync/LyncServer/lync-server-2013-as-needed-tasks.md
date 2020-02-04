---
title: 'Lync Server 2013: 필요한 작업'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: As-needed tasks
ms:assetid: b66bc6fe-f138-4cf4-ba7f-aee9a3e0497e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722431(v=OCS.15)
ms:contentKeyID: 63969643
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 344512a1dd4db44b8290efdcc726275b4a6898de
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="as-needed-tasks-in-lync-server-2013"></a>Lync Server 2013의 필요에 따라 작업

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-08-18_

필요에 따라 다음 작업을 수행 합니다. 또한 표준 절차에 따라 자주 적용 됩니다.

  - **전체 보안 감사   ** 이 감사는 메시징 시스템의 업그레이드 또는 다시 디자인에 대 한 응답으로, 또는 성공한 보안 침해에 대 한 응답으로 수행할 수 있습니다. 절차에는 서버와 방화벽의 포트 스캔, 보안 픽스 감사 및 타사 침투 테스트가 포함 될 수 있습니다.

  - **인증서를 만료**   날짜로 바꾸기 Lync Server 인증서는 일반 주간 작업 중 하나 이며, 관리자가 모든 인증서의 만료 날짜에 대 한 기록을 포함 해야 하는 절차의 일부입니다. 이 레코드를 사용 하면 관리자가 특정 인증서가 만료 되 고 필요에 따라 바뀔 때 알림을 만들 수 있습니다.

  - **성능 기준**   업데이트 업그레이드 또는 구성 변경 후 성능 기준을 업데이트 합니다. 조직에서 초기 계획을 사용 하 여 성과 변화를 측정 하 고 시스템 성능에 영향을 주는 문제를 검색할 수 있습니다.

  - **엔터프라이즈 풀**   의 초기 구성, 표준 버전 서버 및 조직 환경의 다른 서버에 대 한 관리는 개별 서버를 배포 하는 동안 수행 되었습니다. 스탠더드 버전 서버와 엔터프라이즈 풀에 대 한 서버 및 풀 배포 후 관리에는 다음 작업이 포함 됩니다.
    
      - 프런트 엔드 서버 관리
    
      - 웹 회의 관리
    
      - 회의 관리
    
      - 서비스 계정 자격 증명 변경
    
      - 데이터베이스 관리
    
      - 서비스 시작 및 중지 및 서버 역할 비활성화
    
      - 서버 및 서버 역할 제거, 풀 제거, 서버 및 풀 서비스 해제

  - **용도 관리 조직**   에 가장 적합 한 기능과 기능을 제공 하도록 Lync Server 2013을 구성할 수 있습니다. 여기에는 다음이 포함 됩니다.
    
      - 온-프레미스 웹 회의 모임에 대 한 지원 관리
    
      - 메일 그룹의 사용을 관리 하 여 인스턴트 메시지 보내기
    
      - 연락처, 현재 상태, 쿼리 관리
    
      - 클라이언트 버전 필터링 구성
    
      - 지능형 IM 필터링 구성
    
      - 보관, 통화 세부 기록, 모임 준수 구성

  - **Edge 서버 연결**   관리 외부 연결을 제공 하는 데 필요한 서버 및 설정의 지속적인 관리에는 다음이 포함 됩니다.
    
      - 내부 서버와 Edge 서버 간 연결 관리
    
      - Edge 서버의 내부 및 외부 인터페이스 및 인증서 구성
    
      - 페더레이션 파트너 액세스 관리

  - **주소록 관리 서버**   관리에는 다음이 포함 됩니다.
    
      - 주소록 서버 전화 번호 정규화 구성
    
      - 명령줄에서 주소록 서버 관리

  - **사용자 계정의 사용자 계정**   관리를 관리 하려면 다음이 포함 됩니다.
    
      - Lync Server에 대 한 사용자 계정 사용
    
      - 마법사를 사용 하 여 Lync Server 사용자 구성
    
      - 개별 Lync Server 사용자 계정 속성 구성
    
      - Lync Server 사용자 검색
    
      - Lync Server 사용자 이동
    
      - Lync Server 사용자 삭제

  - **Lync server 2013 로그 파일**   분석 일반적으로 문제 해결에 사용 되는 매우 유용한 도구는 lync [server 2013 로깅 도구를 사용 하 여](http://technet.microsoft.com/en-us/library/gg558599.aspx)자세히 설명 하는 lync server 2013 로깅 도구입니다.

로깅 도구는 서버 기준으로 로그 파일을 생성 하기 때문에 Microsoft Office Server 12 리소스 키트 도구가 컴퓨터에 설치 되어 있는 경우 Snooper 도구를 사용 하 여 이러한 로그 파일을 보고 분석할 수 있습니다. 그렇지 않으면 Snooper 유틸리티를 사용 하는 것 보다 훨씬 덜 투명 하 고 복잡 한 텍스트 편집기를 사용 하 여 로그를 분석할 수도 있습니다.

프로토콜 메시지를 보고 분석 하려면

로깅 도구에서 디버그 세션을 종료 했으면 로그 파일 분석을 클릭 하 여 Snooper 도구를 사용 하 여 로그 파일을 봅니다. 프로토콜 로그는 다음 구성 요소에 대해 분석할 수 있습니다.

  - SIP (Lync Server SipStack)

  - Lync Server S4 (SIP)

  - Lync Server 컨퍼런스 신호 트래픽 (C3P) (MCU Infra C3P 및 포커스 C3P 포함)

  - PSOM (Lync Server 웹 회의 트래픽)

  - Lync Server 통합 커뮤니케이션 클라이언트 플랫폼 클라이언트 (및 CP)

  - 보관 데이터베이스의 오류 보고서

필요에 따라 작업의 성능을 구성 하는 데 도움이 되도록 필요한 작업의 검사 목록을 참조 하세요.

<div>


> [!IMPORTANT]  
> 자세한 관리 및 관리 절차에 대해서는 Microsoft Lync Server 2013 관리 가이드를 참조 하세요.



</div>

<div>

## <a name="backup-and-restore-policies-or-configuration-settings"></a>정책 또는 구성 설정 백업 (및 복원)

Lync Server 2013를 사용 하면 전체 시스템을 백업 하 고 복원할 수 있습니다. 백업할 Iif (someday restore) 단일 정책 또는 단일 구성 설정 컬렉션을 선택한 다음 적절 한 정책을 검색 하 고 해당 개체를 XML 파일로 저장 하는 Export-Clixml cmdlet에 파이프 합니다.

`Get-CsClientPolicy -Identity "RedmondClientPolicy" | Export-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

이제 RedmondClientPolicy에서 실험 하 고 다양 한 설정을 변경할 수 있습니다. 이전 정책을 복원 하도록 결정 한 경우 다음을 입력 합니다.

`$x = Import-Clixml -Path C:\Backup\RedmondClientPolicy.xml`

`Set-CsClientPolicy -Instance $x`

이 방법은 대부분의 정책 및 설정에 적용 되지만, 여러 하위 개체 (예: 별도의 음성 경로가 여러 개 포함 된 라우팅 구성 설정)를 포함 하는 일부 복잡 한 항목에서는 작동 하지 않습니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

