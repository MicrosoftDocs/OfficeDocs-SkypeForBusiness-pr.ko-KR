---
title: Lync Server 2013에서 비즈니스용 Skype 클라이언트 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure the client experience
ms:assetid: 61e783f1-24f4-430b-ae52-c76a4d206dc7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn954919(v=OCS.15)
ms:contentKeyID: 65227958
ms.date: 09/18/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5bd70d0f37dbed8a38994af6dc806556380484b5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-the-client-experience-with-skype-for-business"></a>비즈니스용 Skype를 사용 하 여 클라이언트 환경 구성

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2015-09-17_

**요약:** 이 항목에서는 Lync Server 2013 환경에서 비즈니스용 Skype 클라이언트 사용자에 대 한 클라이언트 환경을 구성 하는 방법에 대해 설명 합니다. 2013 년 12 2014 월 누적 업데이트 (5.0.8308.857) 이상이 설치 된 Lync Server를 실행 하는 경우에만 클라이언트 환경을 구성할 수 있습니다. Lync Server 2013 업데이트에 대 한 자세한 내용은 [Lync server 2013에 대 한 업데이트](http://go.microsoft.com/fwlink/p/?linkid=532651)를 참조 하세요.

비즈니스용 skype는 Skype 소비자 제품 환경을 기반으로 하는 새로운 사용자 환경을 제공 합니다. Lync의 모든 기능 외에도 비즈니스용 Skype는 간소화 된 컨트롤 및 익숙한 아이콘과 함께 새로운 기능을 제공 합니다. 새 클라이언트 환경에 대 한 자세한 내용은 [now for The Lync To 비즈니스용 Skype--what 's new를 참조](http://go.microsoft.com/fwlink/?linkid=529022)하세요.

Lync Server 2013는 Lync 클라이언트 환경 뿐만 아니라 새로운 비즈니스용 Skype 클라이언트 환경을 지원 합니다. 관리자는 사용자를 위한 기본 클라이언트 환경을 선택할 수 있습니다. 예를 들어 조직의 사용자가 새로운 비즈니스용 Skype 환경에서 완벽 하 게 교육을 받을 때까지 Lync 클라이언트 환경을 배포할 수 있습니다. 또는 모든 사용자를 비즈니스용 Skype 서버 2015로 아직 업그레이드 하지 않은 경우 모든 사용자가 새 서버로 업그레이드 될 때까지 동일한 클라이언트 환경을 사용할 수 있습니다.

<div>


> [!IMPORTANT]  
> 조직에 비즈니스용 Skype 서버 2015과 Lync Server 2013이 배포 되어 있는 경우 서버 버전 및 UI 설정에 따라 기본 클라이언트 환경이 달라 집니다. 사용자가 비즈니스용 Skype를 처음 시작 하면 Lync 사용자 인터페이스를 선택한 경우에도 항상 비즈니스용 Skype 사용자 인터페이스가 표시 됩니다. 몇 분 후에 사용자에 게 Lync 모드로 전환 하 라는 메시지가 표시 됩니다. 자세한 내용은이 항목 뒷부분의 <STRONG>첫 번째 시작 클라이언트 동작</STRONG> 을 참조 하십시오.



</div>

<div>


> [!NOTE]  
> Lync 2013 클라이언트 환경은 비즈니스용 Skype 2016 클라이언트 버전에 대 한 옵션이 아닙니다. 클라이언트 환경에서 Lync 2013 클라이언트를 사용 하도록 구성 하기 전에 클라이언트 버전에서 번호 16으로 시작 하지 않는지 확인 하십시오. 예: x.x.x.



</div>

<div>

## <a name="configure-the-client-experience"></a>클라이언트 환경 구성

EnableSkypeUI 매개 변수와 함께 **CSClientPolicy** cmdlet을 사용 하 여 조직의 사용자가 보게 될 클라이언트 환경을 지정할 수 있습니다. 다음 명령은 전역 정책의 영향을 받는 조직의 모든 사용자에 대해 비즈니스용 Skype 클라이언트 환경을 선택 합니다 (사이트 또는 사용자 관련 정책이 전역 정책을 재정의 함).

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $true

다음 명령은 글로벌 정책에 의해 영향을 받는 조직의 모든 사용자에 대해 Lync 클라이언트 환경을 선택 합니다.

    Set-CsClientPolicy -Identity Global -EnableSkypeUI $false

다음 명령은 Redmond 사이트 내의 모든 사용자에 대해 비즈니스용 Skype 클라이언트 환경을 선택 합니다.

    Set-CsClientPolicy -Identity site:Redmond -EnableSkypeUI $true

조직 내의 특정 사용자에 대 한 클라이언트 환경을 구성 하려는 경우에는 **새로운 CsClientPolicy** cmdlet을 사용 하 여 새 사용자 정책을 만든 다음 **부여-csclientpolicy** cmdlet을 사용 하 여 특정 사용자에 게 정책을 할당할 수 있습니다.

예를 들어 다음 명령은 비즈니스용 Skype 클라이언트 환경을 선택 하는 새 클라이언트 정책 (SalesClientUI)을 만듭니다.

    New-CsClientPolicy -Identity SalesClientUI -EnableSkypeUI $true

다음 명령은 Sales 부서의 모든 구성원에 게 정책 SalesClientUI를 할당 합니다.

    Get-CsUser -LDAPFilter "Department=Sales" | Grant-CsClientPolicy -PolicyName SalesClientUI

</div>

<div>

## <a name="first-launch-client-behaviors"></a>첫 번째 클라이언트 동작 시작

기본적으로 사용자가 비즈니스용 Skype를 처음 시작 하면 EnableSkypeUI 매개 변수 값을 이전에 설명한 $False으로 설정 하 여 Lync 클라이언트 환경을 선택한 경우에도 항상 비즈니스용 Skype 사용자 인터페이스가 표시 됩니다. . 몇 분 후에 사용자에 게 Lync 모드로 전환 하 라는 메시지가 표시 됩니다.

사용자가 처음으로 비즈니스용 Skype 클라이언트를 시작할 때 Lync 사용자 인터페이스를 표시 하려면 클라이언트를 업데이트 한 후 처음 시작 하기 전에 다음 단계를 수행 합니다.

1.  앞에서 설명한 대로 사용 `EnableSkypeUI` 중인 정책에서 값이 $False으로 설정 되어 있는지 확인 합니다.

2.  사용자 컴퓨터에서 시스템 레지스트리를 업데이트 합니다. 처음 사용자가 비즈니스용 Skype 클라이언트를 시작 하기 전에이 작업을 수행 해야 하며, 한 번만 수행 하면 됩니다. 도메인에 가입 된 컴퓨터에서 레지스트리를 업데이트 하는 그룹 정책 개체를 만드는 방법에 대 한 자세한 내용은이 항목의 뒷부분에 나오는 섹션을 참조 하십시오.
    
    **\_\\\] HKEY 현재\_사용자\\소프트웨어\\Microsoft\\Office Lync 키에서 새 이진 값을 만듭니다. \[** ****
    
    **값 이름은** **EnableSkypeUI**이어야 하며 **값 데이터** 를 **00 00 00 00**로 설정 해야 합니다.
    
    키의 모양은 다음과 같습니다.
    
        [HKEY_CURRENT_USER\Software\Microsoft\Office\Lync]
        "CanSharePptInCollab"=dword:00000001
        "CanShareOneNoteInCollab"=dword:00000001
        "CanAppShareInCollab"=dword:00000001
        "EnableSkypeUI"=hex:00,00,00,00

이제 사용자가 처음으로 비즈니스용 Skype 클라이언트를 시작할 때 Lync 사용자 인터페이스가 표시 됩니다.

<div>

## <a name="control-the-display-of-the-welcome-screen-tutorial"></a>시작 화면 자습서의 표시 제어

사용자가 비즈니스용 Skype 클라이언트를 열 때 기본 동작은 *대부분의 사용자가 요청 하는 7 가지 빠른 팁*을 포함 하는 시작 화면을 표시 하는 것입니다. 시작 화면이 표시 되지 않도록 설정할 수 있지만 사용자는 클라이언트 컴퓨터에 다음 레지스트리 값을 추가 하 여 자습서에 액세스 하도록 허용 합니다.

**\_\\HKEY 현재 사용자\\소프트웨어\\Microsoft\\Office\\\] 15.0 Lync 키에서 새 dword(32 (32 비트) 값을 만듭니다.\_ \[** **** **값 이름은** **IsBasicTutorialSeenByUser**이어야 하며 **값 데이터** 를 **1**로 설정 해야 합니다.

키의 모양은 다음과 같습니다.

    "IsBasicTutorialSeenByUser"=dword:00000001

</div>

<div>

## <a name="turn-off-the-client-tutorial"></a>클라이언트 자습서 해제

사용자가 자습서에 액세스 하지 못하게 하려면 다음 레지스트리 값을 사용 하 여 클라이언트 자습서를 해제할 수 있습니다.

**\_\\HKEY 현재 사용자\\소프트웨어\\Microsoft\\Office\\\] 15.0 Lync 키에서 새 dword(32 (32 비트) 값을 만듭니다.\_ \[** **** **값 이름은** **TutorialFeatureEnabled**이어야 하며 **값 데이터** 를 **0**으로 설정 해야 합니다.

    "TutorialFeatureEnabled"=dword:00000000

**값 데이터** 를 **1**로 설정 하 여 자습서를 다시 설정할 수 있습니다.

</div>

</div>

<div>

## <a name="default-client-experiences"></a>기본 클라이언트 환경

조직에 비즈니스용 Skype 서버 2015 및 Lync Server가 배포 되어 있는 경우 서버 버전과 Skype UI 설정에 따라 클라이언트 환경이 달라 집니다. 다음 표에는 서버 버전 및 UI 설정을 기반으로 하는 초기 클라이언트 환경이 나와 있습니다.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>서버 버전</p></th>
<th><p>EnableSkypeUI 설정</p></th>
<th><p>클라이언트 환경</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>비즈니스용 Skype 서버 2015</p></td>
<td><p>기본</p></td>
<td><p>비즈니스용 Skype</p></td>
</tr>
<tr class="even">
<td><p>비즈니스용 Skype 서버 2015</p></td>
<td><p>참</p></td>
<td><p>비즈니스용 Skype</p></td>
</tr>
<tr class="odd">
<td><p>비즈니스용 Skype 서버 2015</p></td>
<td><p>False</p></td>
<td><p>사용자가 Lync 모드로 전환 요청 (사용자가 UI 설정을 $true로 변경한 경우 나중에 비즈니스용 Skype로 전환할 수 있음)</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 또는 Lync Server 2013 (올바른 패치 포함)</p></td>
<td><p>기본</p></td>
<td><p>사용자가 Lync 모드로 전환 요청 (사용자가 UI 설정을 $true로 변경한 경우 나중에 비즈니스용 Skype로 전환할 수 있음)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 또는 Lync Server 2013 (올바른 패치 포함)</p></td>
<td><p>참</p></td>
<td><p>비즈니스용 Skype</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 또는 Lync Server 2013 (올바른 패치 포함)</p></td>
<td><p>False</p></td>
<td><p>사용자가 Lync 모드로 전환 요청 (사용자가 UI 설정을 $true로 변경한 경우 나중에 비즈니스용 Skype로 전환할 수 있음)</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 또는 Lync Server 2013 (패치 없음)</p></td>
<td><p>기본</p></td>
<td><p>사용자가 Lync 클라이언트 환경으로 전환 하기를 요청 했습니다 (나중에 비즈니스용 Skype로 전환할 수 없음).</p></td>
</tr>
</tbody>
</table>


다음 표에는 관리자가 Skype UI 환경의 초기 설정을 변경할 때의 클라이언트 환경이 나와 있습니다.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>서버 버전</p></th>
<th><p>Skype UI 설정</p></th>
<th><p>클라이언트 UI = Lync</p></th>
<th><p>클라이언트 UI = 비즈니스용 Skype</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>비즈니스용 Skype 서버 2015</p></td>
<td><p>참</p></td>
<td><p>비즈니스용 Skype로 전환 하 라는 사용자에 게 요청</p></td>
<td><p>비즈니스용 Skype</p></td>
</tr>
<tr class="even">
<td><p>비즈니스용 Skype 서버 2015</p></td>
<td><p>False</p></td>
<td><p>Lync UI</p></td>
<td><p>Lync UI로 전환 하 라는 사용자에 게 요청</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 또는 Lync Server 2013 (올바른 패치 포함)</p></td>
<td><p>참</p></td>
<td><p>비즈니스용 Skype로 전환 하 라는 사용자에 게 요청</p></td>
<td><p>비즈니스용 Skype</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010 또는 Lync Server 2013 (올바른 패치 포함)</p></td>
<td><p>False</p></td>
<td><p>Lync UI</p></td>
<td><p>Lync UI로 전환 하 라는 사용자에 게 요청</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010 또는 Lync Server 2013 (패치 없음)</p></td>
<td><p>기본</p></td>
<td><p>Lync 모드 (비즈니스용 Skype로 전환할 수 없음)</p></td>
<td><p>Lync UI (비즈니스용 Skype로 전환할 수 없음)</p></td>
</tr>
</tbody>
</table>


비즈니스용 Skype 클라이언트의 구성을 관리 하는 데 필요한 패치 버전은 다음과 같습니다.

  - Lync Server 2010-Lync Server 2010의 경우 2015 4.0.7577.710 (누적 업데이트) 자세한 내용은 [Lync Server 2010에 대 한 업데이트](http://go.microsoft.com/fwlink/p/?linkid=532771) 를 참조 하세요.

  - Lync Server 2013-Lync Server 2013의 경우 12 월 2014 5.0.8308.857 (누적 업데이트) 자세한 내용은 [Lync Server 2013에 대 한 업데이트](http://go.microsoft.com/fwlink/p/?linkid=532772)를 참조 하세요.

</div>

<div>

## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>도메인에 가입 된 컴퓨터에서 레지스트리를 수정 하는 그룹 정책 개체 만들기

사용자가 처음으로 비즈니스용 Skype 클라이언트를 시작할 때 Lync 클라이언트 환경을 표시 하기 위한 레지스트리 업데이트는 한 번만 수행 하면 됩니다. GPO (그룹 정책 개체)를 사용 하 여 레지스트리를 업데이트 하는 경우 값 데이터를 업데이트 하는 대신 새 값을 만들려면 개체를 정의 해야 합니다. GPO가 적용 되 면 새 값이 없는 경우 GPO가이를 만들고 값 데이터를 0으로 설정 합니다.

다음 절차에서는 사용자가 비즈니스용 Skype를 처음 시작할 때 Lync 클라이언트 환경이 표시 되도록 레지스트리를 수정 하는 방법을 설명 합니다. 또한이 절차를 사용 하 여 앞에서 설명한 것 처럼 시작 화면 자습서를 사용 하지 않도록 레지스트리를 업데이트할 수 있습니다.

**GPO를 만들려면**

1.  **그룹 정책 관리 콘솔**을 시작 합니다.
    
    그룹 정책 관리 콘솔을 사용 하는 방법에 대 한 자세한 내용은 [그룹 정책 관리 콘솔](http://go.microsoft.com/fwlink/?linkid=532759)을 참조 하십시오.

2.  **그룹 정책 개체** 노드를 마우스 오른쪽 단추로 클릭 하 고 메뉴에서 **새로 만들기** 를 선택 합니다.

3.  **새 gpo** 대화 상자에서 GPO의 이름 (예: **MakeLyncDefaultUI**)을 입력 하 고 **확인**을 클릭 합니다.

4.  방금 만든 새 GPO를 마우스 오른쪽 단추로 클릭 한 다음 메뉴에서 **편집** 을 선택 합니다.

5.  **그룹 정책 관리 편집기**에서 **사용자 구성**, **기본 설정**, **Windows 설정을**차례로 확장 한 다음 **레지스트리** 노드를 선택 합니다.

6.  **레지스트리** 노드를 마우스 오른쪽 단추로 클릭 한 다음 **새** \> **레지스트리 항목**을 선택 합니다.

7.  **새 레지스트리 속성** 대화 상자에서 다음을 업데이트 합니다.
    
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th>필드</th>
    <th>선택 하거나 입력할 값</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>작업</strong></p></td>
    <td><p><strong>만들기</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>벌</strong></p></td>
    <td><p>HKEY_CURRENT_USER</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>키 경로</strong></p></td>
    <td><p>Software\Microsoft\Office\Lync</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Value name</strong></p></td>
    <td><p>EnableSkypeUI</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>값 형식</strong></p></td>
    <td><p>REG_BINARY</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Value data</strong></p></td>
    <td><p>00000000</p></td>
    </tr>
    </tbody>
    </table>


8.  **확인** 을 클릭 하 여 변경 내용을 저장 하 고 GPO를 닫습니다.

다음으로, 만든 GPO를 정책을 할당 하려는 사용자 그룹 (예: OU)에 연결 해야 합니다.

**GPO를 사용 하 여 정책을 할당 하려면**

1.  그룹 정책 관리 콘솔에서 정책을 할당 하려는 OU를 마우스 오른쪽 단추로 클릭 한 다음 **기존 GPO에 연결**을 선택 합니다.

2.  **Gpo 선택** 대화 상자에서 만든 gpo를 선택 하 고 **확인**을 선택 합니다.

3.  대상 사용자의 컴퓨터에서 명령 프롬프트를 열고 다음 명령을 입력 합니다.
    
    **gpupdate/target: 사용자**
    
    "정책 업데이트 중 ..." 메시지 GPO가 적용 되는 동안 표시 됩니다. 완료 되 면 "사용자 정책 업데이트가 완료 되었습니다." 라는 메시지가 표시 됩니다.

4.  명령 프롬프트에 다음 명령을 입력합니다.
    
    **gpresult/r**
    
    아래에 표시 된 GPO 이름을 사용 하 여 "할당 된 그룹 정책 개체"를 확인 해야 합니다.

또한 레지스트리를 검사 하 여 GPO가 사용자 컴퓨터의 레지스트리를 성공적으로 업데이트 했는지 확인할 수 있습니다. 레지스트리 편집기를 열고 ** \[\_HKEY 현재\_사용자\\Software\\Microsoft\\Office\\Lync\] ** 키로 이동 합니다. GPO가 레지스트리를 성공적으로 업데이트 한 경우 값이 0 인 EnableSkypeUI 라는 값이 표시 됩니다.

</div>

</div>

<span> </span>

</div>

</div>

</div>

