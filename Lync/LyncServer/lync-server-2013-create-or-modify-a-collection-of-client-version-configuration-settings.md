---
title: 클라이언트 버전 구성 설정 모음 만들기 또는 수정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of client version configuration settings
ms:assetid: 4e6faffd-a36f-40f1-8734-78d84b7df921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ898477(v=OCS.15)
ms:contentKeyID: 50873757
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6851a332b0b2c33d769328a0656f206d5f7d271c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180115"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-client-version-configuration-settings-in-lync-server-2013"></a>Lync Server 2013에서 클라이언트 버전 구성 설정 모음 만들기 또는 수정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

클라이언트 버전 구성 설정은 클라이언트 버전 제어를 설정하거나 해제하는 데 사용됩니다. 전역 클라이언트 버전 구성은 Lync Server를 사용 하 여 설치 되며, 전체 서버 배포에 대해 클라이언트 버전 제어를 사용 하거나 사용 하지 않도록 설정 하는 데 사용 됩니다. 개별 사이트에 대 한 클라이언트 버전 구성 설정을 구성할 수도 있습니다. Lync Server 2013 제어판 또는 Lync Server 2013 관리 셸에서 클라이언트 버전 구성 설정을 만들거나 수정할 수 있습니다.

<div>


> [!NOTE]
> 익명 사용자는 사용자, 사이트 또는 서비스와 연결되지 않으므로 전역 수준 정책에만 영향을 받습니다.



</div>

<div>

## <a name="to-create-or-modify-client-version-configuration-settings-by-using-lync-server-control-panel"></a>Lync Server 제어판을 사용 하 여 클라이언트 버전 구성 설정을 만들거나 수정 하려면

1.  CsUserAdministrator 역할 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **클라이언트**를 클릭 하 고 **클라이언트 버전 구성** 탐색 단추를 클릭 합니다.

4.  **클라이언트 버전 구성** 페이지에서 다음을 수행 합니다.
    
      - 새 구성을 만들려면 **새로**만들기를 클릭 하 고 사이트를 선택한 다음 **확인** 이름을 클릭 하 고 설정을 업데이트 합니다.
    
      - 구성을 수정 하려면 구성을 선택 하 고 **편집**을 클릭 한 다음 **자세한 정보 표시**를 클릭 하 고 설정을 변경 합니다.

</div>

<div>

## <a name="creating-or-modifying-client-version-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 클라이언트 버전 구성 설정 만들기 또는 수정

**새-csclientversionconfiguration** cmdlet을 사용 하 여 클라이언트 버전 구성 설정을 만든 후에는 **csclientversionconfiguration** cmdlet을 사용 하 여 수정할 수 있습니다. 이러한 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-create-a-new-collection-of-client-version-configuration-settings"></a>클라이언트 버전 구성 설정의 새 컬렉션을 만들려면

  - 다음 명령은 Redmond 사이트에 적용 된 클라이언트 버전 구성 설정의 새 컬렉션을 만듭니다. 이 예에서는 Redmond 사이트에 대해 클라이언트 버전 관리를 사용 하지 않도록 설정 합니다.
    
        New-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $False

</div>

<div>

## <a name="to-enable-client-versioning-for-a-site"></a>사이트에 대해 클라이언트 버전 관리를 사용 하도록 설정 하려면

  - 이 명령은 Redmond 사이트에 대 한 클라이언트 버전 관리를 사용 하도록 설정 합니다.
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -Enabled $True

</div>

<div>

## <a name="to-disable-client-versioning-throughout-the-organization"></a>조직 전체에서 클라이언트 버전 관리를 사용 하지 않도록 설정 하려면

  - 이 예에서는 조직에서 사용 중인 모든 클라이언트 버전 구성 설정에 대해 클라이언트 버전 관리를 사용 하지 않도록 설정 합니다.
    
        Get-CsClientVersionConfiguration | Set-CsClientVersionConfiguration  -Enabled $False

</div>

자세한 내용은 [새-csclientversionconfiguration](https://technet.microsoft.com/library/Gg399029(v=OCS.15)) 및 [csclientversionconfiguration](https://technet.microsoft.com/library/Gg398623(v=OCS.15)) Cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

