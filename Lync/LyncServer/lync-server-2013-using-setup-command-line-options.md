---
title: 'Lync Server 2013: 설치 명령줄 옵션 사용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Setup command-line options
ms:assetid: 99878c3c-ff31-48e2-8424-580d7b07a7bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205129(v=OCS.15)
ms:contentKeyID: 48184957
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c530387fa9f504120ff3a8f38128eeb07b04e615
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527645"
---
# <a name="using-setup-command-line-options-in-lync-server-2013"></a>Lync Server 2013에서 설치 명령줄 옵션 사용

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-03_

Setup.exe 명령줄이 사용되는 Office 설치 작업은 매우 한정적입니다. 제품 설치와 기능 사용자 지정에 설치 명령줄 옵션 대신 Office 사용자 지정 도구와 Config.xml 파일을 사용하는 것이 일반적입니다.

다음 표에는 Office Setup.exe 명령줄에서 인식하는 명령줄 옵션이 나와 있습니다.

### <a name="office-setup-command-line-options"></a>Office 설치 명령줄 옵션

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>설치 명령줄 옵션</th>
<th>설명</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>/admin</p></td>
<td><p>Office 사용자 지정 도구를 실행하여 설치 사용자 지정 파일(.msp 파일)을 만듭니다.</p></td>
</tr>
<tr class="even">
<td><p>/adminfile [path]</p></td>
<td><p>지정된 설치 사용자 지정 파일을 설치에 적용합니다. 특정 사용자 지정 파일(.msp 파일)의 경로 또는 사용자 지정 파일이 저장된 폴더의 경로를 지정할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>/config [path]</p></td>
<td><p>설치하는 동안 설치 프로그램에서 사용할 Config.xml 파일을 지정합니다. /Config 옵션을 사용 하 여 다음과 같이 Lync 2013 설치에 대해 사용자 지정 된 Config.xml 파일을 지정 합니다. <code>/config \\server\share\Lync15\Lync.WW\Config.xml</code></p></td>
</tr>
<tr class="even">
<td><p>/modify Lync</p></td>
<td><p>수정된 Config.xml 파일과 함께 유지 관리 모드로 설치 프로그램을 실행합니다. 예를 들어 /modify 옵션을 사용하여 Lync 기능을 추가하거나 제거할 수 있습니다.</p></td>
</tr>
<tr class="odd">
<td><p>/repair Lync</p></td>
<td><p>사용자 컴퓨터에서 설치 프로그램을 실행하여 Lync를 복구합니다.</p></td>
</tr>
<tr class="even">
<td><p>/uninstall Lync</p></td>
<td><p>설치 프로그램을 실행하여 사용자 컴퓨터에서 Lync를 제거합니다.</p></td>
</tr>
</tbody>
</table>


설치 명령줄 옵션을 사용 하는 방법에 대 한 자세한 내용은를 참조 하세요 <https://go.microsoft.com/fwlink/p/?linkid=267515> .

</div>

<span> </span>

</div>

</div>

</div>

