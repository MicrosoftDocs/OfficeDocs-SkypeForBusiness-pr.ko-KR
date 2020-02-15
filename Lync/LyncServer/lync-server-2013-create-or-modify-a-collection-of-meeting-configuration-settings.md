---
title: 모임 구성 설정 모음 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of meeting configuration settings
ms:assetid: ce6773c1-a0d5-4405-8e32-33a6f3a46a1a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721889(v=OCS.15)
ms:contentKeyID: 49733822
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1bfa41eebf8231a1118ca16c83ca8f27ecb4244
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 모임 구성 설정 모음 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

모임 구성 페이지의 설정을 사용 하 여 모임 참가 환경의 다양 한 특성을 정의할 수 있습니다. 기본적으로 전역 설정에서 참가 환경이 정의됩니다. 사이트 수준 및 풀 수준의 모임 참가 설정을 만들 수도 있습니다. 풀 수준 설정을 만들면 설정이 해당 풀에서 호스팅된 모든 모임에 적용됩니다. 풀 수준 설정을 만들지 않으면 사이트 수준 설정이 적용됩니다(있는 경우). 사이트 수준 설정을 정의하지 않으면 전역 설정이 모든 모임에 적용됩니다.

<div>

## <a name="to-create-new-meeting-join-settings"></a>새 모임 참가 설정을 만들려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 표시줄에서 **회의**, **모임 구성**을 차례로 클릭합니다.

4.  **모임 구성** 페이지에서 **새로 만들기**를 클릭하고 다음 중 하나를 수행합니다.
    
      - 사이트 수준 정책을 만들려면 **사이트 구성**을 클릭합니다. **사이트 선택** 검색 필드에 모임 참가 설정을 정의할 사이트의 이름 일부나 전체를 입력합니다. 사이트 결과 목록에서 원하는 사이트를 클릭한 다음 **확인**을 클릭합니다.
    
      - 풀 수준 정책을 만들려면 **풀 구성**을 클릭합니다. **서비스 선택** 검색 필드에 모임 참가 설정을 정의할 풀 서비스의 이름 일부나 전체를 입력합니다. 서비스 결과 목록에서 원하는 풀을 클릭하고 **확인**을 클릭합니다.

5.  PSTN(공중 전화망)에서 전화 접속한 참가자를 대기실을 거쳐 라우팅하려면 **PSTN 발신자 바이패스 대기실** 확인란의 선택을 취소합니다. 기본적으로 PSTN에서 전화 접속한 참가자는 모임으로 바로 이동됩니다.

6.  모임에서 발표자가 될 수 있는 사용자를 구성하려면 **발표자로 지정**에서 다음 중 하나를 수행합니다.
    
      - 이끌이 이외의 다른 사용자를 발표자로 지정하지 않으려면 **없음**을 클릭합니다.
    
      - 조직의 구성원인 참가자만 발표자로 지정하려면 **회사**를 클릭합니다. 이것이 기본 설정입니다.
    
      - 모든 참가자를 발표자로 지정하려면 **모든 참가자**를 클릭합니다.

7.  모임 예약 시 이끌이가 회의 유형을 선택하도록 하려면 **기본적으로 지정되는 전화 회의 유형** 확인란의 선택을 취소합니다. 회의 유형은 기본적으로 자동으로 지정됩니다.

8.  인증되지 않은 익명의 사용자를 자동으로 허용되지 않도록 하려면 **기본적으로 익명 사용자 허용** 확인란의 선택을 취소합니다. 기본적으로 익명 사용자는 모임에 자동으로 허용됩니다.

9.  참가자에 게 전송 된 모임 초대를 사용자 지정 하려면 다음을 수행 합니다. Url 및 사용자 지정 바닥글 텍스트의 최대 길이는 1KB입니다. **도움말 URL**을 제외 하 고 사용자 지정 항목에 대 한 값을 지정 하지 않으면 모임에 포함 되지 않습니다. 사용자 지정 도움말 URL을 포함 하지 않으면 Lync에 대 한 기본 도움말 URL이 초대에 표시 됩니다.
    
      - 모임 초대에 표시 되는 로고를 사용자 지정 하려면 **로고 URL**에서 로고의 위치를 입력 합니다.
        
        <div>
        

        > [!NOTE]
        > 로고는 크기가 188 x 30 픽셀인 GIF 또는 JPG 이미지 여야 합니다.

        
        </div>
    
      - 모임 초대에 나타나는 도움말 텍스트를 사용자 지정 하려면 **도움말 URL**에서 도움말 텍스트의 위치를 입력 합니다.
    
      - 모임 초대에 나타나는 법적 고 지 텍스트를 사용자 지정 하려면 **legal 텍스트 URL**에 법적 텍스트의 위치를 입력 합니다.
    
      - 모임 초대에 나타나는 바닥글 텍스트를 사용자 **정의 하려면 사용자 지정 바닥글 텍스트**에 텍스트를 입력 합니다.

10. **커밋**을 클릭합니다.

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a>기존 모임 구성 모음을 수정 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 표시줄에서 **회의**, **모임 구성**을 차례로 클릭합니다.

4.  모임 구성 목록에서 변경 하려는 구성을 클릭 하 고 **편집**을 클릭 한 후에 **자세한 정보 표시**를 클릭 합니다.

5.  **모임 구성 편집**에서 수정할 수 없는 구성 이름을 제외한 모든 구성 설정을 수정 합니다.

6.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 새 모임 구성 설정 만들기

Windows PowerShell 및 Get-csmeetingconfiguration cmdlet을 사용 하 여 사이트 범위 에서만 모임 구성 설정을 만들 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a>기본값을 사용 하는 모임 구성 설정을 만들려면

  - 이 명령은 Redmond 사이트에 대 한 새 모임 구성 설정 집합을 만듭니다.
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    이전 명령에서 필수 Identity 매개 변수를 제외한 모든 매개 변수를 지정 하지 않았으므로 새 모임 구성 설정에는 모든 속성의 기본값이 사용 됩니다.

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a>모임 구성 설정을 만들 때 속성 값을 변경 하려면

  - 다른 속성 값을 사용하는 설정을 만들려면 간단히 적합한 매개 변수와 매개 변수 값을 포함하면 됩니다. 예를 들어 기본적으로 모든 사용자에 게 발표자로 모임에 참석 하도록 허용 하는 모임 구성 설정 모음을 만들려면 다음과 같은 명령을 사용 합니다.
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a>모임 구성 설정을 만들 때 여러 속성 값을 변경 하려면

  - 여러 매개 변수를 포함하여 여러 속성 값을 수정할 수 있습니다. 예를 들어이 명령은 모든 사람을 발표자로 모임에 다시 겁니다 다음, PSTN 사용자가 모임에 공식적으로 참석할 때까지 로비에서 대기 하도록 강제 합니다.
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

자세한 내용은 [get-csmeetingconfiguration](https://technet.microsoft.com/library/Gg398065(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

