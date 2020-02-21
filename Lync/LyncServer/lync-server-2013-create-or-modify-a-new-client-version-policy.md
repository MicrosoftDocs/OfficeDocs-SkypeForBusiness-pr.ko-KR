---
title: 'Lync Server 2013: 새 클라이언트 버전 정책 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a new client version policy
ms:assetid: 4be6e449-aa82-4b46-abb1-d31281573a72
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898476(v=OCS.15)
ms:contentKeyID: 50873756
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e95abe52883bff2c99ad02b01ea4cc1473f4626f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-new-client-version-policy-in-lync-server-2013"></a>Lync Server 2013에서 새 클라이언트 버전 정책 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

클라이언트 버전 정책을 사용 하 여 해당 환경에서 지원 되는 클라이언트 버전을 지정할 수 있습니다. 클라이언트 버전 관리를 사용 하면 여러 클라이언트 버전을 지 원하는 데 드는 비용을 줄일 수 있습니다. 이전 버전의 클라이언트가 상호 작용 하는 경우 이전 버전의 클라이언트에 의해 사용 가능한 기능을 제한할 수 있으므로 전반적인 사용자 환경도 향상 시킬 수 있습니다. Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸에서 클라이언트 버전 정책을 만들거나 수정할 수 있습니다.

<div>

## <a name="to-create-or-modify-client-version-policies-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 클라이언트 버전 정책을 만들거나 수정 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 합니다.
    
    <div>
    

    > [!NOTE]  
    > <STRONG>클라이언트 버전 정책</STRONG> 탭이 기본적으로 선택 되어 있습니다.

    
    </div>

4.  **클라이언트 버전 정책** 페이지에서 다음 중 하나를 수행 합니다.
    
      - 클라이언트 버전 정책을 만들려면 **새로 만들기**를 클릭 하 고 **사이트 정책**, **풀 정책**또는 **사용자 정책을**선택한 다음 **확인**을 클릭 합니다.
    
      - 전역 정책 또는 기존 클라이언트 버전 정책을 수정 하려면 정책을 선택 하 고 **편집**을 클릭 한 후에 **자세한 정보 표시**를 클릭 합니다.

5.  **클라이언트 버전 정책 편집** 페이지에서 [Lync Server 2013의 새 클라이언트 버전 정책 규칙 만들기 또는 수정](lync-server-2013-create-or-modify-a-new-client-version-policy-rule.md)에 설명 된 대로 규칙을 만들거나 수정 합니다.

</div>

<div>

## <a name="creating-or-modifying-client-version-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 클라이언트 버전 정책 만들기 또는 수정

**새-CsClientVersionPolicy** cmdlet을 사용 하 여 클라이언트 버전 정책을 만든 후에는 **csclientversionpolicy** cmdlet을 사용 하 여 해당 정책 설정을 수정할 수 있습니다. 이러한 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-create-a-new-site-scoped-client-version-policy"></a>새 사이트 범위 클라이언트 버전 정책을 만들려면

  - 다음 명령은 Redmond 사이트에 적용 된 새 클라이언트 버전 정책을 만듭니다. 추가 매개 변수를 지정 하지 않았으므로 새 정책에서 기본 클라이언트 버전 설정을 사용 하 게 됩니다.
    
        New-CsClientVersionPolicy -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-per-user-client-version-policy"></a>새 사용자별 클라이언트 버전 정책을 만들려면

  - 사용자별 정책을 만들려면 다음과 같은 명령을 사용 합니다.
    
        New-CsClientVersionPolicy -Identity "RedmondClientVersionPolicy"

</div>

자세한 내용은 [새-CsClientVersionPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientVersionPolicy) Cmdlet 및 [설정 된 csclientversionpolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientVersionPolicy) Cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

