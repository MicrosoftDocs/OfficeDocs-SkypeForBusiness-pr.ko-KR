---
title: Lync Server 2013 전화 접속 회의 배포 검사 목록
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44591676d69b5fb4ac3d66ce0e18718389a0c189
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a>Lync Server 2013 의 전화 접속 회의 배포 검사 목록

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-10-03_

전화 접속 회의에 필요한 구성 요소는 회의 작업을 배포할 때 배포 됩니다. 전화 접속 회의를 구성 하려면 먼저 엔터프라이즈 음성 또는 중재 서버와 PSTN (공개 전환 전화 네트워크) 게이트웨이를 배포 해야 합니다.

다음 표에 나와 있는 모든 단계는 사용자가 PSTN에서 전화 접속을 하 여 음성/영상 회의에 참가 하기 전에 수행 해야 합니다.

<div>


> [!NOTE]  
> Office Communications Server 2007 R2에서 마이그레이션하는 경우 전화 접속 회의를 배포 하기 전에 Office Communications Server 2007 R2 환경에 최신 업데이트를 적용 해야 합니다.



</div>

### <a name="dial-in-conferencing-deployment-process"></a>전화 접속 회의 배포 프로세스

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>단계의</th>
<th>방법은</th>
<th>필요한</th>
<th>배포 설명서</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>조정 서버 및 PSTN 게이트웨이를 포함 하 여 회의 작업량을 포함 하는 토폴로지를 만들고 프런트 엔드 풀 또는 Standard Edition 서버를 배포 합니다.</strong></p></td>
<td><ol>
<li><p>토폴로지 작성기를 실행 하 여 토폴로지를 구성 합니다. 토폴로지를 구성 하는 동안 전화 접속 회의 옵션을 선택 합니다.</p></li>
<li><p>토폴로지를 게시 하 고 프런트 엔드 풀 또는 Standard Edition 서버를 배포 합니다.</p></li>
<li><p>필요한 경우 독립 실행형 중재 서버를 만들고 PSTN 게이트웨이와 연결 합니다.</p>
<div>

> [!NOTE]  
> 엔터프라이즈 음성을 배포 하지 않고 엔터프라이즈 EditionFront End Server 또는 Standard Edition Server와 중재 서버를 collocate 하지 않는 경우에만이 단계가 필요 합니다. 엔터프라이즈 음성을 배포 하는 경우 엔터프라이즈 음성 배포의 일부로 중재 서버와 PSTN 게이트웨이를 설치 하 고 구성 합니다. 중재 서버를 collocate 경우에는 프런트 엔드 풀 또는 Standard Edition Server 배포의 일부로 중재 서버를 설치 하 고 구성 합니다.


</div></li>
</ol></td>
<td><p>도메인 관리자</p>
<p>RTCUniversalServerAdmins</p>
<p>관리자</p></td>
<td><ul>
<li><p><a href="lync-server-2013-deploying-lync-server.md">Lync Server 2013 배포</a></p></li>
<li><p>독립 실행형 중재 서버 풀을 만들려면 다음을 수행 합니다. <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Lync server 2013에서 중재 서버 배포 및 피어 정의</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>다이얼 플랜 구성</strong></p></td>
<td><p>다이얼 플랜은 전화 인증 및 통화 라우팅과 관련 하 여 특정 위치에서 전화를 거는 번호를 단일 표준 (E) 형식으로 변환 하는 일련의 전화 번호 정규화 규칙입니다. 다른 위치에서 전화를 거는 같은 번호는 각각의 다이얼 플랜을 기준으로 각 위치에 따라 다른 전자 164 번호로 확인 될 수 있습니다. 엔터프라이즈 음성을 배포 하는 경우에는 해당 배포의 일부로 다이얼 플랜을 설정 하 고 다이얼 인 회의도 함께 사용할 수 있는지 확인 해야 합니다. 엔터프라이즈 음성을 배포 하지 않는 경우 전화 접속 회의를 위한 다이얼 플랜을 설정 해야 합니다.</p>
<p>Lync Server 2013 제어판 또는 Lync Server 관리 셸을 사용 하 여 다음과 같이 다이얼 플랜을 설정 합니다.</p>
<ol>
<li><p>전화 접속 액세스 전화 번호를 라우팅하기 위해 하나 이상의 다이얼 플랜을 만듭니다.</p></li>
<li><p>각 풀에 기본 다이얼 플랜을 할당 합니다. 전화 접속 <strong>회의 지역을</strong> 다이얼 플랜을 적용할 지리적 위치로 설정 합니다. 지역에서 다이얼 플랜을 전화 접속 액세스 번호와 연결 합니다.</p></li>
</ol></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Lync Server 2013에서 전화 접속 회의에 대한 다이얼 플랜 구성</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>다이얼 플랜에 영역이 할당 되어 있는지 확인</strong></p></td>
<td><p><strong>Get-CsDialPlan 플랜</strong> 및 <strong>Set-csdialplan 플랜</strong> cmdlet을 실행 하 여 모든 다이얼 플랜에 지역이 지정 되어 있는지 확인 합니다.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsVoiceAdministrator</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">다이얼 플랜 설정 Lync 서버 2013에 지역이 지정 되어 있어야 합니다.</a></p></td>
</tr>
<tr class="even">
<td><p><strong>) 사용자 개인 id 번호 (PIN) 요구 사항 확인 또는 수정</strong></p></td>
<td><p>Lync Server 2013 제어판 또는 Lync Server 관리 셸을 사용 하 여 회의 <strong>PIN 정책을</strong>보거나 수정할 수 있습니다. 최소 PIN 길이, 최대 로그온 시도 횟수, PIN 만료, 공통 패턴 허용 여부를 지정할 수 있습니다.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(선택 사항) Lync Server 2013에서 PIN 정책 설정 확인</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>전화 접속 회의를 지원 하도록 회의 정책 구성</strong></p></td>
<td><p>Lync Server 2013 제어판 또는 Lync Server 관리 셸을 사용 하 여 <strong>회의 정책</strong> 설정을 구성 합니다. 여부 지정:</p>
<ul>
<li><p>PSTN 회의 전화 접속을 사용할 수 있습니다.</p></li>
<li><p>사용자가 익명 참가자를 초대할 수 있습니다.</p></li>
<li><p>인증 되지 않은 사용자는 전화 걸기 phoning를 사용 하 여 회의에 참가할 수 있습니다. 전화 걸기 phoning를 사용 하 여 회의 서버는 사용자에 게 전화를 걸고 사용자는 해당 휴대폰에 응답 하 여 회의에 참가할 수 있습니다.</p></li>
</ul></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Lync Server 2013에서 전화 접속에 대한 회의 정책 구성</a></p></td>
</tr>
<tr class="even">
<td><p><strong>전화 접속 액세스 번호 구성</strong></p></td>
<td><p>Lync Server 2013 제어판 또는 Lync Server Management Shell을 사용 하 여 전화 접속 액세스 번호를 설정 하 여 사용자가 회의에 전화를 걸고 해당 전화 접속 계획에 액세스 번호를 연결 하는 지역을 지정 합니다. 이끌이 다이얼 플랜에서 지정한 영역의 처음 세 개 액세스 번호는 회의 초대에 포함 됩니다. 모든 액세스 번호는 전화 접속 회의 설정 페이지에서 사용할 수 있습니다.</p>
<div>

> [!NOTE]  
> 전화 접속 액세스 번호를 만든 후에는 <STRONG>CsDialInConferencingAccessNumber</STRONG> cmdlet을 사용 하 여 Active Directory 연락처 개체의 표시 이름을 수정 하 고 사용자가 올바른 액세스 번호를 더 쉽게 식별할 수 있도록 설정할 수 있습니다.


</div></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Lync Server 2013에서 전화 접속 회의 액세스 번호 구성</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>(선택 사항) 전화 접속 회의 설정 확인</strong></p></td>
<td><p><strong>CsDialinConferencingAccessNumber</strong> cmdlet을 사용 하 여 액세스 번호 및 지역이 지정 되지 않은 액세스 번호에 사용 되지 않는 전화 접속 회의 영역이 있는 다이얼 플랜을 검색할 수 있습니다.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p>
<p>Csviewadministrator</p>
<p>CsHelpDesk</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(선택 사항) Lync Server 2013에서 전화 접속 회의 설정 확인</a></p></td>
</tr>
<tr class="even">
<td><p><strong>) DTMF 명령의 키 매핑 수정</strong></p></td>
<td><p><strong>CsDialinConferencingDtmfConfiguration</strong> cmdlet을 사용 하 여 참가자가 전화 회의 설정을 제어 하는 데 사용할 수 있는 DTMF (듀얼 톤 multifrequency) 명령에 사용 되는 키를 수정 합니다 (예: 음소거 및 음소거 해제 또는 잠금 및 잠금 해제).</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(선택 사항) Lync Server 2013에서 DTMF 명령에 대한 키 매핑 수정</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>) 컨퍼런스 참가 및 알림 종료 동작 수정</strong></p></td>
<td><p><strong>CsDialinConferencingConfiguration</strong> 를 사용 하 여 참가자가 회의에 참가 하 고 나갈 때 알림이 작동 하는 방식을 변경할 수 있습니다.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(선택 사항) Lync Server 2013에서 회의 참가/나가기 알림 활성화/비활성화</a></p></td>
</tr>
<tr class="even">
<td><p><strong>(선택 사항) 전화 접속 회의 확인</strong></p></td>
<td><p><strong>CsDialInConferencing</strong> cmdlet을 사용 하 여 지정 된 풀에 대 한 액세스 번호가 올바르게 작동 하는지 테스트 합니다.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsServerAdministrator</p>
<p>CsAdministrator</p></td>
<td><p><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(선택 사항) Lync Server 2013에서 전화 접속 회의 확인</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>Lync 2013용 온라인 모임 추가 기능 배포</strong></p></td>
<td><p>사용자가 전화 접속 회의를 지 원하는 회의 일정을 예약할 수 있도록 Lync 2013에 대 한 온라인 모임 추가 기능을 배포 합니다. Lync 2013을 설치 하면 Lync 2013의 온라인 모임 추가 기능이 자동으로 설치 됩니다.</p></td>
<td><p>관리자</p></td>
<td><p><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Lync 2013용 온라인 모임 추가 기능 배포</a></p></td>
</tr>
<tr class="even">
<td><p><strong>사용자 계정 설정 구성</strong></p></td>
<td><p>Lync Server 2013 제어판 또는 Lync Server Management Shell을 사용 하 여 전화 통신 <strong>회선 URI</strong> 를 고유한 정규화 된 전화 번호 (예: tel: + 14255550200)로 구성 합니다.</p></td>
<td><p>RTCUniversalServerAdmins</p>
<p>CsAdministrator</p>
<p>CsUserAdministrator</p></td>
<td><p><a href="lync-server-2013-configure-user-account-settings.md">Lync Server 2013에서 사용자 계정 설정 구성</a></p></td>
</tr>
<tr class="odd">
<td><p>권장 컨퍼런스 디렉터리 구성</p></td>
<td><p><strong>CsConferenceDirectory</strong> cmdlet을 사용 하 여 풀의 모든 999 사용자에 대해 하나의 회의 디렉터리를 만듭니다.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013의 전화 접속 회의 요구 사항</a> <a href="recommended-create-conference-directories.md">(권장) 전화 회의 디렉터리 만들기</a></p></td>
</tr>
<tr class="even">
<td><p><strong>) 사용자가 전화 접속 회의를 시작 하 고 초기 PIN 설정</strong></p></td>
<td><p><strong>CsPinSendCAWelcomeMail</strong> 스크립트를 사용 하 여 사용자의 초기 핀을 설정 하 고 초기 PIN 및 전화 접속 회의 설정 페이지로 연결 되는 링크가 포함 된 환영 전자 메일을 보낼 수 있습니다.</p></td>
<td><p>RTCUniversalServerAdmins</p></td>
<td><p><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(선택 사항) Lync Server 2013에서 사용자에게 전화 접속 회의 시작 메시지 보내기</a></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

