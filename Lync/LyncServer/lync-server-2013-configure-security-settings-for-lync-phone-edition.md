---
title: 'Lync Server 2013: Lync Phone Edition에 대 한 보안 설정 구성'
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
ms.openlocfilehash: 6f414eb395025b359d074bb1d5882b20919eb3f8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730018"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-security-settings-for-lync-phone-edition-in-lync-server-2013"></a>Lync Server 2013에서 Lync Phone 에디션에 대 한 보안 설정을 구성 합니다.

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

SIP 보안 설정 및 전화 잠금 설정을 통해 Lync Phone Edition을 실행 하는 디바이스의 보안을 향상 시킬 수 있습니다.

<div>

## <a name="to-configure-security-settings-for-lync-phone-edition"></a>Lync Phone Edition에 대 한 보안 설정을 구성 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **장치 구성을**클릭 합니다.

4.  **장치 구성** 페이지의 장치 구성 목록에서 보안 설정을 변경 하려는 구성을 두 번 클릭 합니다.

5.  **장치 구성 편집**의 **SIP 보안**에서 sip 보안 수준을 지정 합니다. 기본 수준은 **높음으로**사용 하는 것이 좋습니다.

6.  **장치 구성 편집**의 **전화 잠금**에서 **장치 잠금 적용** 확인란 (기본적으로 선택 됨)을 선택 하거나 선택을 취소 하 고 최소 PIN 길이 (기본적으로 6 자) 및 제한 시간 (기본적으로 10 분)을 지정 합니다. 이러한 기본값을 사용 하는 것이 좋으며 PIN 길이 및/또는 제한 시간 간격을 감소 시키는 것이 좋습니다.
    
    <div>
    

    > [!NOTE]  
    > 자세한 내용은 <A href="lync-server-2013-enforce-phone-locking.md">Lync Server 2013에서 전화 잠금 적용</A>을 참조 하세요.

    
    </div>

</div>

<div>

## <a name="configuring-security-settings-for-lync-phone-edition-phones-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 Lync Phone Edition 전화에 대 한 보안 설정 구성

Lync Server Management Shell 및 **CsUCPhoneConfiguration** cmdlet을 사용 하 여 보안 설정을 관리할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-modify-the-sip-security-mode"></a>SIP 보안 모드를 수정 하려면

  - 이 명령은 UC 전화 설정의 전역 컬렉션에 대 한 SIPSecurityMode를 Medium으로 설정 합니다. 또한 SIP 보안은 낮음 또는 높음 (기본값)으로 설정할 수 있습니다.
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

</div>

<div>

## <a name="to-modify-the-minimum-pin-length"></a>최소 PIN 길이를 수정 하려면

  - 이 예제에서는 모든 UC 전화 설정이 최소 7 자리 PIN 길이를 요구 하도록 수정 됩니다.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

</div>

자세한 내용은 [Get-help CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)을 참조 하세요.

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

