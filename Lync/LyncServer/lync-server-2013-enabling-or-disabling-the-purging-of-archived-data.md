---
title: 'Lync Server 2013: 보관 된 데이터의 삭제를 사용 하거나 사용 하지 않도록 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling the purging of archived data
ms:assetid: 28cef09f-0970-4fc3-8315-f26689e3e187
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520968(v=OCS.15)
ms:contentKeyID: 48183678
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e62ff615b4e2fcf5ec10f470993f985db0363a4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-the-purging-of-archived-data-in-lync-server-2013"></a>Lync Server 2013에서 보관 된 데이터의 삭제를 사용 하거나 사용 하지 않도록 설정

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

Lync Server 2013 제어판에서는 보관 구성을 사용 하 여 삭제를 사용 하거나 사용 하지 않도록 설정 하 고 제거가 구현 되는 방식을 구성 합니다. 여기에는 다음 보관 구성이 포함됩니다.

  - Lync Server 2013를 배포할 때 기본적으로 만들어지는 글로벌 구성입니다.

  - 보관이 특정 사이트 또는 풀에 구현되는 방식을 지정하는 데 사용하도록 만들 수 있는 사이트 수준 및 풀 수준 구성(선택 사항)

보관을 배포할 때 처음으로 보관 구성을 설정하지만 배포 이후에 구성을 변경, 추가 및 삭제할 수도 있습니다. 지정할 수 있는 옵션 및 보관 구성의 계층 구조를 비롯 하 여 보관 구성이 구현 되는 방식에 대 한 자세한 내용은 계획 설명서, 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하십시오.

<div>


> [!NOTE]  
> Lync Server 2013에 있는 사용자에 대해 보관을 사용 하려면 보관 정책을 구성 하 여 내부 통신, 외부 통신 또는 둘 모두에 대해 보관을 사용 하도록 설정할지 여부를 지정 해야 합니다. 기본적으로는 내부 또는 외부 통신에 대해 보관이 사용하도록 설정되지 않습니다. 정책에서 보관을 사용하도록 설정하기 전에 이 섹션에 설명된 대로 배포와 특정 사이트 및 풀(선택 사항)에 적합한 보관 구성을 지정해야 합니다. 보관을 사용 하는 방법에 대 한 자세한 내용은 배포 설명서의 " <A href="lync-server-2013-configuring-and-assigning-archiving-policies.md">Lync Server 2013에서 보관 정책 구성 및 할당</A> "을 참조 하십시오.<BR>Microsoft Exchange 통합을 사용 하 여 Exchange 2013 서버에 보관 데이터와 파일을 저장 하 고 모든 사용자가 Exchange 2013 서버에 있는 보관을 배포 하는 것을 결정 한 경우 SQL Server 데이터베이스 구성을 제거 해야 합니다. 토폴로지에서 토폴로지 작성기를 사용 하 여이 작업을 수행 해야 합니다. 자세한 내용은 작업 설명서에서 <A href="lync-server-2013-changing-archiving-database-options.md">Lync Server 2013의 보관 데이터베이스 옵션 변경을</A> 참조 하십시오.



</div>

<div>

## <a name="to-enable-or-disable-purging-for-archiving"></a>보관 삭제를 사용하거나 사용하지 않도록 설정하려면

1.  CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.

2.  브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 제어판을 엽니다. Lync Server 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.

3.  왼쪽 탐색 모음에서 **모니터링 및 보관**을 클릭하고 **보관 구성**을 클릭합니다.

4.  보관 구성 목록에서 적절한 전역, 사이트 또는 풀 구성의 이름을 클릭하고 **편집**을 클릭한 후에 **자세한 정보 표시**를 클릭하고 다음을 수행합니다.
    
      - 삭제를 사용하도록 설정하려면 **보관 데이터 삭제 사용** 확인란을 선택하고 다음 중 하나를 수행합니다.
        
          - 모든 레코드를 삭제하려면 **내보낸 보관 데이터 및 최대 기간(일)이 지난 저장된 보관 데이터 삭제**를 클릭하고 기간(일)을 지정합니다.
        
          - 내보낸 데이터만 삭제하려면 **내보낸 보관 데이터만 삭제**를 클릭합니다.
    
      - 삭제를 사용하지 않도록 설정하려면 **보관 데이터 삭제 사용** 확인란 선택을 취소합니다.

5.  **커밋**을 클릭합니다.

</div>

<div>

## <a name="enabling-or-disabling-the-purging-of-archiving-data-by-using-windows-powershell-cmdlets"></a>Windows PowerShell Cmdlet을 사용 하 여 보관 데이터 삭제를 사용 하거나 사용 하지 않도록 설정

Windows PowerShell 및 **get-csarchivingconfiguration** cmdlet을 사용 하 여 보관 데이터의 자동 삭제를 사용 하거나 사용 하지 않도록 설정할 수 있습니다. 이 cmdlet은 Lync Server 2013 관리 셸 또는 Windows PowerShell의 원격 세션에서 실행할 수 있습니다. 원격 Windows PowerShell을 사용 하 여 Lync Server에 연결 하는 방법에 대 한 자세한 내용은 Lync Server Windows PowerShell 블로그 문서 "빠른 시작: 원격 PowerShell을 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)사용 하 여 Microsoft Lync Server 2010 관리"를 참조 하세요.

<div>

## <a name="to-enable-the-purging-of-all-archiving-data"></a>모든 보관 데이터를 삭제할 수 있도록 설정 하려면

  - 모든 보관 데이터의 삭제를 사용하도록 설정하려면 **EnablePurging** 속성을 true($True)로 설정합니다. 예시는 다음과 같습니다:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True
    
    이 명령을 실행 한 후 모든 Lync Server는 **KeepArchivingDataForDays** 속성에 지정한 값 보다 오래 된 모든 보관 레코드를 제거 합니다.

</div>

<div>

## <a name="to-enable-the-purging-only-of-exported-archiving-data"></a>내보낸 보관 데이터만 삭제할 수 있도록 설정 하려면

  - [Export-csarchivingdata](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet을 사용 하 여 데이터 파일로 내보낸 보관 레코드에 대 한 삭제를 제한 하려면 PurgeExportedArchivesOnly 속성을 True ($True)로도 설정 해야 합니다. 예시는 다음과 같습니다:
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $True -PurgeExportedArchivesOnly $True
    
    이 명령을 실행 한 후에는 Lync Server에서 두 가지 조건을 충족 하는 보관 레코드만 삭제 하 고 1) **KeepArchivingDataForDays** 속성에 지정 된 값 보다 오래 되었습니다. 그리고 2) **export-csarchivingdata** cmdlet을 사용 하 여 내보낸 것입니다.

</div>

<div>

## <a name="to-disable-the-purging-of-all-archiving-data"></a>모든 보관 데이터의 삭제를 사용 하지 않도록 설정 하려면

  - 보관 레코드의 자동 삭제를 사용하지 않도록 설정하려면 **EnablePurging** 속성을 False($False)로 설정합니다. 예를 들면 다음과 같습니다.
    
        Set-CsArchivingConfiguration -Identity "site:Redmond" -EnablePurging $False

</div>

보관 데이터를 제거 하기 위한 추가 옵션을 비롯 한 자세한 내용은 [get-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) cmdlet에 대 한 도움말 항목을 참조 하십시오.

</div>

<div>

## <a name="see-also"></a>참고 항목


[Lync Server 2013에서 보관이 작동 하는 방식](lync-server-2013-how-archiving-works.md)  


[Lync Server 2013에서 보관 정책 구성 및 할당](lync-server-2013-configuring-and-assigning-archiving-policies.md)  
[조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

