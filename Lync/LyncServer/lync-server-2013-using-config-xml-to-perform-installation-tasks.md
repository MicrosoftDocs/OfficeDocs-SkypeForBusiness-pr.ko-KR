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
ms.openlocfilehash: e2933da3fc52cc6a5c23f74806ff3a4e81dcb2ba
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42212834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="using-configxml-to-perform-installation-tasks-in-lync-server-2013"></a>Config.xml을 사용 하 여 Lync Server 2013에서 설치 작업 수행

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-02_

사용자 지정 설치에는 기본적으로 OCT(Office 사용자 지정 도구)가 사용되기는 하지만, 관리자는 Config.xml 파일을 사용하여 OCT에서 사용할 수 없는 추가 설치 지침을 지정할 수 있습니다. Config.xml 파일을 통해서만 수행할 수 있는 사용자 지정 작업은 다음과 같습니다.

  - 네트워크 설치 지점 경로 지정

  - 설치할 제품 선택

  - 설치 사용자 지정 파일 및 소프트웨어 업데이트의 위치와 로깅 구성

  - 사용자 이름 등의 설치 옵션 지정

  - Office를 설치하지 않고 사용자 컴퓨터에 LIS(로컬 설치 원본) 복사

  - 설치에서 언어 추가 또는 제거

Config.xml 파일을 사용 하 여 Lync 2013 자동 설치를 구성 하는 것이 좋습니다.

기본적으로 핵심 제품 폴더에 저장 된 Config.xml 파일 (예: \\product) WW) 설치 프로그램에 해당 제품을 설치 하도록 지시 합니다. 예를 들어 다음 폴더의 Config.xml 파일은 Lync 2013을 설치 합니다.

  - \\\\서버\\공유\\lync15.admx가\\ \\

Lync 2013 설치에 가장 일반적으로 사용 되는 Config.xml 요소는 다음 표에 나와 있습니다.

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
<td><p>최상위 요소(필수)입니다. Product=Lync 등의 Product 특성을 포함합니다.</p></td>
</tr>
<tr class="even">
<td><p>OptionState</p></td>
<td><p>특정 제품 기능이 설치 중에 처리되는 방법을 지정합니다. 다음 특성을 사용 하 여 Outlook 2010을 방해 하는 공유 구성 요소를 포함 하는 Business Connectivity Services의 설치를 차단 합니다.</p>
<ul>
<li><p>Id =&quot;주 번호&quot;</p></li>
<li><p>State =&quot;없음&quot;</p></li>
<li><p>Children =&quot;Force&quot;</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>디스플레이</p></td>
<td><p>설치 프로그램에서 사용자에게 표시하는 UI의 수준입니다. 일반적인 특성은 다음과 같습니다.</p>
<ul>
<li><p>고 지 사항&quot;=&quot; | &quot;예&quot;아니요 (기본값)</p></li>
<li><p>AcceptEula =&quot;Yes&quot; | &quot;No&quot;(기본값)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>기록을</p></td>
<td><p>설치 프로그램이 수행하는 로깅 종류에 대한 옵션입니다. 일반적인 특성은 다음과 같습니다.</p>
<ul>
<li><p>Type =&quot;Off&quot; | &quot;Standard&quot;(기본값) | &quot;자세한 정보 표시&quot;</p></li>
<li><p>Template=”파일 이름.txt”(로그 파일의 이름)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>설정</p></td>
<td><p>Windows Installer 속성의 값을 지정합니다. 일반적인 특성은 다음과 같습니다.</p>
<ul>
<li><p>설정 Id =&quot;이름&quot; (Windows Installer 속성의 이름)</p></li>
<li><p>Value =&quot;value&quot; (속성에 할당할 값)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>DistributionPoint</p></td>
<td><p>설치를 실행할 네트워크 설치 지점의 정규화된 경로입니다. Location 특성을 포함합니다.</p>
<ul>
<li><p>Location = "path"</p></li>
</ul></td>
</tr>
</tbody>
</table>


다음 예제에서는 Lync 2013의 일반적인 자동 설치를 위한 Config.xml 파일을 보여 줍니다.

    <Configuration Product="Lync">
      <OptionState Id="LOBiMain" State="Absent" Children="Force" />
      <Display Level="None" CompletionNotice="No" AcceptEula="Yes" />
      <Logging Type="verbose" Path="%temp%" Template="LyncSetupVerbose(*).log" />
      <Setting Id="SETUP_REBOOT" Value="Never" />
      <DistributionPoint Location="\\server\share\Lync15" />
    </Configuration>

Config.xml 파일을 사용 하 여 Office 설치 및 유지 관리 작업을 수행 하는 방법에 대 <https://go.microsoft.com/fwlink/p/?linkid=267514>한 자세한 내용은를 제공 합니다.

<div>

## <a name="to-customize-the-configxml-file"></a>Config.xml 파일을 사용자 지정하려면

1.  메모장과 같은 텍스트 편집기 도구를 사용하여 Config.xml 파일을 엽니다.

2.  변경할 요소가 포함된 줄을 찾습니다.

3.  요소 항목을 사용하려는 자동 옵션으로 수정합니다. 주석 구분 기호 "\<\!--" 및 "--\>"를 제거 해야 합니다. 예를 들어 다음과 같은 구문을 사용할 수 있습니다.
    
        < DistributionPoint Location="\\server\share\Lync15" />

4.  Config.xml 파일을 저장합니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

