---
title: 'Lync Server 2013: PIN 정책 정보 보기 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View PIN policy inforrmation
ms:assetid: 1d48b060-d77f-44ee-b70f-3ce128aedac4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687985(v=OCS.15)
ms:contentKeyID: 49733575
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ab1705d7af62b6a44d278b666e619fae119540c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038050"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-pin-policy-inforrmation-in-lync-server-2013"></a>Lync Server 2013에서 PIN 정책 정보 보기 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

**Pin 정책** 탭을 사용 하 여 IP 전화와 함께 Lync 2013에 연결 하는 사용자의 PIN (개인 식별 번호) 인증을 볼 수 있습니다. PIN 인증을 사용하려면 웹 서비스 설정에서 **PIN 인증 사용**이 선택되어 있는지 확인합니다. 자세한 내용은 [Modify 기존 웹 서비스 구성 설정에서 Lync Server 2013](lync-server-2013-modify-existing-web-service-configuration-settings.md)를 참조 하세요.

사용자 수준 또는 사이트 수준 PIN 정책을 수정하려면 다음 단계를 수행합니다.

<div>

## <a name="to-view-information-about-a-pin-policy-in-lync-server-control-panel"></a>Lync Server 제어판의 PIN 정책에 대 한 정보를 보려면

1.  RTCUniversalServerAdmins 그룹의 구성원 이거나이에 해당 하는 사용자 권한이 있는 사용자 계정 또는 CsServerAdministrator 또는 CsAdministrator 역할에 할당 된 경우 Lync Server 2013을 배포한 네트워크에 있는 컴퓨터에 로그온 합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **보안**을 클릭하고 **PIN 정책**을 클릭합니다.

4.  **PIN 정책** 페이지에서 정책을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭합니다.

</div>

<div>

## <a name="viewing-pin-policies-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 PIN 정책 보기

또한 Windows PowerShell 및 Get-cspinpolicy cmdlet을 사용 하 여 PIN 정책을 볼 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-view-pin-policies"></a>PIN 정책을 보려면

  - 모든 PIN 정책에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 하 고 enter 키를 누릅니다.
    
        Get-CsPinPolicy
    
    그러면 다음과 같은 정보가 반환됩니다.
    
        Identity             : Global
        Description          :
        MinPasswordLength    : 5
        PINHistoryCount      : 0
        AllowCommonPatterns  : False
        PINLifetime          : 0
        MaximumLogonAttempts :

</div>

자세한 내용은 [get-cspinpolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsPinPolicy) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 기존 웹 서비스 구성 설정 수정](lync-server-2013-modify-existing-web-service-configuration-settings.md)  
[Lync Server 2013에서 새 PIN 정책 만들기](lync-server-2013-create-a-new-pin-policy.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

