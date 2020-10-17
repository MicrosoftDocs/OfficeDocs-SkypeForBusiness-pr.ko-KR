---
title: 'Lync Server 2013: 중재 서버용 파일 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc7fd5613b39fd17724c9b62152f9d9401fbc072
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498595"
---
# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a>Lync Server 2013에서 중재 서버용 파일 설치

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-08-06_

이 절차를 성공적으로 완료 하려면 최소한 RTCUniversalReadOnlyAdmins 그룹의 구성원 자격이 있는 도메인 사용자 및 로컬 관리자에 게 서버에 로그온 해야 합니다.

이 항목의 단계를 사용 하 여 Lync server 2013 배포 마법사를 실행 하 여 토폴로지 작성기를 사용 하 여 풀을 정의 하 고 게시할 때 중재 서버 풀에 추가한 컴퓨터에 중재 서버에 대 한 파일을 설치 합니다. 파일 중재 서버를 설치할 때 중재 서버 풀의 각 컴퓨터에 필요한 인증서도 설치 하 고 할당 합니다.

이 사이트에서 이미 배치 된 중재 서버를 프런트 엔드 풀 또는 Standard Edition 서버에 배포한 경우에는이 항목을 건너뛰고 대신 [Lync server 2013에서 트렁크 구성을](lync-server-2013-configuring-trunks.md)계속 진행할 수 있습니다.

<div>


> [!NOTE]  
> 이 항목에서는 배포 설명서에서 " <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">lync server 2013의 토폴로지 작성기에서 중재 서버 정의</A> 및 <A href="lync-server-2013-publish-the-topology.md">2013 토폴로지 게시</A> "에 설명 된 대로 독립 실행형 중재 서버 풀을 이미 정의 하 고 게시 했다고 가정 합니다. 그리고 중재 서버 풀의 컴퓨터가 lync server 2013에서 enterprise voice 용 <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">소프트웨어 필수 구성</A> 요소에 설명 된 필수 구성 요소를 충족 하는지 확인 한 후에는 lync server <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">2013의 기업 voice에 대 한 보안 및 구성 필수 구성 요소</A>를 설치 해야 합니다.



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>독립 실행형 중재 서버 풀 용 파일을 설치 하려면

1.  설치 미디어에서 \<installation media\> ** \\ 설치 \\ amd64 \\Setup.exe**를 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행**을 클릭 합니다.

2.  **설치 위치** 페이지에서 **확인**을 클릭 합니다.

3.  **최종 사용자 사용권 계약** 페이지에서 **동의 함을**클릭 하 고 **확인**을 클릭 합니다. (계속 하는 데 필요 합니다.)

4.  **Lync server 2010 배포 마법사** 페이지에서 **Lync server 시스템 설치 또는 업데이트**를 클릭 합니다.

5.  **1 단계: 로컬 구성 저장소 설치**옆에 있는 **실행**을 클릭 한 다음 화면의 지시를 따릅니다.

6.  **중앙 관리 저장소의 로컬 복제본 구성** 페이지에서 **중앙 관리 저장소에서 직접 기본 검색**을 수락 하 고 **다음**을 클릭 합니다.

7.  **명령 실행** 페이지에서 작업 상태가 **완료**됨으로 표시 되 면 **마침을**클릭 합니다.

8.  **2 단계: Lync Server 구성 요소 설치 또는 제거**옆에 있는 **실행**을 클릭 한 후 **다음**을 클릭 합니다.

9.  **명령 실행** 페이지에서 작업 상태가 **완료**됨으로 표시 되 면 **마침을**클릭 합니다.

10. **3 단계: 인증서 요청, 설치 또는 할당**옆에 있는 **실행**을 클릭 합니다. 기본 설정을 그대로 적용 하 여 화면에 나타나는 지침을 따릅니다. 중재 서버에는 하나의 인증서가 필요 하므로 **3 단계** 를 두 번 실행 하 여 필요한 인증서를 발급 하 고 다시 할당 해야 합니다.

11. 인증서가 올바르게 발급 및 할당 되 면 **4 단계: 서비스 시작**옆에 있는 **실행**을 클릭 한 다음 화면의 지시를 따릅니다.

12. **4 단계가** 성공적으로 완료 되 면 서버를 다시 시작 하 고 domainadmins 그룹의 구성원으로 서버에 로그온 합니다.

13. Lync Server 제어판을 실행 중인 컴퓨터에서, 중재 서버의 서비스 상태가 녹색 확인 표시로 표시 되도록 Lync Server 제어판의 **토폴로지** 페이지를 확인 합니다. 대신 빨간색 X가 나타나면 중재 서버를 선택 합니다. **동작** 메뉴에서 **모든 서비스 시작**을 클릭 합니다.

중재 서버 풀에 둘 이상의 컴퓨터를 추가한 경우 중재 서버 풀의 다른 모든 컴퓨터에서이 절차의 단계를 수행 합니다. 다른 컴퓨터의 중재 서버용 파일을 설치 하지 않아도 되는 경우에는 [Lync server 2013에서 트렁크 구성](lync-server-2013-configuring-trunks.md) 의 절차에 따라이 중재 서버 풀 (또는 사이트의 모든 중재 서버)과 해당 피어 간의 트렁크 연결에 대 한 설정을 구성 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 내부 서버에 대 한 인증서 요구 사항](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

