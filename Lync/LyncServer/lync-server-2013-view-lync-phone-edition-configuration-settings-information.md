---
title: 'Lync Server 2013: Lync Phone Edition 구성 설정 정보 보기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 213b9775b22818c34eb8f7896ea02a4872182a42
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a>Lync Server 2013에서 Lync Phone Edition 구성 설정 정보 보기

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

Lync Phone Edition을 실행 하는 장치에 대 한 구성 정보를 볼 수 있습니다. 정보는 모음으로 구성 됩니다. Lync Server를 설치할 때 배포에서 Lync Phone Edition을 실행 하는 모든 장치에 적용 되는 Lync Phone Edition 설정의 모음을 가져옵니다. 특정 사이트에 대 한 새 설정 모음을 만들 수도 있습니다. 전역 설정 보다 사이트 설정이 우선권을 갖습니다. 각 설정 모음에는 이름, 범위 (전역 또는 사이트), SIP 보안 설정, 로깅 수준, 보이스 서비스 품질 (QoS) 수준, 전화 잠금 설정, 전화 잠금 세부 정보, 즉 잠금 해제 개인 식별의 최소 길이가 지정 됩니다. 전화 번호 (PIN) 및 휴대폰 자체를 잠그는 시간

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a>Lync Phone Edition을 실행 하는 장치에 대 한 구성 정보를 보려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **장치 구성** 탐색 단추를 클릭 합니다.

4.  **장치 구성** 페이지에서 정보를 볼 설정 모음을 클릭 합니다. 이름, 범위, SIP 보안 설정, 음성 음질 수준 및 전화 잠금 설정이 기본 페이지에 나열 됩니다. 로깅 수준 및 전화 잠금 세부 정보를 보려면 **편집** 메뉴를 클릭 한 다음 **세부 정보 표시**를 클릭 합니다.

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 Lync Phone Edition 구성 정보 보기

Lync Server Management Shell 및 **CsUCPhoneConfiguration** cmdlet을 사용 하 여 Lync Phone Edition 구성 설정을 볼 수 있습니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a>Lync Phone Edition 구성 정보를 보려면

  - 모든 Lync Phone Edition 구성 설정에 대 한 정보를 보려면 Lync Server 관리 셸에서 다음 명령을 입력 한 다음 enter 키를 누릅니다.
    
        Get-CsUCPhoneConfiguration
    
    명령은 다음과 같은 정보를 반환 합니다.
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

</div>

자세한 내용은 [Get-help CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)을 참조 하세요.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 Lync Phone Edition 구성 설정 모음 만들기 또는 수정](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[Lync Server 2013에서 Lync Phone Edition 구성 설정의 기존 모음 삭제](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Lync Server 2013에서 Lync Phone 에디션에 대 한 보안 설정을 구성 합니다.](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Lync Server 2013에서 전화 잠금 적용](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

