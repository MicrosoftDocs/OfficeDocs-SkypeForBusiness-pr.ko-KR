---
title: 'Lync Server 2013: Config.xml을 사용 하 여 설치 작업 수행'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Config.xml to perform installation tasks
ms:assetid: 0813184a-ab40-417c-b3a3-c2090766b831
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204651(v=OCS.15)
ms:contentKeyID: 48183332
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b6e037f2c69e963e8ca5963a71dabe80f9c75fd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a>Config.xml을 사용 하 여 Lync Server 2013에서 설치 작업 수행

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2012-10-02_

OCT (Office 사용자 지정 도구)는 사용자 지정 설치에 대 한 기본 도구 이지만 관리자는 Config.xml 파일을 사용 하 여 OCT에서 사용할 수 없는 추가 설치 지침을 지정할 수 있습니다. 다음 사용자 지정은 Config.xml 파일만을 사용 하 여 만들 수 있습니다.

  - 네트워크 설치 지점의 경로를 지정 합니다.

  - 설치할 제품을 선택 합니다.

  - 로깅 및 설치 사용자 지정 파일 및 소프트웨어 업데이트의 위치를 구성 합니다.

  - 사용자 이름 등의 설치 옵션을 지정 합니다.

  - Office를 설치 하지 않고 사용자의 컴퓨터에 LIS (로컬 설치 원본)를 복사 합니다.

  - 설치에서 언어를 추가 하거나 제거 합니다.

Lync 2013 자동 설치를 구성 하려면 Config.xml 파일을 사용 하는 것이 좋습니다.

기본적으로 핵심 제품 폴더 (예: \\product)에 저장 된 config.xml 파일입니다. WW) 설치 프로그램이 해당 제품을 설치 하도록 지시 합니다. 예를 들어 다음 폴더의 Config.xml 파일은 Lync 2013를 설치 합니다.

  - \\\\서버\\공유\\Lync15\\(Lync. \\a l a)

Lync 2013 설치에 가장 일반적으로 사용 되는 Config.xml 요소는 다음 표에 나열 되어 있습니다.

### <a name="configxml-elements"></a>Config.xml 요소

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>요소</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>구성</p></td>
<td><p>최상위 수준 요소 (필수). Product 특성을 포함 합니다 (예: Product = Lync).</p></td>
</tr>
<tr class="even">
<td><p>없음 상태</p></td>
<td><p>설치 중에 특정 제품 기능을 처리 하는 방법을 지정 합니다. 다음 특성을 사용 하 여 Outlook 2010에 방해가 되는 공유 구성 요소를 포함 하는 Business Connectivity Services의 설치를 방지 합니다.</p>
<ul>
<li><p>Id =&quot;(발신자 i 주)&quot;</p></li>
<li><p>State =&quot;없음&quot;</p></li>
<li><p>Children =&quot;Force&quot;</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>표시</p></td>
<td><p>설치 프로그램이 사용자에 게 표시 하는 UI 수준입니다. 일반적인 특성에는 다음이 포함 됩니다.</p>
<ul>
<li><p># 고 지&quot;사항&quot; | &quot;=&quot;예 아니요 (기본값)</p></li>
<li><p>AcceptEula =&quot;Yes&quot; | &quot;No&quot;(기본값)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>로깅하</p></td>
<td><p>설정이 수행 하는 로깅 종류에 대 한 옵션입니다. 일반적인 특성에는 다음이 포함 됩니다.</p>
<ul>
<li><p>종류 =&quot;해제&quot; | &quot;표준&quot;(기본값) | &quot;자세한 정보&quot;</p></li>
<li><p>Template = "파일명" (로그 파일 이름)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>설정</p></td>
<td><p>Windows Installer 속성에 대 한 값을 지정 합니다. 일반적인 특성에는 다음이 포함 됩니다.</p>
<ul>
<li><p>설정 Id =&quot;이름&quot; (Windows Installer 속성의 이름)</p></li>
<li><p>Value =&quot;value&quot; (속성에 할당할 값)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>DistributionPoint</p></td>
<td><p>설치를 실행할 네트워크 설치 지점의 정규화 된 경로입니다. Location 특성을 포함 합니다.</p>
<ul>
<li><p>위치 = "path"</p></li>
</ul></td>
</tr>
</tbody>
</table>


다음 예제에서는 Lync 2013의 일반적인 자동 설치에 해당 하는 Config.xml 파일을 보여 줍니다.

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

Config.xml 파일을 사용 하 여 Office 설치 및 유지 관리 작업을 수행 하는 방법에 대 <http://go.microsoft.com/fwlink/p/?linkid=267514>한 자세한 내용은에서 확인할 수 있습니다.

<div>

## <a name="to-customize-the-configxml-file"></a>Config.xml 파일을 사용자 지정 하려면

1.  메모장과 같은 텍스트 편집기 도구를 사용 하 여 Config.xml 파일을 엽니다.

2.  변경 하려는 요소가 포함 된 선을 찾습니다.

3.  사용할 자동 옵션으로 요소 항목을 수정 합니다. 주석 구분 기호 "\<\!--" 및 "--\>"를 제거 해야 합니다. 예를 들어 다음 구문을 사용 합니다.
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  Config.xml 파일을 저장 합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

