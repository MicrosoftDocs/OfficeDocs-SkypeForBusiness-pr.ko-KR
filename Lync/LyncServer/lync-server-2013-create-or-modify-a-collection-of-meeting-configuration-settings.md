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
ms.openlocfilehash: 0a5f80066a68b45e062a351478bea93a5c2e8fd0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-meeting-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 모임 구성 설정 모음 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

모임 구성 페이지의 설정을 사용 하 여 모임 참가 환경의 다양 한 특성을 정의할 수 있습니다. 기본적으로 전역 설정은 참가 환경을 정의 합니다. 사이트 수준 및 풀 수준 모임 참가 설정을 만들 수도 있습니다. 풀 수준 설정을 만드는 경우 해당 설정이 해당 풀에서 호스트 하는 모든 모임에 적용 됩니다. 풀 수준 설정을 만들지 않으면 사이트 수준 설정이 있는 경우 적용 됩니다. 사이트 수준 설정을 정의 하지 않으면 모든 모임에 전역 설정이 적용 됩니다.

<div>

## <a name="to-create-new-meeting-join-settings"></a>새 모임 참가 설정을 만들려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **회의** 를 클릭 한 다음 **모임 구성을**클릭 합니다.

4.  **모임 구성** 페이지에서 **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.
    
      - 사이트 수준 정책을 만들려면 **사이트 구성을**클릭 합니다. 사이트 검색 **선택** 필드에 모임 참가 설정을 정의할 사이트 이름의 전부 또는 일부를 입력 합니다. 사이트 결과 목록에서 원하는 사이트를 클릭 한 다음 **확인**을 클릭 합니다.
    
      - 풀 수준 정책을 만들려면 **풀 구성을**클릭 합니다. 서비스 검색 **선택** 필드에 모임 참가 설정을 정의할 풀 서비스 이름의 전부 또는 일부를 입력 합니다. 결과 서비스 목록에서 원하는 풀을 클릭 한 다음 **확인**을 클릭 합니다.

5.  대기실를 통해 PSTN (공개 교환 전화 네트워크)에서 전화 접속 하는 참가자를 라우팅하려면 **pstn 발신자의 로비 사용 안 함** 확인란의 선택을 취소 합니다. 기본적으로 PSTN에서 전화를 거는 참가자는 모임으로 직접 이동 합니다.

6.  모임에서 발표자가 될 수 있는 사용자를 구성 하려면 **발표자로 지정**에서 다음 중 하나를 수행 합니다.
    
      - 이끌이 이외의 사용자가 발표자가 될 수 없도록 하려면 **없음**을 클릭 합니다.
    
      - 조직의 구성원 인 참가자만 발표자로 지정할 수 있도록 하려면 **회사**를 클릭 합니다. 이는 기본 설정입니다.
    
      - 모든 참가자가 발표자로 지정 하도록 허용 하려면 **모든 사용자**를 클릭 합니다.

7.  모임을 예약할 때 주최자가 회의 유형을 선택 하도록 하려면 **기본적으로 지정 된 회의 유형** 확인란의 선택을 취소 합니다. 기본적으로 회의 유형은 자동으로 지정 됩니다.

8.  익명 (인증 되지 않은) 사용자가 자동으로 허용 되지 않도록 하려면 **기본적으로 익명 사용자** 허용 확인란의 선택을 취소 합니다. 기본적으로 익명 사용자는 자동으로 모임에 참석할 수 있습니다.

9.  참가자에 게 전송 되는 모임 초대를 사용자 지정 하려면 다음을 실행 합니다. Url 및 사용자 지정 바닥글 텍스트에 대 한 최대 길이는 1KB 것을 참고 하세요. **도움말 URL**을 제외한 사용자 지정에 대 한 값을 지정 하지 않으면 모임에 포함 되지 않습니다. 사용자 지정 도움말 URL이 포함 되어 있지 않으면 Lync에 대 한 기본 도움말 URL이 초대에 표시 됩니다.
    
      - 모임 초대에 표시 되는 로고를 사용자 지정 하려면 **로고 URL**에 로고의 위치를 입력 합니다.
        
        <div>
        

        > [!NOTE]
        > 로고는 188 x 30 픽셀 크기의 GIF 또는 JPG 이미지 여야 합니다.

        
        </div>
    
      - 모임 초대에 표시 되는 도움말 텍스트를 사용자 지정 하려면 **도움말 URL**에 도움말 텍스트의 위치를 입력 합니다.
    
      - 모임 초대에 표시 되는 법률 텍스트를 사용자 지정 하려면 **legal 텍스트 URL**에 법률 텍스트의 위치를 입력 합니다.
    
      - 모임 초대에 표시 되는 바닥글 텍스트를 사용자 지정 하려면 **사용자 지정 바닥글 텍스트**에 텍스트를 입력 합니다.

10. **커밋**을 클릭합니다.

</div>

<div>

## <a name="to-modify-an-existing-collection-of-meeting-configurations"></a>기존 모임 구성 모음을 수정 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **회의** 를 클릭 한 다음 **모임 구성을**클릭 합니다.

4.  모임 구성 목록에서 변경 하려는 구성을 클릭 하 고 **편집**을 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

5.  **모임 구성 편집**에서 수정할 수 없는 구성 이름을 제외한 모든 구성 설정을 수정 합니다.

6.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="creating-new-meeting-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 새 모임 구성 설정 만들기

Windows PowerShell 및 새 CsMeetingConfiguration cmdlet을 사용 하 여 모임 구성 설정을 만들 수 있습니다 (사이트 범위에만 해당). 이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-create-meeting-configuration-settings-that-use-the-default-values"></a>기본 값을 사용 하는 모임 구성 설정을 만들려면

  - 이 명령은 Redmond 사이트에 대 한 새 모임 구성 설정 집합을 만듭니다.
    
        New-CsMeetingConfiguration -Identity "site:Redmond"
    
    앞의 명령에서 필수 Id 매개 변수 이외의 매개 변수를 지정 하지 않았으므로 새 모임 구성 설정에는 해당 속성에 대 한 기본값이 사용 됩니다.

</div>

<div>

## <a name="to-change-a-property-value-when-creating-meeting-configuration-settings"></a>모임 구성 설정을 만들 때 속성 값을 변경 하려면

  - 다른 속성 값을 사용 하는 설정을 만들려면 간단히 적절 한 매개 변수와 매개 변수 값을 포함 합니다. 예를 들어 기본적으로 모든 사용자가 발표자로 모임에 참가 하도록 허용 하는 모임 구성 설정의 컬렉션을 만들려면 다음과 같은 명령을 사용 합니다.
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-meeting-configuration-settings"></a>모임 구성 설정을 만들 때 여러 속성 값을 변경 하려면

  - 여러 매개 변수를 포함 하 여 여러 속성 값을 수정할 수 있습니다. 예를 들어이 명령은 모든 사람을 발표자로 모임에 입장할, PSTN 사용자가 모임에 공식적으로 참석할 때까지 대기실에서 대기 하도록 강제 합니다.
    
        New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True

</div>

자세한 내용은 [새 CsMeetingConfiguration](https://technet.microsoft.com/en-us/library/Gg398065(v=OCS.15)) cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

