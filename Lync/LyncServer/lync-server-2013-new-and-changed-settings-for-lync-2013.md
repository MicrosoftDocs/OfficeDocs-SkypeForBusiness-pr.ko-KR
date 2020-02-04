---
title: 'Lync Server 2013: Lync 2013의 새로 만들기 및 변경 된 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New and changed settings for Lync 2013
ms:assetid: bb13789c-7eda-461c-a387-02ea8ca4dabe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205204(v=OCS.15)
ms:contentKeyID: 48185241
ms.date: 12/08/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb5366f7e3d4c2aba81b5b8b25873ea22d54c3a6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765849"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a>Lync 2013의 새로운 설정 및 변경 됨

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-12-05_

이 항목에서는 클라이언트 관리와 직접 관련 된 Lync Server Management Shell cmdlet의 변경 내용에 대해 설명 합니다. Lync Server 2013에는 몇 가지 새로운 매개 변수와 다른 방법을 통해 구성할 수 있는 기능에 대 한 deprecates 매개 변수가 도입 되었습니다.

<div>

## <a name="new-client-management-parameters"></a>새 클라이언트 관리 매개 변수


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>새로운</th>
<th>Lync Server 관리 셸 Cmdlet</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TracingLevel</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>True로 설정 하면 소프트웨어 추적이 Lync에서 사용 하도록 설정 됩니다. False로 설정 되 면 소프트웨어 추적이 사용 되지 않습니다. 소프트웨어 추적은 프로그램에서 수행 하는 모든 것에 대 한 자세한 기록 (API 호출 추적 포함)을 포함 합니다. 추적은 개발자와 응용 프로그램 지원 담당자에 게 주로 유용 합니다. 이 설정은 통신 서버 2007 R2 그룹 정책 설정 &quot;에 해당 하는 것과 같으며 Communicator 추적을 설정 합니다. &quot; 설정은 다음과 같습니다.</p>
<ul>
<li><p>Off = 추적을 사용할 수 없으며 사용자는이 설정을 변경할 수 없습니다.</p></li>
<li><p>Light = 최소 추적을 수행 하 고 사용자가이 설정을 변경할 수 없습니다.</p></li>
<li><p>On = Verbose 추적을 수행 하 고 사용자가이 설정을 변경할 수 없습니다.</p></li>
</ul>
<p>기본적으로 TracingLevel는 null 값으로 설정 됩니다. 즉, 최소한의 추적이 수행 되지만, 사용자는이 최소 추적을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>EnableMediaRedirection</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>True ($True)로 설정 된 경우 오디오 및 비디오 스트림을 다른 네트워크 트래픽과 분리할 수 있으므로 클라이언트 장치에서 오디오 및 비디오를 로컬로 인코딩 및 디코딩하는 것을 허용 합니다. 미디어 리디렉션은 일반적으로 대역폭 사용량을 낮추고, 서버 확장성을 높이 며, 장치 remoting 또는 코덱 압축과 같은 유사한 기술에 비해 최적화 된 사용자 환경을 제공 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>True로 설정 하면 모든 Lync 모임이 큰 모임으로 &quot;처리 됩니다. &quot; 대용량 모임이 있으면 기본적으로 전송 되는 모임 명단의 크기 외에도 참가자에 게 전송 되는 알림 수에 제한이 적용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>True ($True)로 설정 하면 사용자가 회의에 사용 되는 PowerPoint 슬라이드에 주석을 추가할 수 없습니다. 그러나 AllowAnnotations 속성 값에 따라 사용자는 여전히 다른 whiteboarding 기능에 액세스할 수 있습니다. 기본값은 False로, PowerPoint 주석이 허용 됨을 의미 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>True (기본값)로 설정 되 면 회의에 연결 된 열려 있는 OneNote 전자 필기장이 자동으로 회의 참가자, 회의 중에 공유 된 콘텐츠에 대 한 세부 정보로 업데이트 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>다른 새로운 CsMeetingConfiguration 매개 변수와 함께 사용 하 여 Lync 2013의 온라인 모임 추가 기능에서 생성 된 모임 초대를 사용자 지정 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Lync 2013의 온라인 모임 추가 기능에서 생성 된 모든 초대에 조직의 로고를 추가 합니다. GIF 또는 JPG 이미지의 URL을 지정 합니다.</p></td>
</tr>
<tr class="even">
<td><p>도움말 Url</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Lync 2013의 온라인 모임 추가 기능에서 생성 된 모든 초대에 조직의 도움말 또는 지원 URL을 추가 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Lync 2013의 온라인 모임 추가 기능에서 생성 된 모든 초대에 법적 고 지 사항 텍스트를 추가 합니다. 텍스트의 위치에 대 한 URL을 지정 합니다.</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>CsMeetingConfiguration</p></td>
<td><p>Lync 2013의 온라인 모임 추가 기능에서 생성 된 모든 초대에 사용자 지정 바닥글을 추가 합니다. 사용자 지정 바닥글 텍스트의 위치에 대 한 URL을 지정 합니다.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a>사용 되지 않는 클라이언트 관리 매개 변수


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>매개 변수</th>
<th>Lync Server 관리 셸 Cmdlet</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CustomizedHelpUrl</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>이 매개 변수는 Lync Server 2013에서 더 이상 사용 되지 않습니다. EnableEnterpriseCustomizedHelp와 함께 사용 하는 경우이 매개 변수는 조직에서 사용자가 Lync의 도움말 메뉴를 클릭할 때 사용자 지정 된 도움말이 표시 되도록 해당 URL을 지정 하도록 설정 했습니다.</p></td>
</tr>
<tr class="even">
<td><p>EnableEnterpriseCustomizedHelp</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>이 매개 변수는 Lync Server 2013에서 더 이상 사용 되지 않습니다. CustomizedHelpUrl와 함께 사용 하는 경우이 매개 변수는 조직에서 사용자 지정 된 도움말을 표시할 수 있도록 설정 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>Lync Server 2013에서 Set CSClientPolicy cmdlet의 EnableSQMData 매개 변수가 제거 되었습니다. 대신 SQM (소프트웨어 품질 관리) 데이터에 대 한 공유 그룹 정책 설정을 사용 하 여 Lync 클라이언트 일반 옵션 페이지의 사용자 환경 개선 옵션에 대 한 사용자 인터페이스를 결정할 수 있습니다.</p>
<p>HKEY_CURRENT_USER \Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>최대값</p>
<p>1 = 확인란을 표시 하 고 선택 합니다 (사용자가 체크 상자를 지울 수 있음).</p>
<p>0 = 해제 하 고 확인란을 사용 하지 않도록 설정 합니다 (사용자가 무시할 수 없음).</p>
<p>Null = 값은 Office 설정에 따라 결정 되며 사용자가 선택 하는 대로 설정할 수 있는 확인란이 표시 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>이 매개 변수는 제거 되었습니다. 대신 Lync Server 2013을 배포 하 고 토폴로지를 게시 하면 모든 사용자에 대해 통합 대화 저장소가 기본적으로 사용 하도록 설정 됩니다. 즉, 모든 사용자의 연락처가 Exchange에 유지 되 고 Lync, Outlook, Outlook Web Access에서 사용할 수 있습니다. Set-Csuser서비스 정책 cmdlet을 사용 하 여 통합 된 연락처 저장소를 사용할 수 있는 사용자를 사용자 지정할 수 있습니다. 사이트, 테 넌 트 또는 개인 또는 개인 그룹을 기준으로 사용자를 전역적으로 사용할 수 있습니다. 자세한 내용은 <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Lync Server 2013에서 통합 대화 저장소에 사용자 사용</a>을 참조 하세요.</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>이 매개 변수는 Lync 2013에서 사용 되지 않습니다. 이전 릴리스에서이 매개 변수는 클라이언트가 Exchange 공용 폴더에서 MAPI 데이터를 검색 하는 빈도를 지정 합니다.</p></td>
</tr>
<tr class="even">
<td><p>DisableICE</p></td>
<td><p>CsClientPolicy</p></td>
<td><p>이 매개 변수는 Lync 2013에서 더 이상 사용 되지 않습니다.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

