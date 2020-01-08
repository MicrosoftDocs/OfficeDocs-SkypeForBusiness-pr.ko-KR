---
title: 'Lync Server 2013: Lync 채팅방 시스템 관리 웹 포털 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using the Lync Room System Administrative Web Portal
ms:assetid: c387b2a3-3e42-4642-af72-88126ed2820f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn743660(v=OCS.15)
ms:contentKeyID: 62268951
ms.date: 11/13/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2369cdde9d14275fddf007b5e073c748ce5a8906
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-the-lync-room-system-administrative-web-portal-in-lync-server-2013"></a>Lync Server 2013에서 Lync 채팅방 시스템 관리 웹 포털 사용

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-11-10_

서버에 LRS을 배포한 후에는 브라우저에서 LRS 관리 웹 포털에 로그인 하 여 모든 LRS 채팅방의 상태를 확인할 수 있습니다.

<div>

## <a name="sign-in"></a>서명하세요

1.  다음 URL을 찾습니다.
    
    https://\<fe-서버\>/lrs

2.  LRSSupport 계정 또는 LRSSupportAdminGroup 보안 그룹에 추가 된 계정에 대 한 자격 증명을 입력 합니다.

![Lync 채팅방 시스템 관리 포털 로그인 화면](images/Dn436326.050bcf70-2f3b-46b2-9b96-ebd12679b713(OCS.15).png "Lync 대화방 시스템 관리 포털 로그인 화면")

</div>

<div>

## <a name="lrs-administrative-web-portal-summary-page"></a>LRS 관리 웹 포털 요약 페이지

요약 페이지는 서버에 배포 된 모든 LRS 공간에 대해 다음 정보를 제공 합니다.

  - ****   관리자가 채팅방에 제공 하는 사용자 지정 이름에 태그를 지정 합니다. 룸 이름을 클릭 하 여 포털에서 태그를 설정할 수 있습니다.

  - **상태**   공간 설정 페이지의 상태 섹션 아래에 표시 되는 방에 대 한 집계 상태에서 파생 된 채팅방의 상태 상태입니다.

  - **다음**모임 다음 모임이 예정 된 날짜와 시간입니다.   

  - **LRS 버전, 제조업체, 모델**   이러한 값은 LRS에서 미리 설정 되어 있습니다. 이 필드는 제조업체에 따라 비어 있을 수 있습니다.

  - **마지막 새로 고침**   은 웹 페이지를 마지막으로 새로 고친 시간을 표시 합니다.

![Lync 채팅방 시스템 관리 포털 요약](images/Dn743660.f829ce90-dd95-4725-bd94-6870c5dcf046(OCS.15).png "Lync 대화방 시스템 관리 포털 요약 보기")

</div>

<div>

## <a name="lrs-room-information"></a>LRS 방 정보

포털의 채팅방 정보 섹션을 통해 개별 LRS 방을 보고 구성할 수 있습니다. 여기에는 네 가지 섹션 (설정, 세부 정보, 문제 해결, 상태)이 포함 되어 있습니다.

<div>

## <a name="settings"></a>설정

설정 섹션에서 회의실에 대 한 암호, 방 태그 및 기본 볼륨 수준을 설정할 수 있습니다. 이러한 설정을 구성 하는 경우 LRS 콘솔을 다시 시작한 후에만 변경 내용이 복제 됩니다. 15.12 이상 버전의 Lync 대화방 시스템에 대 한 시스템 업데이트 설정만 표시 됩니다.

![Lync 채팅방 시스템 관리 포털 회의실 설정](images/Dn743660.ab162e19-41ac-4991-9b2a-92575aa53eda(OCS.15).png "Lync 대화방 시스템 관리 포털 방 설정")

</div>

<div>

## <a name="details"></a>세부적인

세부 정보 섹션에는 마지막 새로 고침 시간을 비롯 하 여 LRS 룸의 설정에 대 한 읽기 전용 요약이 제공 됩니다. 다음 모임 마지막 업데이트, 유지 관리 및 보정 기본 스피커, 마이크 및 벨소리 설정 7.0 SIP URI, 각 화면에 대 한 화면 수 및 세부 정보 상태 및 활동.

![Lync 채팅방 시스템 관리 포털 세부 정보](images/Dn743660.2958bbba-db74-4670-a920-87fdfb2fc22d(OCS.15).png "Lync 대화방 시스템 관리 포털 세부 정보 보기")

</div>

<div>

## <a name="troubleshooting"></a>해결사

문제 해결 섹션을 사용 하 여 로그를 원격으로 수집 하 고 지정 된 위치에 저장할 수 있습니다. LRS 콘솔 (LRS 사용자 인터페이스)을 다시 시작 하거나 전체 시스템을 다시 시작할 수도 있습니다. 로그를 수집 하려면 지정 된 형식으로 폴더 경로를 제공 하 고 폴더에 LRS machine 계정에 대 한 쓰기 권한이 있는지 확인 합니다. 로그 크기가 너무 크면 로그 수집을 완료 하는 데 최대 5 분이 걸릴 수 있습니다. 페이지를 새로 고치면 최신 상태가 제공 됩니다.

![Lync 채팅방 시스템 관리 포털 채팅방 로그인](images/Dn743660.749aee71-deaa-4ace-a146-fe2b349f0f42(OCS.15).png "Lync 대화방 시스템 관리 포털 채팅방 로깅")

</div>

<div>

## <a name="health"></a>체력과

상태 섹션에는 Lync Server 연결, 오디오 장치, 비디오 장치, 복구 상태 및 화면 장치의 상태를 시각적으로 보여 줍니다.

![Lync 채팅방 시스템 관리 포털 채팅방 상태](images/Dn743660.8cc644f8-8e3e-42d5-9079-045d8fe9daa7(OCS.15).png "Lync 대화방 시스템 관리 포털 방 상태")

</div>

</div>

<div>

## <a name="additional-notes-about-the-administrative-web-portal"></a>관리 웹 포털에 대 한 추가 참고 사항

<div>


> [!NOTE]  
> <UL>
> <LI>
> <P>설정 변경 사항은 LRS 시스템을 다시 시작한 후에만 적용 됩니다.</P>
> <LI>
> <P>LRSApp 계정 암호가 만료 되는 경우 채팅방의 상태를 볼 수 없게 됩니다. LRSAppuser 계정 암호가 만료 되지 않도록 구성 하거나, 만료가 가까운 경우 암호를 업데이트 해야 합니다.</P>
> <LI>
> <P>LRS 관리 웹 포털은 온-프레미스 배포에만 지원 됩니다.</P></LI></UL>



</div>

</div>

<div>

## <a name="frequently-asked-questions"></a>자주 묻는 질문

<div>

## <a name="why-cant-i-sign-in-to-the-administrative-web-portal"></a>관리 웹 포털에 로그인 할 수 없는 이유는 무엇 인가요?

  - 을 열면 https://localhost/lrs로그인 페이지가 표시 되지만 자격 증명을 입력할 때에는 로그인 할 수 없습니다. 이 경우 열려 https://FQDNofFEserver/lrs 있어야 관리 웹 포털에 로그인 할 수 있습니다.

  - 관리 웹 포털에 액세스 하는 컴퓨터가 작업 그룹에 있는 경우 "http://"가 작동 하지 않습니다. 대신 "https"를 사용 합니다.

</div>

<div>

## <a name="why-cant-i-see-lrs-in-the-administrative-web-portal"></a>관리 웹 포털에 LRS 표시 되지 않는 이유는 무엇 인가요?

  - 배포에 LRS 계정이 있고 LRS 관리 웹 포털 배포 권장 사항에 따라 생성 되었는지 확인 합니다. Lync 서버에서 LRS 계정이 enable-CsMeetingRoom, no-CsUser를 사용 하 여 프로 비전 되었는지 확인 합니다.

  - LRS 계정을 만든 후 관리 웹 포털에서 계정을 볼 수 없는 경우 **MeetingPortal** 구성 요소가 선택 된 Lync server 로깅 도구를 사용 하 여 서버 로그를 수집 하 고이를 LRS 지원 연락처로 보냅니다.

</div>

<div>

## <a name="why-cant-i-see-the-status-of-lrs-in-the-administrative-web-portal"></a>관리 웹 포털에서 LRS의 상태를 볼 수 없는 이유는 무엇 인가요?

  - LRSApp 사용자 계정이 SIP를 사용 하도록 설정 되어 있는지 확인 합니다.

  - 문제가 지속 되는 경우 LRS 시스템의 D **** :\\Tracing\\LRSAdminLogs\\에서 추적 파일을 수집한 다음 LRS 지원 연락처로 보냅니다.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

