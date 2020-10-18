---
title: 'Lync Server 2013: 전화 잠금 적용'
description: 'Lync Server 2013: 전화 잠금을 적용 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5afae4fa27edf9378bacc39a29697c9607b25c07
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575604"
---
# <a name="enforce-phone-locking-in-lync-server-2013"></a>Lync Server 2013에서 전화 잠금 적용

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

Lync Phone Edition 장치는 보안상의 이유로 잠길 수 있습니다. 전화 잠금을 적용 하면 사용자가 구성한 일정 기간이 지난 후 Lync Phone Edition을 실행 하는 장치가 잠깁니다. 전화가 잠기면 사용자가 전화를 걸 수 있지만 일정 및 연락처 정보, 음성 메일 또는 통화 로그에 액세스할 수 없습니다. 전화 잠금을 해제 하기 위해 사용자는 PIN을 입력 합니다.

전화 잠금을 적용 하려면 Lync Server 제어판 또는 Lync Server PowerShell cmdlet을 사용 하 여 사용 하도록 설정 하 고 구성 합니다. 전화 잠금은 전역적으로 또는이를 구성 하는 사이트 내 에서만 설정할 수 있습니다.

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a>전화 잠금을 구성 하 고 적용 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  **클라이언트**를 클릭 하 고 **장치 구성을**클릭 합니다.

4.  **장치 구성** 탭의 장치 구성 목록에서 전화 잠금 설정을 변경할 구성을 두 번 클릭 합니다.

5.  **장치 구성 편집** 대화 상자에서 **장치 잠금 적용** 확인란이 선택 되어 있는지 확인 합니다.

6.  **최소 PIN 길이**에서 잠금 해제 PIN에 포함 해야 하는 최소 자릿수의 기본값을 적용 하거나 새 값을 지정 합니다. PIN 길이의 범위는 4에서 15 사이의 숫자이 고 기본값은 6입니다.

7.  **전화 잠금 시간 제한**에서 전화를 잠그기 전 까지의 최소 기간에 대해 기본값을 적용 하거나 새 값을 지정 합니다. 시간 제한 범위는 0 ~ 60 분 이며 기본값은 10입니다. HH: MM: SS 형식으로 값을 입력 합니다.

8.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 전화 잠금 적용

전화 잠금은 Set-CsUCPhoneConfiguration cmdlet을 사용 하 여 적용할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.

<div>

## <a name="to-enable-phone-locking"></a>전화 잠금을 사용 하도록 설정 하려면

  - 다음 명령은 Redmond 사이트에 대 한 전화 잠금을 사용 하도록 설정 합니다. 전화 잠금을 사용 하지 않으려면 EnforcePhoneLock 속성을 False ($False)로 설정 합니다.
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a>전화 잠금을 사용 하도록 설정 하 고 전화 잠금 제한 시간을 수정 하려면

  - 이 명령은 전화 잠금을 사용 하도록 설정 하 고 전화 잠금 제한 시간을 30 분으로 설정할 수도 있습니다.
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a>조직 전체에서 전화 잠금을 사용 하도록 설정 하려면

  - 이 예에서는 조직에서 사용 중인 모든 UC 전화 구성 설정에 대해 전화 잠금이 사용 되도록 설정 됩니다.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

자세한 내용은 [set-csucphoneconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013 인증 관리](lync-server-2013-managing-lync-server-authentication.md)  


[Lync Server 2013에서 장치, 전화 및 클라이언트 응용 프로그램 관리](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

