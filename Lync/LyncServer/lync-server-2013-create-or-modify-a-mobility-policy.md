---
title: 'Lync Server 2013: 모바일 정책 만들기 또는 수정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a mobility policy
ms:assetid: fc2dfea0-2215-440d-9f4b-7c985da29211
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721946(v=OCS.15)
ms:contentKeyID: 49733884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3f64e74b389b268027e06b2f4103b0c828c5be6f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-mobility-policy-in-lync-server-2013"></a>Lync Server 2013에서 모바일 정책 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

모바일 사용자가 인스턴트 메시지 (IM), 현재 상태, 대화 상대 등의 Lync 기능에 지원 되는 모바일 장치를 사용할 수 있도록 이동성 정책을 만들거나 수정할 수 있습니다. Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸에서 모바일 정책을 만들거나 수정할 수 있습니다.

<div>

## <a name="to-create-a-mobility-policy-with-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 모바일 정책 만들기

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **모바일 정책** 탐색 단추를 클릭 합니다.

4.  **모바일 정책** 페이지에서 **새로 만들기**를 클릭 하 고 다음 중 하나를 수행 합니다.
    
    1.  사이트 모바일 정책을 만들려면 **사이트 정책을**클릭 하 고 사이트를 클릭 한 다음 **확인**을 클릭 하 고 기본 설정을 검토 하 고 원하는 경우 변경 작업을 수행 합니다.
    
    2.  사용자 이동성 정책을 만들려면 **사용자 정책을**클릭 하 고, 이름을 입력 하 고, 기본 설정을 검토 하 고, 원하는 대로 변경 합니다.

5.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="to-modify-a-mobility-policy-with-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 모바일 정책을 수정 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **모바일 정책** 탐색 단추를 클릭 합니다.

4.  **모바일 정책** 페이지에서 기존 이동성 정책 중 하나를 클릭 합니다.

5.  **편집** 메뉴에서 **세부 정보 표시**를 클릭 합니다.

6.  설정을 편집 합니다.

7.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="creating-external-access-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 외부 액세스 정책 만들기

Windows PowerShell 및 **CsMobilityPolicy** cmdlet을 사용 하 여 사이트 범위 또는 사용자 단위 범위에서 모바일 기능 정책을 만들 수 있습니다. 또한 **Set-CsMobilityPolicy** cmdlet을 사용 하 여 전역 정책을 비롯 한 기존 정책을 수정할 수 있습니다. 이러한 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-create-a-mobility-policy-at-the-site-scope"></a>사이트 범위에서 이동성 정책 만들기

  - 이 명령은 Redmond 사이트에 대 한 새로운 이동성 정책을 만듭니다.
    
        New-CsMobilityPolicy -Identity "site:Redmond"
    
    앞의 명령에서 필수 Id 매개 변수 이외의 매개 변수를 지정 하지 않았으므로 정책의 모든 속성에 대 한 기본값이 사용 됩니다.

</div>

<div>

## <a name="to-create-a-mobility-policy-at-the-per-user-scope"></a>사용자별 범위에서 모바일 정책을 만들려면

  - 사용자별 범위에서 모바일 정책을 만들려면 정책에 대 한 고유 Id를 지정 합니다.
    
        New-CsMobilityPolicy -Identity "RedmondMobilityPolicy"

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-a-mobility-policy"></a>이동성 정책을 만들 때 단일 속성 값을 변경 하려면

  - 다른 속성 값을 사용 하는 정책을 만들려면 적절 한 매개 변수와 매개 변수 값을 포함 합니다. 예를 들어이 명령은 작업을 통한 통화를 사용 하지 않도록 설정 하는 이동성 정책을 만듭니다.
    
        New-CsMobilityPolicy -Identity "site:Redmond" -EnableOutsideVoice $False

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-a-mobility-policy"></a>이동성 정책을 만들 때 여러 속성 값을 변경 하려면

  - 여러 매개 변수를 포함 하 여 여러 속성 값을 수정할 수 있습니다. 예를 들어이 명령은 작업을 통해 이동성 및 통화를 모두 해제 하는 정책을 만듭니다.
    
        New-CsMobilityPolicy "site:Redmond" -EnableMobility $False -EnableOutsideVoice $False

</div>

자세한 내용은 [새 CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy) 및 [CsMobilityPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsMobilityPolicy) Cmdlet에 대 한 도움말 항목을 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 모바일 정책 구성](lync-server-2013-configuring-mobility-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

