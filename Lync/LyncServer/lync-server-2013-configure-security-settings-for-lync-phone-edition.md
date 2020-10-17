---
title: 'Lync Server 2013: Lync Phone Edition에 대 한 보안 설정 구성'
description: 'Lync Server 2013: Lync Phone Edition에 대 한 보안 설정을 구성 합니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure security settings for Lync Phone Edition
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521014(v=OCS.15)
ms:contentKeyID: 48184464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 82e6a6488db66a8497930ee6b2d1aec6fc8b0b2d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564354"
---
# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a>Lync Server 2013에서 Lync Phone Edition에 대 한 보안 설정 구성

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

SIP 보안 설정 및 전화 잠금 설정을 통해 Lync Phone Edition을 실행 하는 장치의 보안을 향상 시킬 수 있습니다.

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a>Lync Phone Edition에 대 한 보안 설정을 구성 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭하고 **장치 구성**을 클릭합니다.

4.  **장치 구성** 페이지의 장치 구성 목록에서 보안 설정을 변경 하려는 구성을 두 번 클릭 합니다.

5.  **장치 구성 편집**의 **SIP 보안**에서 sip 보안 수준을 지정 합니다. 기본 수준은 **높음**이며 사용 하는 것이 좋습니다.

6.  **장치 구성 편집**의 **전화 잠금**에서 기본적으로 선택 되어 있는 **장치 잠금 적용** 확인란을 선택 하거나 선택을 취소 하 고 최소 PIN 길이 (기본적으로 6 자)와 제한 시간 (기본값은 10 분)을 지정 합니다. 이러한 기본값을 사용 하거나 PIN 길이를 늘리거나 제한 시간을 줄이는 것이 좋습니다.
    
    <div>
    

    > [!NOTE]  
    > 자세한 내용은 <A href="lync-server-2013-enforce-phone-locking.md">Lync Server 2013에서 전화 잠금 적용</A>을 참조 하십시오.

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 Lync Phone Edition 전화에 대 한 보안 설정 구성

Lync Server 관리 셸 및 **set-csucphoneconfiguration** cmdlet을 사용 하 여 보안 설정을 관리할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.

<div>

## <a name="to-modify-the-sip-security-mode"></a>SIP 보안 모드를 수정 하려면

  - 이 명령은 UC 전화 설정의 전역 컬렉션에 대 한 SIPSecurityMode를 Medium으로 설정 합니다. 또한 SIP 보안을 낮음 또는 높음으로 설정할 수도 있습니다 (기본값).
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a>최소 PIN 길이를 수정 하려면

  - 이 예에서는 모든 UC 전화 설정이 최소 7 자리의 PIN 길이를 요구 하도록 수정 됩니다.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

자세한 내용은 [set-csucphoneconfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)를 참조 하십시오.

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

