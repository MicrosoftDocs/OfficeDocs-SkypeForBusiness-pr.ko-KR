---
title: 'Lync Server 2013: 장치 업데이트 로그 파일에 대 한 설정 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify settings for Device Update log files
ms:assetid: 9b57f126-1853-43b3-bbd4-06401e6498bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182554(v=OCS.15)
ms:contentKeyID: 48184975
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2118cac5e8380d27e8f273f5cb469efdbddfd9bd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534335"
---
# <a name="modify-settings-for-device-update-log-files-in-lync-server-2013"></a>Lync Server 2013에서 장치 업데이트 로그 파일에 대 한 설정 수정

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

Lync Server 제어판 또는 Lync Server 관리 셸을 사용 하 여 조직에 장치 업데이트 정보가 기록 되는 방식에 대 한 설정을 변경할 수 있습니다. 다음 표에서는 수정할 수 있는 설정과 설정을 수정 하는 데 사용 하는 도구를 보여 줍니다.

로그 설정은 전체적으로 변경 하거나 사이트별로 적용할 수 있습니다.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>변경 하려면</th>
<th>사용</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>로그 파일의 최대 크기 (바이트)입니다.</p></td>
<td><p>Lync Server 제어판</p>
<p>또는</p>
<p>Communications Server 관리 셸</p></td>
</tr>
<tr class="even">
<td><p>캐시에 보유할 수 있는 정보의 최대 양 (바이트)입니다.</p></td>
<td><p>Lync Server 제어판</p>
<p>또는</p>
<p>Communications Server 관리 셸</p></td>
</tr>
<tr class="odd">
<td><p>로그 파일에 캐시 된 정보를 기록 하는 빈도 (분)</p></td>
<td><p>Lync Server 제어판</p>
<p>또는</p>
<p>Communications Server 관리 셸</p></td>
</tr>
<tr class="even">
<td><p>로그 파일 보존 기간 (일)</p></td>
<td><p>Lync Server 제어판</p>
<p>또는</p>
<p>Communications Server 관리 셸</p></td>
</tr>
<tr class="odd">
<td><p>삭제 해야 하는 만료 된 파일을 확인 하는 시간 (일)</p></td>
<td><p>Communications Server 관리 셸</p></td>
</tr>
<tr class="even">
<td><p>허용할 로그 파일 확장명</p></td>
<td><p>Communications Server 관리 셸</p></td>
</tr>
<tr class="odd">
<td><p>보유할 로그 파일 형식</p></td>
<td><p>Communications Server 관리 셸</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="to-change-logging-settings-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 로깅 설정을 변경 하려면

1.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

2.  왼쪽 탐색 표시줄에서 **클라이언트**, **장치 로그 구성**을 차례로 클릭합니다.

3.  **장치 로그 구성** 페이지에서 변경할 구성을 두 번 클릭합니다.

4.  **로그 설정 편집** 대화 상자에서 다음 설정을 변경 합니다.
    
      - **최대 파일 크기 (바이트)**     로그 파일이 제거 될 때까지 사용할 수 있는 최대 크기를 지정 합니다. 기본값은 1024000 바이트 (1mb)입니다.
    
      - **최대 캐시 크기 (바이트)**     캐시를 삭제 하 고 로그 파일에 데이터를 기록 하기 전에 로그 파일 캐시에 보유할 수 있는 최대 정보 양 (바이트)을 지정 합니다. 기본값은 512000 바이트 (0.5 MB)입니다.
    
      - **캐시 플러시 시간 (분) (1-60)**     로그 파일 캐시에 저장 된 정보가 실제 로그 파일에 기록 되는 빈도를 나타냅니다. 데이터가 기록 된 후 캐시는 지워집니다. 기본값은 5 분입니다.
    
      - **로그 파일을 보관할 일 수 (1-365)**     로그 파일을 삭제 하기 전에 보관할 기간 (일)을 지정 합니다. 기본값은 10 일입니다.

5.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="changing-logging-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 로깅 설정 변경

장치 업데이트 로그 파일 설정은 Windows PowerShell 및 **new-csdeviceupdateconfiguration** cmdlet을 사용 하 여 수정할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다.

<div>


> [!NOTE]  
> 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 <A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A> 하세요.



</div>

다음 예제에서는 **new-csdeviceupdateconfiguration** 를 사용 하 여 설정을 수정할 수 있는 몇 가지 방법을 보여 줍니다.

<div>

## <a name="to-modify-the-maximum-log-file-size-and-the-log-cleanup-interval"></a>최대 로그 파일 크기 및 로그 정리 간격을 수정 하려면

  - 다음 명령은 Redmond 사이트에 적용 된 장치 업데이트 로그 설정을 수정 합니다. 이 예에서 최대 로그 파일 크기는 204800 바이트로 설정 되 고 로그 정리 간격은 14 일로 설정 됩니다.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -MaxLogFileSize 204800 -LogCleanUpInterval 14.00:00:00

</div>

<div>

## <a name="to-modify-the-log-cleanup-time-of-day"></a>로그 정리 시간을 수정 하려면

  - 이 명령은 Redmond 사이트에 대 한 로그 정리 시간을 오전 3:00로 설정 합니다.
    
        Set-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupTimeOfDay 03:00

</div>

자세한 내용은 [new-csdeviceupdateconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsDeviceUpdateConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

