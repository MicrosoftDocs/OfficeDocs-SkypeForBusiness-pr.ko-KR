---
title: Lync Phone Edition 구성 설정의 기존 컬렉션 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce796b13ea69296fa72799a13d35cb2046a643b0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514635"
---
# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 Lync Phone Edition 구성 설정의 기존 컬렉션 삭제

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

Lync Phone Edition을 실행 하는 장치에 대 한 설정 컬렉션을 더 이상 사용 하지 않으려면 삭제 합니다. 사이트의 컬렉션을 삭제하면 전역 설정이 해당 사이트의 전화에 적용됩니다. 전역 컬렉션은 삭제할 수 없습니다.

<div>


> [!NOTE]
> 컬렉션을 삭제하는 대신 일부 설정을 변경만 할 수 있습니다. 이 작업을 수행 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">2013 Lync Phone Edition 구성 설정 모음을 만들거나 수정 하는</A>방법을 참조 하세요.



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a>Lync Phone Edition 구성 설정 모음을 삭제 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭하고 **장치 구성** 탐색 단추를 클릭합니다.

4.  **장치 구성** 페이지에서 삭제할 컬렉션을 클릭하고 **편집** 메뉴를 클릭한 후에 **삭제**를 클릭합니다.
    
    <div>
    

    > [!NOTE]
    > 전역 컬렉션을 삭제해도 단순히 설정이 기본 설정으로 돌아가며 컬렉션이 제거되는 것은 아닙니다.

    
    </div>

5.  확인 상자에서 **확인**을 클릭합니다.

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 Lync Phone Edition 구성 설정 제거

Lync Phone Edition 구성 설정은 Windows PowerShell 및 **CsUCConfiguration** cmdlet을 사용 하 여 삭제할 수 있습니다. Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a>Lync Phone Edition 구성 설정의 지정 된 컬렉션을 제거 하려면

  - 다음 명령은 Redmond 사이트에 적용된 UC 전화 구성 설정을 삭제합니다.
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a>사이트 범위에 적용 된 모든 Lync Phone Edition 구성 설정을 제거 하려면

  - 다음 명령은 서비스 범위에 적용된 모든 UC 전화 구성 설정을 제거합니다.
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a>전화 잠금이 사용 하지 않도록 설정 된 모든 Lync Phone Edition 구성 설정을 제거 하려면

  - 다음 명령은 전화 잠금이 사용하지 않도록 설정된 UC 전화 구성 설정 컬렉션을 삭제합니다.
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

자세한 내용은 [Remove-set-csucphoneconfiguration](https://technet.microsoft.com/library/Gg398249(v=OCS.15))를 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

