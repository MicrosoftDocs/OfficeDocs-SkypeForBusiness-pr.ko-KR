---
title: Lync Server 2013 파일럿 풀 배포
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploy Lync Server 2013 pilot pool
ms:assetid: 19c27053-8b21-401f-ad91-75c2dd355e91
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204718(v=OCS.15)
ms:contentKeyID: 48183539
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46e6d4bd34c20038e430323b0f78ccf4f918aa62
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724048"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploy-lync-server-2013-pilot-pool"></a>Lync Server 2013 파일럿 풀 배포

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-11-22_

Lync Server 2013 마이그레이션에 필요한 첫 번째 단계 중 하나는 파일럿 풀을 배포 하는 것입니다. 파일럿 풀은 Office Communications Server 2007 R2 배포를 사용 하 여 Lync Server 2013 공존을 테스트 하는 위치입니다. 공존은 모든 사용자와 풀을 Lync Server 2013로 이동할 때까지 지속 되는 임시 상태입니다.

파일럿 풀을 배포 하는 경우 새 프런트 엔드 풀 정의 마법사를 사용 합니다. Office Communications Server 2007 R2 풀에 있는 Lync Server 2013 파일럿 풀에 동일한 기능 및 작업을 배포 해야 합니다. Office Communications Server 2007 R2 환경을 보관 또는 모니터링 하기 위해 보관 서버, 모니터링 서버 또는 System Center Operations Manager를 배포한 경우 마이그레이션 전체에서 보관 또는 모니터링을 계속 하려면 다음을 수행 해야 합니다. 또한 이러한 기능을 시험 운용 환경에 배포 합니다. Office Communications Server 2007 R2 environment를 보관 하거나 모니터링 하기 위해 배포한 버전이 Lync Server 2013 환경에서 데이터를 캡처하지 않습니다.

<div>


> [!NOTE]  
> 다음 절차에서는 전체 파일럿 풀 배포 프로세스의 일부로 고려해 야 하는 기능과 설정에 대해 설명 합니다. 이 섹션에서는 파일럿 풀 배포의 일부로 고려해 야 하는 주요 요점만 중점적으로 설명 합니다. 자세한 단계는 <A href="lync-server-2013-deploying-lync-server.md">Lync Server 2013</A> 배포 가이드 배포를 참조 하세요.



</div>

**Lync Server 2013 파일럿 풀을 배포 하려면**

1.  도메인 관리자 그룹 및 RTCUniversalServerAdmins 그룹의 구성원으로 토폴로지 작성기가 설치 된 컴퓨터에 로그온 합니다.

2.  토폴로지 작성기를 열고 새 토폴로지를 만들도록 선택 합니다.

3.  기본 SIP 도메인을 입력 합니다.
    
    ![새 토폴로지 만들기, 주 도메인 정의 페이지](images/JJ204718.68775d87-f32c-494a-8386-6d4c81e81284(OCS.15).jpg "새 토폴로지 만들기, 주 도메인 정의 페이지")

4.  **새 프런트 엔드 풀 정의** 마법사에 도달할 때까지 마법사를 계속 완료 합니다. 다음을 클릭 합니다.

5.  풀 FQDN을 입력 합니다. 파일럿 풀을 정의할 때 Enterprise Edition 프런트 엔드 풀 또는 Standard Edition 서버를 배포 하도록 선택할 수 있습니다. Lync Server 2013에는 이전 풀에 배포 된 것과 일치 하는 파일럿 풀 기능이 필요 하지 않습니다.
    
    <div>
    

    > [!WARNING]  
    > 파일럿 풀에 대해 정의한 풀 또는 서버 FQDN (정규화 된 도메인 이름)이 고유 해야 합니다. 현재 배포 된 Office Communications Server 2007 R2 풀 또는 현재 배포 되는 다른 서버 이름과 일치 시킬 수 없습니다.

    
    </div>
    
    ![프런트 엔드 풀 FQDN 정의 페이지](images/JJ204718.5ff4336c-13fa-47cc-899b-066f267eb3f0(OCS.15).jpg "프런트 엔드 풀 FQDN 정의 페이지")

6.  풀에 추가 될 컴퓨터를 정의 합니다.
    
    ![새 프런트 엔드 풀 정의 대화 상자](images/JJ204718.374f0ed4-988b-465f-9861-8d1db401e76f(OCS.15).jpg "새 프런트 엔드 풀 정의 대화 상자")

7.  **기능 선택** 페이지에서이 프런트 엔드 풀에 대해 원하는 기능에 해당 하는 확인란을 선택 합니다. 예를 들어 인스턴트 메시지 (IM) 및 현재 상태 기능만 배포 하는 경우에는 회의 확인란을 선택 하 여 단체 메신저를 허용 하 되 전화 접속 (PSTN) 회의, 엔터프라이즈 음성 또는 통화 허용 제어 확인란을 선택 하지 않습니다. 음성, 영상, 공동 작업 회의 기능을 나타냅니다. 기능을 선택 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync server 2013에서 프런트 엔드 풀 또는 Standard Edition 서버 정의 및 구성을](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) 참조 하세요.
    
    ![프런트 엔드 풀 기능 선택 페이지](images/JJ204718.5c3f3ff9-6e17-4d66-9b13-3bd55b38246b(OCS.15).jpg "프런트 엔드 풀 기능 선택 페이지")

8.  **Collocated 서버 역할 선택** 페이지에서 Lync server 2013에서 중재 서버를 collocate 하는 것이 좋습니다. Lync Server 2013에서 레거시 토폴로지를 병합할 때 먼저 Office Communications Server 2007 R2 중재 서버를 collocate 해야 합니다. 토폴로지를 병합 하 고 Lync Server 2013 조정 서버를 구성한 후에는 배포에서 조정 서버 역할을 Lync Server 2013로 이동할 때 collocated 중재 서버를 유지할지 또는 독립 실행형 서버로 변경할지를 결정할 수 있습니다. 프로세스.
    
    ![프런트 엔드 풀 배치된 서버 역할 선택 페이지](images/JJ204718.e00b7eba-010b-44ed-b0a6-6ab3e534fb8c(OCS.15).jpg "프런트 엔드 풀 배치된 서버 역할 선택 페이지")

9.  이 프런트 엔드 풀을 사용 하 여 **서버 역할 연결** 페이지에서 파일럿 풀 배포 중에 **Edge 풀을이 프론트 엔드 풀의 미디어 구성 요소에서 사용할 수 있도록 설정** 합니다 옵션을 선택 하지 마세요. 이 기능을 사용 하 여 이후 마이그레이션 단계에서 온라인 상태로 만들 수 있습니다. 지금은이 설정을 지워짐 상태로 유지 합니다.
    
    ![프런트 엔드 풀과 서버 역할 연결 페이지](images/JJ204718.2d95a798-ad76-4dad-9392-ce41f4d938d1(OCS.15).jpg "프런트 엔드 풀과 서버 역할 연결 페이지")

10. **Office Web Apps 서버 선택** 페이지에서 **새로 만들기**를 클릭 하 고 응용 프로그램 서버의 FQDN을 지정 합니다.
    
    ![새 Office Online 서버 FQDN 속성 정의](images/JJ204718.25c6b455-f1b8-4326-a569-6e338153d398(OCS.15).jpg "새 Office Online 서버 FQDN 속성 정의")

11. **Sql server 스토어 보관 정의** 페이지에서 Lync server 2013에 대해 이전에 만든 sql Server 인스턴스를 선택 합니다.
    
    ![보관 SQL Server 저장소 정의 페이지](images/JJ204718.0f76f1dc-d0d7-42a0-aea3-400b8e1f35cd(OCS.15).jpg "보관 SQL Server 저장소 정의 페이지")

12. **SQL Server 모니터링 서버 저장소 정의** 페이지에서 Lync server 2013에 대해 이전에 만든 sql server 인스턴스를 선택 합니다. **마침**을 클릭합니다.

13. 토폴로지 작성기의 위쪽 노드에서 **Lync Server** 를 마우스 오른쪽 단추로 클릭 하 고 **속성 편집을 클릭 합니다.** **간단한 url**을 클릭 합니다.

14. **관리 액세스 URL**을 업데이트 합니다.
    
    ![속성 편집, 단순 URL 페이지](images/JJ204718.ef596dd2-1983-47e0-b342-4fc7a0e36380(OCS.15).jpg "속성 편집, 단순 URL 페이지")
    
    간단한 Url에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 간단한 Url 편집 또는 구성](lync-server-2013-edit-or-configure-simple-urls.md) 항목을 참조 하세요.

15. **편집 속성**에서 **중앙 관리 서버**를 클릭 합니다.

16. 드롭다운 목록에서 Lync Server 2013 풀을 선택 합니다.
    
    ![속성 편집, 중앙 관리 서버 페이지](images/JJ204718.211955fc-85f2-462d-8709-e6ea67092e89(OCS.15).jpg "속성 편집, 중앙 관리 서버 페이지")

17. 확인을 클릭 하 여 **속성 편집** 페이지를 닫습니다.

18. **작업** 메뉴에서 **토폴로지 게시**를 선택 합니다.

19. 게시 프로세스가 완료 되 면 **마침을**클릭 합니다.

20. Lync Server 2013 배포 마법사로 돌아가면 **Lync Server 시스템 설치 또는 업데이트**를 클릭 합니다.
    
    ![Lync Server 2013 배포 마법사](images/JJ204718.fb05adef-ad29-4905-9090-d409261b0e48(OCS.15).jpg "Lync Server 2013 배포 마법사")

구성 저장소의 로컬 복사본을 설치 하 고 필수 서비스를 시작 하려면 배포 설명서에서 [Lync Server 2013 프런트 엔드 서버 및 프런트 엔드 풀 설정을](lync-server-2013-setting-up-front-end-servers-and-front-end-pools.md) 참조 하세요.


</div>

<span> </span>

</div>

</div>

</div>

