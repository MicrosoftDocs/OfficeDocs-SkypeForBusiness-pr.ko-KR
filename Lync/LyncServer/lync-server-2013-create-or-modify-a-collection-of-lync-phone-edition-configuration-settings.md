---
title: Lync Phone Edition 구성 설정 모음 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af910ccffd65f14b7f11919ab66ae95acbf4e09
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180125"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 Lync Phone Edition 구성 설정 모음 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

Lync Server를 설치할 때 Lync Phone Edition 설정의 전역 컬렉션을 가져옵니다. 이러한 설정은 배포에서 Lync Phone Edition을 실행 하는 모든 장치에 적용 됩니다. 이러한 설정은 언제 든 지 변경할 수 있습니다. 특정 사이트의 장치에 적용 되는 새 설정 모음을 설정할 수도 있습니다. 사이트 설정은 전역 설정보다 우선합니다.

구성 설정은 컬렉션 이름, 범위 (전역 또는 사이트), SIP 보안 설정, 로깅 수준, 음성 QoS (서비스 품질) 수준, 전화 잠금 설정, 전화 잠금 세부 정보 (즉, a)가 개인 식별 번호를 잠금 해제 하는 시간 (초)으로 구성 됩니다. PIN)은 잠금 전까지 유휴 상태를 유지 해야 합니다.

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a>Lync Phone Edition 구성 설정 컬렉션을 만들거나 기존 컬렉션에 대 한 설정을 편집 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭하고 **장치 구성** 탐색 단추를 클릭합니다.

4.  **장치 구성** 페이지에서 다음 중 하나를 수행 합니다.
    
      - Lync Phone Edition 구성 설정의 새 컬렉션을 만들려면 **새로**만들기를 클릭 하 고 사이트를 선택한 다음 **확인**을 클릭 하 고 기본 설정을 검토 한 다음 원하는 경우 변경 합니다.
    
      - 기존 컬렉션에서 설정을 편집 하려면 컬렉션을 클릭 하 고 **편집** 메뉴를 클릭 한 다음 **자세한 정보 표시**를 클릭 하 고 변경 작업을 수행 합니다.
        
        <div>
        

        > [!TIP]
        > 전역 컬렉션에 대 한 기본 설정을 사용 하 여 다시 돌아가려면 전역 컬렉션을 클릭 하 고 <STRONG>편집</STRONG> 메뉴를 클릭 한 다음 <STRONG>삭제</STRONG>를 클릭 하 고 <STRONG>확인</STRONG>을 클릭 합니다. 전역 컬렉션은 삭제 되지 않습니다. 설정을 기본값으로 다시 설정 하기만 하면 됩니다.

        
        </div>

5.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 새 Lync Phone Edition 구성 설정 만들기

Windows PowerShell 및 **set-csucphoneconfiguration** cmdlet을 사용 하 여 사이트 범위 에서만 Lync Phone Edition 구성 설정을 만들 수 있습니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a>기본값을 사용 하는 새 Lync Phone Edition 구성 설정을 만들려면

  - 이 명령은 Redmond 사이트에 대 한 새로운 UC 전화 구성 설정 집합을 만듭니다.
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    이전 명령에서 필수 Identity 매개 변수를 제외하고는 지정된 매개 변수가 없으므로 새 구성 설정 컬렉션에는 모든 속성의 기본값이 사용됩니다.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a>새 Lync Phone Edition 구성 설정을 만들 때 단일 속성 값을 변경 하려면

  - 다른 속성 값을 사용하는 설정을 만들려면 간단히 적합한 매개 변수와 매개 변수 값을 포함하면 됩니다. 예를 들어 기본적으로 전화 잠금이 필요한 UC 전화 구성 설정 모음을 만들려면 다음과 같은 명령을 사용 합니다.
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a>새 Lync Phone Edition 구성 설정을 만들 때 여러 속성 값을 변경 하려면

  - 여러 매개 변수를 포함하여 여러 속성 값을 수정할 수 있습니다. 예를 들어이 명령은 전화 잠금을 적용 하 고 최소 PIN 길이를 8 자리로 설정 합니다.
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

자세한 내용은 [set-csucphoneconfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))를 참조 하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 Lync Phone Edition 구성 설정의 기존 컬렉션 삭제](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Lync Server 2013에서 Lync Phone Edition에 대 한 보안 설정 구성](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Lync Server 2013에서 전화 잠금 적용](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

