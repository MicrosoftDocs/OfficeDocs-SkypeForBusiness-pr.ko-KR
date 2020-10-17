---
title: 'Lync Server 2013: 특정 사이트 또는 풀에 대 한 보관을 관리 하기 위한 보관 구성 만들기'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating an Archiving configuration to manage Archiving for specific sites or pools
ms:assetid: c5c864a6-96c7-4bbb-ab7c-61eb1744246c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205251(v=OCS.15)
ms:contentKeyID: 48185361
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faf083627c3a4e422a44f81652e3afeea63ad1ec
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504695"
---
# <a name="creating-an-archiving-configuration-in-lync-server-2013-to-manage-archiving-for-specific-sites-or-pools"></a>Lync Server 2013에서 보관 구성을 만들어 특정 사이트 또는 풀에 대 한 보관 관리

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

Lync Server 2013 제어판에서는 보관 구성을 사용 하 여 배포에서 보관이 구현 되는 방식을 제어할 수 있습니다. 여기에는 다음 보관 구성이 포함됩니다.

  - Lync Server 2013를 배포할 때 기본적으로 만들어지는 글로벌 구성입니다.

  - 보관이 특정 사이트 또는 풀에 구현되는 방식을 지정하는 데 사용하도록 만들 수 있는 사이트 수준 및 풀 수준 구성(선택 사항)

보관을 배포할 때 처음으로 보관 구성을 설정하지만 배포 이후에 구성을 변경, 추가 및 삭제할 수도 있습니다. 지정할 수 있는 옵션 및 보관 구성의 계층 구조를 비롯 하 여 보관 구성이 구현 되는 방식에 대 한 자세한 내용은 계획 설명서, 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하십시오.

<div>


> [!NOTE]  
> 보관을 사용 하려면 외부 통신을 위해 또는 Lync Server 2013에 있는 사용자에 대해 보관 정책을 사용 하도록 설정할지 여부를 지정 하는 보관 정책 구성 해야 합니다. 기본적으로 보관은 내부 또는 외부 통신 중 하나에 대해 사용하지 않도록 설정됩니다. 어느 정책에서든 보관을 사용하도록 설정하려면 이 섹션에 설명된 대로 먼저 배포 환경과 특정 사이트/풀(선택 사항)에 대해 적합한 보관 구성을 지정해야 합니다. 보관을 사용 하는 방법에 대 한 자세한 내용은 배포 설명서의 " <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013에서 보관 정책 구성 및 할당</A> "을 참조 하십시오.<BR>Microsoft Exchange 통합을 사용 하 여 Exchange 2013 서버에 보관 데이터와 파일을 저장 하 고 모든 사용자가 Exchange 2013 서버에 속해 있는 보관을 배포 하는 것을 결정 한 경우에는 토폴로지에서 SQL Server 데이터베이스 구성을 제거 해야 합니다. 토폴로지 작성기를 사용 하 여이 작업을 수행 해야 합니다. 자세한 내용은 작업 설명서에서 <A href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013의 보관 데이터베이스 옵션 변경을</A> 참조 하십시오.



</div>

<div>

## <a name="to-create-an-archiving-configuration-for-a-site-or-pool"></a>사이트 또는 풀의 보관 구성을 만들려면

1.  CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **보관 구성**을 클릭합니다.

4.  **보관 구성** 페이지에서 **새로 만들기**를 클릭하고 다음 중 하나를 수행합니다.
    
      - 사이트 보관 구성을 만들려면 **사이트 구성**을 클릭한 후 **사이트 선택**에서 보관을 구성할 사이트를 선택합니다.
    
      - 풀 보관 구성을 만들려면 **풀 구성**을 클릭한 후 **풀 선택**에서 보관을 구성할 풀을 선택합니다.

5.  **새 보관 설정 만들기**의 **보관 설정** 드롭다운 목록 상자에서 다음 중 하나를 수행합니다.
    
      - 메신저 대화 세션에 대해서만 보관을 사용하도록 설정하려면 **메신저 대화 세션 보관**을 클릭합니다.
    
      - 메신저 대화 세션 및 웹 회의 모두에 대해 보관을 사용하도록 설정하려면 **메신저 대화 및 웹 회의 세션 보관**을 클릭합니다.
    
      - 정책에 대해 보관을 사용하지 않도록 설정하려면 **보관 사용 안 함**을 클릭합니다.

6.  또한 **새 보관 설정**에서 다음을 수행합니다.
    
      - 보관을 사용할 수 없을 경우 작업을 차단하려면 **보관에 실패할 경우 메신저 대화 또는 웹 회의 세션 차단** 확인란을 선택합니다.
    
      - Microsoft Exchange Server를 사용 하 여 보관 데이터를 저장 하려면 **Microsoft exchange 통합** 확인란을 클릭 합니다.
    
      - 데이터 삭제를 사용하도록 설정하려면 **보관 데이터 삭제 사용** 대화 상자를 선택한 후 다음 중 하나를 수행합니다.
        
          - 특정 일 수 이후 삭제되도록 설정하려면 **내보낸 보관 데이터 및 최대 기간(일)이 지난 저장된 보관 데이터 삭제**를 클릭한 다음 일 수를 지정합니다.
        
          - 내보낸 보관 데이터로 삭제를 제한하려면 **내보낸 보관 데이터만 삭제**를 클릭합니다,

7.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="creating-archiving-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 보관 구성 설정 만들기

보관 구성 설정은 Windows PowerShell 및 New-CsArchivingConfiguration cmdlet을 사용 하 여 만들 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 사용 하 여 Microsoft Lync Server 2010 관리"를 참조 [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 하세요.

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-for-a-site"></a>사이트에 대 한 새 보관 구성 설정 컬렉션을 만들려면

  - 다음 명령을 실행하면 레드몬드 사이트에 대해 새 보관 구성 설정 컬렉션이 만들어집니다.
    
        New-CsArchivingConfiguration -Identity "site:Redmond"

</div>

<div>

## <a name="to-create-a-new-collection-of-archiving-configuration-settings-that-only-allow-im-archiving"></a>IM 보관만 허용 하는 새 보관 구성 설정 모음을 만들려면

  - 이전 명령에서 필수 Identity 매개 변수를 제외하고는 지정된 매개 변수가 없으므로 새 구성 설정 컬렉션에는 모든 속성의 기본값이 사용됩니다. 다른 속성 값을 사용하는 설정을 만들려면 간단히 적합한 매개 변수와 매개 변수 값을 포함하면 됩니다. 예를 들어 메신저 대화 세션의 보관을 기본적으로 허용하는 보관 구성 설정 컬렉션을 만들려면 다음과 같은 명령만 사용하면 됩니다.
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"

</div>

<div>

## <a name="to-specify-multiple-property-values-when-creating-archiving-configuration-settings"></a>보관 구성 설정을 만들 때 여러 속성 값을 지정 하려면

  - 여러 매개 변수를 포함하여 여러 속성 값을 수정할 수 있습니다. 예를 들어 다음 명령을 실행하면 메신저 대화 세션을 보관하고 보관 서비스를 사용할 수 없는 메신저 대화는 차단하는 새로운 설정을 구성할 수 있습니다.
    
        New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True

</div>

자세한 내용은 [get-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 보관이 작동 하는 방식](lync-server-2013-how-archiving-works.md)  


[조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

