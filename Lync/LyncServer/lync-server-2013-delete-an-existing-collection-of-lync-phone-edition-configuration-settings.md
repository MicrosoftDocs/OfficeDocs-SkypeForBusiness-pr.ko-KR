---
title: Lync Phone Edition 구성 설정의 기존 모음 삭제
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Delete an existing collection of Lync Phone Edition configuration settings
ms:assetid: 1bfc427d-4dcd-4199-b25f-8d5cfec2164f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687984(v=OCS.15)
ms:contentKeyID: 49733574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a2be234fdbb2beb9d2f6f038acbdad03dd8d2048
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="delete-an-existing-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 Lync Phone Edition 구성 설정의 기존 모음 삭제

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

Lync Phone Edition을 실행 하는 장치에 대 한 설정 모음을 더 이상 사용 하지 않으려면 삭제 합니다. 사이트에 대 한 컬렉션을 삭제 하면 해당 사이트의 휴대폰에 전역 설정이 적용 됩니다. 전역 모음은 삭제할 수 없습니다.

<div>


> [!NOTE]
> 컬렉션을 삭제 하는 대신 일부 설정을 변경 하는 것이 좋습니다. 이 작업을 수행 하는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md">Lync Server 2013에서 Lync Phone Edition 구성 설정 모음 만들기 또는 수정을</A>참조 하세요.



</div>

<div>

## <a name="to-delete-a-collection-of-lync-phone-edition-configuration-settings"></a>Lync Phone Edition 구성 설정 모음을 삭제 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당 된 사용자 계정에서 내부 배포의 컴퓨터에 로그온 합니다.

2.  브라우저 창을 열고 관리자 URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Lync server 2013 관리 도구 열기](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하세요.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 한 다음 **장치 구성** 탐색 단추를 클릭 합니다.

4.  **장치 구성** 페이지에서 삭제 하려는 모음을 클릭 하 고 **편집** 메뉴를 클릭 한 다음 **삭제**를 클릭 합니다.
    
    <div>
    

    > [!NOTE]
    > 전역 컬렉션을 삭제 하면 설정이 기본 설정으로 돌아갑니다. 컬렉션이 사라집니다.

    
    </div>

5.  확인 상자에서 **확인**을 클릭 합니다.

</div>

<div>

## <a name="removing-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 Lync Phone Edition 구성 설정 제거

Windows PowerShell 및 **CsUCConfiguration** cmdlet을 사용 하 여 Lync Phone Edition 구성 설정을 삭제할 수 있습니다. Lync Server 2013 관리 셸에서 또는 Windows PowerShell의 원격 세션에서이 cmdlet을 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-remove-a-specified-collection-of-lync-phone-edition-configuration-settings"></a>Lync Phone Edition 구성 설정의 지정 된 모음을 제거 하려면

  - 이 명령은 Redmond 사이트에 적용 된 UC 전화 구성 설정을 삭제 합니다.
    
        Remove-CsUCPhoneConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-applied-to-the-site-scope"></a>사이트 범위에 적용 된 모든 Lync Phone Edition 구성 설정을 제거 하려면

  - 이 명령은 서비스 범위에 적용 된 모든 UC 전화 구성 설정을 제거 합니다.
    
        Get-CsUCPhoneConfiguration -Filter "site:*" | Remove-CsUCPhoneConfiguration

</div>

<div>

## <a name="to-remove-all-of-the-lync-phone-edition-configuration-settings-where-phone-locking-is-disabled"></a>전화 잠금이 사용 되지 않도록 설정 된 모든 Lync Phone Edition 구성 설정을 제거 하려면

  - 이 명령은 전화 잠금이 사용 되지 않도록 설정 된 모든 UC 전화 구성 설정 모음을 삭제 합니다.
    
        Get-CsUCPhoneConfiguration | Where-Object {$_.EnforcePhoneLock -eq $False} | Remove-CsUCPhoneConfiguration

</div>

자세한 내용은 [제거-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398249(v=OCS.15))를 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

