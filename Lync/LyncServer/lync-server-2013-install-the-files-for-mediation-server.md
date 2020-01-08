---
title: 'Lync Server 2013: 중재 서버용 파일 설치'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Install the files for Mediation Server
ms:assetid: f0f7dd15-58e1-40fd-aa7e-6db50ceafacd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412998(v=OCS.15)
ms:contentKeyID: 48185772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60274ced1bf72a17b4c05b4908f60bde32323f12
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="install-the-files-for-mediation-server-in-lync-server-2013"></a>Lync Server 2013에서 중재 서버용 파일 설치

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-08-06_

이 절차를 성공적으로 완료 하려면 로컬 관리자와 최소한 RTCUniversalReadOnlyAdmins 그룹의 구성원 자격이 있는 도메인 사용자로 서버에 최소한으로 로그온 해야 합니다.

이 항목의 단계를 사용 하 여 Lync Server 2013 배포 마법사를 실행 하 여 토폴로지 작성기를 사용 하 여 풀을 정의 하 고 게시할 때 중재 서버 풀에 추가한 컴퓨터에 중재 서버용 파일을 설치 합니다. 파일 조정 서버를 설치할 때 중재 서버 풀의 각 컴퓨터에 필요한 인증서를 설치 하 고 할당할 수도 있습니다.

이 사이트에서 이미 프런트 엔드 풀 또는 Standard Edition 서버에 중재 서버 collocated을 배포한 경우에는이 항목을 건너뛰고 대신 [Lync server 2013에서 trunks](lync-server-2013-configuring-trunks.md)를 계속 구성할 수 있습니다.

<div>


> [!NOTE]  
> 이 항목에서는 <A href="lync-server-2013-define-a-mediation-server-in-topology-builder.md">Lync server 2013의 토폴로지 작성기에서 중재 서버 정의</A> 및 배포 설명서의 <A href="lync-server-2013-publish-the-topology.md">lync server 2013에 토폴로지 게시</A> 에 설명 된 대로 독립 실행형 중재 서버 풀을 정의 하 고 게시 했으며, 중재 서버 풀의 컴퓨터가 <A href="lync-server-2013-software-prerequisites-for-enterprise-voice.md">lync Server 2013 enterprise Voice의 소프트웨어 필수</A> 구성 요소에 설명 된 필수 구성 요소에 부합 하는지 확인 했습니다. <A href="lync-server-2013-security-and-configuration-prerequisites-for-enterprise-voice.md">엔터프라이즈 용 보안 및 구성 요구 사항 Lync Server 2013의 음성</A>



</div>

<div>

## <a name="to-install-the-files-for-a-stand-alone-mediation-server-pool"></a>독립 실행형 중재 서버 풀에 대 한 파일을 설치 하려면

1.  설치 미디어에서 설치 미디어 \<\>**\\설정\\amd64\\setup.exe**를 마우스 오른쪽 단추로 클릭 한 다음 **관리자 권한으로 실행**을 클릭 합니다.

2.  **설치 위치** 페이지에서 **확인**을 클릭 합니다.

3.  **최종 사용자 사용권 계약** 페이지에서 **동의 함**을 클릭 한 다음 **확인**을 클릭 합니다. (계속 하는 데 필요 합니다.)

4.  **Lync server 2010 배포 마법사** 페이지에서 **Lync server 시스템 설치 또는 업데이트**를 클릭 합니다.

5.  **1 단계: 로컬 구성 저장소 설치**, **실행**을 차례로 클릭 한 다음 화면의 지침을 따릅니다.

6.  **중앙 관리 저장소의 로컬 복제본 구성** 페이지에서 **중앙 관리 저장소에서 직접 기본 검색**을 수락 하 고 **다음**을 클릭 합니다.

7.  **명령 실행** 페이지에서 작업 상태가 **완료**로 표시 되 면 **마침을**클릭 합니다.

8.  **2 단계: Lync Server 구성 요소 설정 또는 제거**에서 **실행**을 클릭 하 고 **다음**을 클릭 합니다.

9.  **명령 실행** 페이지에서 작업 상태가 **완료**로 표시 되 면 **마침을**클릭 합니다.

10. **3 단계: 인증서 요청, 설치 또는 할당**옆에 있는 **실행**을 클릭 합니다. 화면에 나타나는 지시에 따라 기본 설정을 적용 합니다. 중재 서버에는 하나의 인증서가 필요 하므로 **3 단계** 를 두 번 (필요한 인증서를 발급 하기 위해 한 번) 한 번 실행 하 고 더 많은 작업을 할당 해야 합니다.

11. 인증서가 올바르게 발급 되 고 지정 된 경우 **4 단계: 서비스 시작**, **실행**을 차례로 클릭 한 다음 화면의 지침을 따릅니다.

12. **4 단계가** 성공적으로 완료 되 면 서버를 다시 시작 하 고 서버에 domainadmins 그룹의 구성원으로 로그온 합니다.

13. Lync Server 제어판을 실행 하는 컴퓨터에서 Lync Server 제어판의 **토폴로지** 페이지에서 중재 서버의 서비스 상태가 녹색 확인 표시로 표시 되어 있는지 확인 합니다. 대신 빨간색 X가 나타나면 중재 서버를 선택 합니다. **작업** 메뉴에서 **모든 서비스 시작**을 클릭 합니다.

중재 서버 풀에 둘 이상의 컴퓨터를 추가한 경우 조정 서버 풀의 다른 모든 컴퓨터에서이 절차의 단계를 수행 합니다. 다른 컴퓨터에 대 한 중재 서버용 파일을 설치할 필요가 없는 경우 [Lync server 2013에서 Trunks 구성](lync-server-2013-configuring-trunks.md) 절차에 따라이 중재 서버 풀 (또는 사이트의 모든 중재 서버)과 해당 피어 간의 트렁크 연결에 대 한 설정을 구성 합니다.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013의 내부 서버에 대한 인증서 요구 사항](lync-server-2013-certificate-requirements-for-internal-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

