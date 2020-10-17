---
title: 구성 설정 확인
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1e1ad498f25656e01507e55c41d98ff4bb9143b4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508415"
---
# <a name="verify-configuration-settings"></a>구성 설정 확인

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-09-28_

토폴로지를 병합 하 고 **import-cslegacyconfiguration** cmdlet을 실행 한 후에는 Office Communications Server 2007 R2 정책 및 설정을 Lync Server 2013로 가져왔는지 확인 합니다. 다음 표에서는 확인해야 하는 정책 및 설정을 나열합니다.

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a>마이그레이션 이후 확인할 정책 및 설정


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>이 작업을 사용하는 경우:</th>
<th>정책 및 설정 확인:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>IM(인스턴트 메시징) 및 회의</p></td>
<td><p>현재 상태 정책</p>
<p>회의 정책</p></td>
</tr>
<tr class="even">
<td><p>전화 접속 회의</p></td>
<td><p>전화 접속 액세스 번호</p>
<p>다이얼 플랜</p></td>
</tr>
<tr class="odd">
<td><p>Enterprise Voice</p></td>
<td><p>음성 정책</p>
<p>음성 경로</p>
<p>다이얼 플랜</p>
<p>PSTN 사용 설정</p></td>
</tr>
<tr class="even">
<td><p>Communicator Web Access</p></td>
<td><p>단순 URL</p></td>
</tr>
<tr class="odd">
<td><p>외부 사용자</p></td>
<td><p>외부 액세스 정책</p></td>
</tr>
<tr class="even">
<td><p>보관</p></td>
<td><p>보관 정책</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a>정책 및 설정을 확인하려면

1.  Office Communications Server 2007 R2 환경에서 다이얼 플랜의 이름 (이전에는 위치 프로필), 전화 접속 액세스 번호 (회의 수행자 액세스 전화 번호 및 지역), 음성 경로, Communicator Web Access에 사용 된 Url을 기록해 둡니다.

2.  Lync Server 2013 프런트 엔드 서버에서 Lync Server 제어판을 엽니다.

3.  가져온 회의 정책을 확인 하려면 왼쪽 창에서 **회의**를 클릭 하 고 **회의 정책을**클릭 한 후에 Office Communications Server 2007 R2 환경의 모든 회의 정책이 목록에 포함 되었는지 확인 합니다.
    
    <div>
    

    > [!NOTE]  
    > 이전 버전의 Office Communications Server의 <STRONG>모임</STRONG> 정책은 이제 Lync Server 2013의 회의 정책 이라고 합니다. 또한 이전 버전의 Office Communications Server에서 <STRONG>익명 Particpants</STRONG> 설정은 이제 Lync Server 2013 회의 정책의 설정입니다.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Office Communications Server 2007 r 2에서 회의 정책이 <STRONG>사용자 당 사용</STRONG>으로 설정 되어 있지 않으면 전역 정책 설정만 가져옵니다. 이 경우에 다른 회의 정책은 가져오지 않습니다.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <STRONG>익명 참가자</STRONG> 가 Office Communications Server 2007 R2 회의 정책에서 <STRONG>사용자별</STRONG> 로 설정 된 경우 마이그레이션 중에 두 회의 정책이 만들어집니다 ( <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> 이 <STRONG>True</STRONG> 로 설정 되 고 1은 <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> 이 <STRONG>False</STRONG>로 설정 됨).

    
    </div>

4.  가져온 다이얼 플랜을 확인하려면 **음성 라우팅**, **다이얼 플랜**을 차례로 클릭한 후 Office Communicator 2007 R2 환경의 모든 다이얼 플랜이 목록에 포함되었는지 확인합니다.
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013에서는 이제 <STRONG>위치 프로필</STRONG> 을 <STRONG>다이얼 플랜</STRONG>이라고 합니다.

    
    </div>

5.  가져온 음성 정책을 확인하려면 **음성 라우팅**, **음성 정책**을 차례로 클릭한 후 Office Communicator 2007 R2 환경의 모든 음성 정책이 목록에 포함되었는지 확인합니다.
    
    <div>
    

    > [!NOTE]  
    > 음성 정책이 Office Communications Server 2007 R2 환경에서 <STRONG>사용자 단위로 사용</STRONG> 하도록 설정 되어 있지 않으면 글로벌 정책 설정만 가져옵니다. 이 경우에 다른 음성 정책은 가져오지 않습니다.

    
    </div>

6.  가져온 음성 경로를 확인하려면 **음성 라우팅**, **경로**를 차례로 클릭한 후 Office Communicator 2007 R2 환경의 모든 음성 경로가 목록에 포함되었는지 확인합니다.

7.  가져온 PSTN 사용 설정을 확인하려면 **음성 라우팅**, **PSTN 사용**을 차례로 클릭한 후 Office Communicator 2007 R2 환경의 PSTN 사용 설정이 목록에 포함되었는지 확인합니다.

8.  가져온 외부 액세스 정책을 확인하려면 **페더레이션 및 외부 액세스**, **외부 액세스 정책**을 차례로 클릭한 후 Office Communicator 2007 R2 환경의 모든 외부 액세스 정책이 목록에 포함되었는지 확인합니다.

9.  보관 정책을 확인 하려면 **모니터링 및 보관**을 클릭 하 고 **보관 정책을**클릭 한 후에 Office Communications Server 2007 R2 환경의 모든 보관 정책이 목록에 포함 되었는지 확인 합니다.

10. Lync Server 관리 셸을 엽니다.

11. 현재 상태 정책을 확인하려면 명령줄에 다음을 입력합니다.
    
        Get-CsPresencePolicy
    
    **Identity** 매개 변수에 있는 이름을 살펴보면 Office Communications Server 2007 R2 환경의 모든 현재 상태 정책을 가져왔는지 확인 합니다.

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a>cmdlet을 사용하여 정책 및 설정을 확인하려면

1.  Lync Server 관리 셸을 엽니다.

2.  다음 표의 cmdlet을 실행하여 정책 및 설정을 확인합니다.
    
    이러한 cmdlet의 구문은 다음 예와 같습니다.
    
        Get-CsConferencingPolicy
    
    이러한 cmdlet에 대한 자세한 내용을 보려면 다음을 실행합니다.
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>이 정책 또는 설정에 대해:</th>
<th>이 cmdlet 사용:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>현재 상태 정책</p></td>
<td><p><strong>Get-cspresencepolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>회의 정책</p></td>
<td><p><strong>Get-csconferencingpolicy</strong></p></td>
</tr>
<tr class="odd">
<td><p>전화 접속 액세스 번호</p></td>
<td><p><strong>Get-csdialinconferencingaccessnumber</strong></p></td>
</tr>
<tr class="even">
<td><p>다이얼 플랜</p></td>
<td><p><strong>Get-CsDialPlan 플랜</strong></p></td>
</tr>
<tr class="odd">
<td><p>음성 정책</p></td>
<td><p><strong>Set-csvoicepolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>음성 경로</p></td>
<td><p><strong>Get-csvoiceroute</strong></p></td>
</tr>
<tr class="odd">
<td><p>PSTN 사용</p></td>
<td><p><strong>G-CsPstnUsage 사용</strong></p></td>
</tr>
<tr class="even">
<td><p>URL</p></td>
<td><p><strong>Get-cssimpleurlconfiguration</strong></p></td>
</tr>
<tr class="odd">
<td><p>외부 액세스 정책</p></td>
<td><p><strong>Get-csexternalaccesspolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>보관 정책</p></td>
<td><p><strong>Grant-csarchivingpolicy</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

