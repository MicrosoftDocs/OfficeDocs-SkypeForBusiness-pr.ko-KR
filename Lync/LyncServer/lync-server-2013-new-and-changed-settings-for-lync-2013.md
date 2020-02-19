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
ms.openlocfilehash: ba26f3175f461f0cdc68924b20c1413bf13a2b41
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42128121"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-and-changed-settings-for-lync-2013"></a>Lync 2013의 새로 만들기 및 변경 된 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-12-05_

이 항목에서는 클라이언트 관리와 직접 관련 된 Lync Server 관리 셸 cmdlet의 변경 사항에 대해 설명 합니다. Lync Server 2013에는 몇 가지 새로운 매개 변수와 다른 방법을 통해 구성할 수 있는 기능에 대 한 deprecates 매개 변수가 도입 되었습니다.

<div>

## <a name="new-client-management-parameters"></a>새로운 클라이언트 관리 매개 변수


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>New</th>
<th>Lync Server 관리 셸 Cmdlet</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TracingLevel</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>True로 설정 하면 소프트웨어 추적이 Lync에서 사용 됩니다. False로 설정 하면 소프트웨어 추적이 사용 되지 않습니다. 소프트웨어 추적은 API 통화 추적을 비롯하여 프로그램이 수행하는 모든 작업에 대한 자세한 기록을 유지합니다. 추적은 개발자와 응용 프로그램 지원 담당자에 게 대부분 유용 합니다. 이 설정은 Communications Server 2007 R2 그룹 정책 설정과 &quot;Communicator에 대 한 추적을 설정 하는 것과 동일 합니다. &quot; 설정은 다음과 같습니다.</p>
<ul>
<li><p>Off = 추적을 사용할 수 없고 사용자가 이 설정을 변경할 수 없습니다.</p></li>
<li><p>Light = 최소한의 추적이 수행되고 사용자가 이 설정을 변경할 수 없습니다.</p></li>
<li><p>On = 자세한 추적이 수행되고 사용자가 이 설정을 변경할 수 없습니다.</p></li>
</ul>
<p>기본적으로 TracingLevel은 null 값으로 설정됩니다. 즉, 최소한의 추적이 수행되지만 사용자가 이 최소한의 추적을 사용하거나 사용하지 않도록 설정할 수 없습니다.</p></td>
</tr>
<tr class="even">
<td><p>EnableMediaRedirection</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>True($True)로 설정하면 오디오 및 비디오 스트림을 다른 네트워크 트래픽과 분리할 수 있습니다. 따라서 클라이언트 장치에서 로컬로 오디오 및 비디오의 인코딩과 디코딩을 수행할 수 있습니다. 일반적으로 미디어 리디렉션은 장치 원격 사용 또는 코덱 압축과 같은 유사한 방법에 비해 대역폭 사용 감소, 서버 확장성 향상, 사용자 환경 최적화 측면에서 더욱 효과적입니다.</p></td>
</tr>
<tr class="odd">
<td><p>AllowLargeMeetings</p></td>
<td><p>CsConferencing</p></td>
<td><p>True로 설정 하면 모든 Lync 모임이 대규모 모임으로 &quot;취급 됩니다. &quot; 모임이 많은 경우에는 기본적으로 전송 되는 모임 명단의 크기 외에도 참석자에 게 전송 되는 알림 수에 제한이 적용 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>DisablePowerPointAnnotations</p></td>
<td><p>CsConferencing</p></td>
<td><p>True($True)로 설정하면 사용자가 전화 회의에 사용되는 PowerPoint 슬라이드에 주석을 추가할 수 없습니다. 그러나 AllowAnnotations 속성의 값에 따라 사용자가 다른 화이트보드 기능에 여전히 액세스할 수 있습니다. 기본값은 False입니다. 즉, PowerPoint 주석을 사용할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>AllowSharedNotes</p></td>
<td><p>CsConferencing</p></td>
<td><p>True(기본값)로 설정하면 전화 회의에 연결된 열려 있는 모든 OneNote 전자 필기장이 전화 회의 참가자 및 전화 회의 중 공유되는 콘텐츠 정보와 같은 정보를 포함하여 자동으로 업데이트됩니다.</p></td>
</tr>
<tr class="even">
<td><p>EnableInviteCustomization</p></td>
<td><p>Get-csmeetingconfiguration</p></td>
<td><p>다른 새 Get-csmeetingconfiguration 매개 변수와 함께 사용 되어 Lync 2013에 대 한 온라인 모임 추가 기능에서 생성 된 모임 초대를 사용자 지정 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>LogoURL</p></td>
<td><p>Get-csmeetingconfiguration</p></td>
<td><p>Lync 2013 용 온라인 모임 추가 기능에서 생성 된 모든 초대에 조직의 로고를 추가 합니다. GIF 또는 JPG 이미지의 URL을 지정하면 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>도움말 Url</p></td>
<td><p>Get-csmeetingconfiguration</p></td>
<td><p>Lync 2013 용 온라인 모임 추가 기능에서 생성 된 모든 초대에 조직의 도움말 또는 지원 URL을 추가 합니다.</p></td>
</tr>
<tr class="odd">
<td><p>LegalURL</p></td>
<td><p>Get-csmeetingconfiguration</p></td>
<td><p>Lync 2013에 대 한 온라인 모임 추가 기능에서 생성 한 모든 초대에 법적 텍스트 또는 고 지 사항을 추가 합니다. 텍스트 위치의 URL을 지정하면 됩니다.</p></td>
</tr>
<tr class="even">
<td><p>CustomFooterText</p></td>
<td><p>Get-csmeetingconfiguration</p></td>
<td><p>Lync 2013 용 온라인 모임 추가 기능에서 생성 된 모든 초대에 사용자 지정 바닥글을 추가 합니다. 사용자 지정 바닥글 텍스트 위치의 URL을 지정하면 됩니다.</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="deprecated-client-management-parameters"></a>더 이상 사용되지 않는 클라이언트 관리 매개 변수


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
<td><p>Set-csclientpolicy</p></td>
<td><p>이 매개 변수는 Lync Server 2013에서 더 이상 사용 되지 않습니다. EnableEnterpriseCustomizedHelp와 함께 사용 하는 경우이 매개 변수를 사용 하도록 설정 하면 조직에서 Lync의 도움말 메뉴를 클릭할 때 사용자 지정 된 도움말이 표시 되도록 URL을 지정할 수 있습니다.</p></td>
</tr>
<tr class="even">
<td><p>EnableEnterpriseCustomizedHelp</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>이 매개 변수는 Lync Server 2013에서 더 이상 사용 되지 않습니다. 이 매개 변수를 CustomizedHelpUrl와 함께 사용 하면 조직에서 사용자 지정 도움말을 표시할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>EnableSQMData</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>EnableSQMData 매개 변수가 Lync Server 2013에서 제거 되었습니다. 대신 SQM(Software Quality Management) 데이터에 대한 공유 그룹 정책 설정을 사용하여 Lync 클라이언트 일반 옵션 페이지에 있는 사용자 환경 개선 옵션의 사용자 인터페이스를 확인할 수 있습니다.</p>
<p>HKEY_CURRENT_USER \Software\Policies\Microsoft\Office\Common\QMEnable</p>
<p>값</p>
<p>1 = 확인란을 선택하고 표시합니다(사용자가 확인란을 선택 취소할 수 있음)</p>
<p>0 = 확인란을 선택 취소하고 비활성화합니다(사용자가 이를 무시할 수 없음)</p>
<p>Null = 값이 Office 설치 프로그램에서 결정되며 사용자가 원할 경우 선택할 수 있도록 확인란이 표시됩니다.</p></td>
</tr>
<tr class="even">
<td><p>AllowExchangeContactStore</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>이 매개 변수는 제거되었습니다. 대신 Lync Server 2013을 배포 하 고 토폴로지를 게시 하면 기본적으로 모든 사용자에 대해 통합 연락처 저장소가 사용 되도록 설정 됩니다. 이를 통해 Exchange에 유지되는 사용자의 모든 대화 상대를 Lync, Outlook 및 Outlook Web Access에서 사용할 수 있습니다. Set-CsUserServicesPolicy cmdlet을 통해 통합 연락처 저장소를 사용할 수 있는 사용자를 사용자 지정할 수 있습니다. 전역적으로, 사이트별로, 테넌트별로 또는 개인 및 개인 그룹별로 사용자가 통합 연락처 저장소를 사용할 수 있도록 설정할 수 있습니다. 자세한 내용은 <a href="lync-server-2013-enable-users-for-unified-contact-store.md">Lync Server 2013에서 통합 연락처 저장소에 사용자 사용</a>을 참조 하십시오.</p></td>
</tr>
<tr class="odd">
<td><p>MAPIPollInterval</p></td>
<td><p>Set-csclientpolicy</p></td>
<td><p>이 매개 변수는 Lync 2013에서 사용 되지 않습니다. 이전 릴리즈에서 이 매개 변수는 클라이언트가 Exchange 공용 폴더에서 MAPI 데이터를 검색한 빈도를 지정했습니다.</p></td>
</tr>
<tr class="even">
<td><p>DisableICE</p></td>
<td><p>Set-csclientpolicy</p></td>
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

