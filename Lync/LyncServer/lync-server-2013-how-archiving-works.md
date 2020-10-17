---
title: 'Lync Server 2013: 보관 작동 방식'
description: 'Lync Server 2013: 보관이 작동 하는 방식입니다.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How Archiving works
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204900(v=OCS.15)
ms:contentKeyID: 48184174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57a5ef19c0781b4faa279a6aad46ac34b83ae0f9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543384"
---
# <a name="how-archiving-works-in-lync-server-2013"></a>Lync Server 2013에서 보관이 작동 하는 방식

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2014-02-04_

Lync Server 2013 보관은 준수 요구 사항을 충족 하는 데 도움이 되는 옵션을 제공 합니다. 조직의 요구 사항을 가장 효율적으로 충족 하는 방식으로 구현 하 고 유지 관리 하려면 다음 사항을 이해 해야 합니다.

  - 보관할 수 있는 정보

  - 사용자의 배포 환경에서 보관을 설정하고 해제하는 방법

  - 보관의 구현 방법을 제어하기 위해 구성할 수 있는 보관 옵션

<div>

## <a name="what-information-can-be-archived"></a>보관할 수 있는 정보

보관할 수 있는 콘텐츠 형식은 다음과 같습니다.

  - 피어 투 피어 인스턴트 메시지

  - 단체 인스턴트 메시지인 회의(모임)

  - 업로드된 콘텐츠(예: 참고 파일) 및 이벤트 관련 콘텐츠(예: 입장, 퇴장, 업로드 공유 및 표시 여부 변경)를 비롯한 회의 콘텐츠

  - 회의 중 공유된 화이트보드 및 설문

보관되지 않는 콘텐츠 형식은 다음과 같습니다.

  - 피어 투 피어 파일 전송

  - 피어 투 피어 인스턴스 메시지 및 회의에 대한 오디오/비디오

  - 피어 투 피어 인스턴스 메시지 및 회의에 대한 데스크톱 및 응용 프로그램 공유

또한 Lync Server에서는 영구 채팅 대화를 보관 하지 않습니다. 영구 채팅 대화를 보관 하려면 Microsoft Lync Server 2013, 영구 채팅 서버를 사용 하 여 배포할 수 있는 구성 요소인 준수 서비스를 사용 하도록 설정 하 고 구성 해야 합니다. 자세한 내용은 계획 설명서에서 [Lync server 2013의 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md) 을 참조 하십시오.

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a>보관 사용을 시작하는 방법

보관은 서버를 배포할 때 각 프런트 엔드 서버에 자동으로 설치되지만 사용자가 구성하기 전까지는 사용하도록 설정되지 않습니다. 구성 방법은 보관의 배포 방법에 따라 결정됩니다.

  - **Microsoft Exchange 통합을 사용 하 여 보관** Exchange 2013에 있는 사용자가 있고 해당 사서함이 보존 In-Place 있는 경우 Lync Server 2013 storage with Exchange storage를 통합 하는 옵션을 선택할 수 있습니다. Microsoft Exchange 통합 옵션을 선택 하는 경우 Exchange 2013 정책 및 구성을 사용 하 여 해당 사용자에 대 한 Lync Server 2013 데이터 보관을 제어 합니다.

  - **Lync Server 보관 데이터베이스를 사용 하 여 보관** Exchange 2013에 있지 않거나 사서함이 보존 In-Place에 포함 되지 않은 사용자가 있거나, 배포 환경의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하지 않으려는 경우 또는 해당 사용자에 대 한 보관 데이터를 저장 하기 위해 SQL Server를 사용 하 여 Lync Server 보관 데이터베이스를 배포할 수 있습니다. 이 경우 Lync Server 2013 보관 정책 및 구성에서는 보관이 사용 되는지 여부와이를 구현 하는 방법을 결정 합니다. Lync Server 2013을 사용 하려면 적절 한 SQL Server 데이터베이스를 토폴로지에 추가 하 고 토폴로지를 게시 해야 합니다.

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a>Microsoft Exchange 통합을 사용 하는 경우 보관 설정

사용자가 Exchange 2013에 있고 해당 사서함이 보존 In-Place에 있는 경우에는이 섹션 뒷부분에서 설명 하는 **Microsoft Exchange 통합** 옵션을 선택 하 여 해당 사용자에 대 한 lync server 2013를 보관 한 다음 Exchange In-Place 보류 정책 및 설정을 지정 하 여 해당 사용자에 대 한 보관을 제어할 수 있으며, Lync server 구성을 통해 다음을 제어할 수도 있습니다.

  - IM이나 회의 내용 또는 두 가지를 모두 보관할지 여부

  - Lync Server 배포에 대해 중요 모드를 구현할지 여부

  - Microsoft Exchange 통합 옵션을 선택한 후 보관 된 데이터를 저장 하는 데 Exchange 2013을 사용 합니다.

이러한 Lync Server 2013 보관 구성 옵션에 대해서는이 섹션 뒷부분에서 설명 합니다. 보관을 지원 하기 위해 Exchange In-Place 보류 정책 및 설정을 구성 하는 방법에 대 한 자세한 내용은 Exchange 2013 제품 설명서를 참조 하십시오.

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a>Lync Server 보관 데이터베이스 저장소를 사용할 경우의 보관 설정

SQL Server 데이터베이스를 사용 하 여 Lync Server 보관 데이터베이스를 사용 하 여 배포의 모든 사용자에 대 한 데이터를 보관 하려면 해당 사용자에 대해 보관을 사용 하도록 설정할지 여부를 제어 하는 Lync Server 보관 정책을 구성 하면 됩니다. 각 보관 정책에서는 다음 두 항목 중 하나 또는 모두에 대해 보관을 사용하거나 사용하지 않도록 설정할 수 있습니다.

  - 내부 통신

  - 외부 통신

기본적으로 모든 Lync Server 보관 정책의 내부 통신 또는 외부 통신에 대해 보관을 사용 하도록 설정 되지 않습니다. Lync server 2013 제어판 또는 Lync Server 2013 관리 셸에서 cmdlet을 사용 하 여 통신을 사용 하거나 사용 하지 않도록 설정 합니다.

Lync Server 2013 보관 정책에는 다음이 포함 됩니다.

  - **전역 보관 정책**. 기본 보관 정책이며 전체 배포에 적용됩니다. 이 기능은 Lync Server 2013를 배포할 때 만들어지며 기본적으로 내부 및 외부 통신 모두에 대해 보관을 사용 하지 않도록 설정 합니다. 이 정책은 삭제할 수 없습니다. 삭제 옵션을 선택하더라도 글로벌 정책은 기본 설정으로 다시 설정됩니다.

  - **사이트 보관 정책**. 선택적으로 사이트에 대한 사이트 수준의 보관 정책을 만들고 구성해서 하나 이상의 특정 사이트에 대해 보관을 사용하거나 사용하지 않도록 설정할 수 있습니다. 사이트 수준의 보관 정책을 만들 때는 기본적으로 보관이 사용하지 않도록 설정됩니다. 자신이 만든 사이트 수준의 보관 정책은 삭제할 수 있습니다. 사이트 수준의 보관 정책은 글로벌 정책을 무시하지만 해당 정책에 지정된 사이트로만 제한됩니다. 예를 들어 글로벌 정책에서 내부 및 외부 통신에 대한 보관을 사용하도록 설정하고 외부 통신에 대한 보관을 사용하지 않도록 설정하는 사이트 정책을 만들었다면 해당 사이트에 대해서는 내부 통신만 보관됩니다.

  - **사용자 보관 정책**. 선택적으로 지정된 사용자 및 사용자 그룹에 대해 사용자 수준의 보관 정책을 만들고, 구성 및 적용하여 하나 이상의 특정 사용자 및 사용자 그룹에 대해 보관을 사용하거나 사용하지 않도록 설정할 수 있습니다. 사용자 수준의 보관 정책을 만들 때는 기본적으로 보관이 사용하지 않도록 설정됩니다. 자신이 만드는 사용자 수준의 보관 정책은 삭제할 수 있으며 해당 보관 정책이 적용되는 사용자 및 사용자 그룹을 변경할 수 있습니다. 사용자 수준의 보관 정책은 글로벌 정책 및 모든 사이트 정책을 무시하지만 해당 정책이 적용되는 사용자 및 사용자 그룹으로만 제한됩니다. 예를 들어 글로벌 정책에서 내부 및 외부 통신에 대한 보관을 사용하지 않도록 설정하고, 내부 및 외부 통신에 대한 보관을 사용하도록 설정하는 사이트 수준의 정책을 만들고, 다시 외부 통신에 대한 보관을 사용하지 않도록 설정하는 사용자 수준의 정책을 만들었다면 사용자 수준의 정책이 적용되는 사용자의 경우 내부 통신만 보관되고 이를 제외한 모든 사이트 사용자에 대해서는 외부 및 내부 통신이 모두 보관됩니다.

보관을 배포할 때 초기 보관 정책을 설정 하는 방법에 대 한 자세한 내용은 배포 설명서의 " [Lync Server 2013에서 보관 정책 구성 및 할당](lync-server-2013-configuring-and-assigning-archiving-policies.md) "을 참조 하십시오. 배포 후 보관 정책을 사용 하 여 통신을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 작업 설명서에서 [Lync Server 2013의 내부 및 외부 통신 보관 관리](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) 를 참조 하세요.

<div>


> [!NOTE]  
> Lync Server 2013 보관 데이터베이스를 모두 구현 하 고 Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange 2013 정책은 Exchange 2013에 있는 사용자에 한 해 해당 사서함을 In-Place 보류 상태로 유지 한 상태에서 Lync Server 보관 정책을 재정의 합니다. Lync 보관은 Microsoft Exchange In-Place 보류 정책만 따릅니다.



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a>보관 구성을 위한 옵션

정책을 사용하고 보관을 사용 및 사용하지 않도록 설정하는 것 외에도 전체 배포에 대해 그리고 선택적으로 특정 사이트 및 풀에 대해 구성할 수 있는 보관 옵션이 있습니다. Lync Server 2013 제어판에서 사용할 수 있는 하나 이상의 보관 구성을 사용 하 여 대부분의 보관 옵션을 제어 하지만 Lync Server 2013 관리 셸을 사용 하 여 구성에만 사용할 수 있는 다른 옵션도 있습니다.

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a>Lync Server 2013 제어판에서 제공되는 보관 구성 옵션

각 보관 구성은 다음과 같은 옵션을 제공합니다.

전역 수준의 구성은 보관을 배포할 때 자동으로 만들어지며, 사용자가 구성할 수 있지만 삭제할 수는 없습니다. 전역 구성을 삭제하도록 옵션을 선택해도 설정이 기본값으로 다시 설정됩니다. 전역 구성과 함께 보관 설정을 제어하는 사이트 및 풀 구성은 여러 개 만들 수 있습니다. 전역 구성과 각 사이트 및 풀 구성에서는 다음과 같은 옵션이 제공됩니다.

  - 보관을 사용하지 않도록 설정하거나, IM(인스턴트 메시징)에 대해서만 보관을 사용하도록 설정하거나, IM 및 회의 모두 보관을 사용하도록 설정합니다.

  - Lync Server 오류가 발생 하는 경우 IM 및 회의 세션을 차단 하도록 중요 모드를 구성 합니다. 오류에는 다음 항목들이 포함됩니다.
    
      - **IM**. Lync Server 저장소 서비스에 문제가 있습니다. 이 경우 보관을 사용하도록 설정된 사용자의 IM이 차단됩니다.
    
      - **회의**. 오류는 사용할 수 없는 파일 공유이거나 저장소 서비스 관련 문제일 수 있습니다. 이 경우 오류 시점에 풀에 호스팅된 모든 활성 회의가 제한 모드로 전환되고 새로운 회의를 활성화할 수 없습니다.
    
    오류가 수정된 다음에는 IM 및 회의 모두 자동으로 복구됩니다.

  - Lync Server 2013 보관 데이터를 저장 하기 위해 별도의 SQL Server 데이터베이스를 설정 하는 대신 Microsoft Exchange Server 2013 통합을 사용 하 여 보관 된 데이터를 저장할 수 있도록 Exchange 2013를 사용 하도록 지정 합니다.

  - 보관된 데이터의 삭제 옵션을 구성합니다. 여기에는 다음 두 가지 중 하나일 수 있는 보관된 데이터를 삭제할 시간 지정이 포함됩니다.
    
      - 지정한 특정 일 수 이후
    
      - 보관 데이터를 내보낸 후에 (Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange로 업로드 된 데이터 포함)
    
    <div>
    

    > [!NOTE]  
    > Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange 2013에 있는 사용자에 대해 삭제 하 고 해당 사서함을 포함 하는 In-Place는 Exchange에서 제어 합니다. 유일한 자격 증명은 Lync Server 파일 공유에 저장 되는 회의 파일에 대 한 것입니다. 이러한 파일은 보관 데이터를 내보낸 후 데이터를 삭제하는 옵션을 선택하는 경우에는 파일을 내보내 해당 파일이 Exchange에 업로드된 후에, 그리고 최대 보존 기간(일)을 지정하는 경우에는 지정된 최대 기간(일) 후에 파일 공유에서 삭제됩니다.

    
    </div>

기본적으로는 모든 보관 옵션이 사용하지 않도록 설정됩니다. Lync Server 2013 제어판을 사용 하 여 보관 구성을 관리할 수 있습니다.

다음 보관 구성을 지정할 수 있습니다.

  - **전역 보관 구성**. 이 구성은 기본 보관 구성이며 전체 배포에 적용됩니다. 이 도구는 Lync Server 2013를 배포할 때 만들어지며 기본적으로 보관 기능을 사용 하도록 설정 하지 않습니다. 전역 구성은 수정할 수 있지만 삭제할 수 없습니다. 구성에 대한 삭제 옵션을 선택해도 전역 구성이 기본 설정으로 다시 설정됩니다.

  - **사이트 보관 구성**. 선택적으로 개별 사이트에 대해 사이트 수준의 보관 구성을 만들고 구성하여 하나 이상의 특정 사이트에 대한 보관을 구성할 수 있습니다. 사이트 수준의 보관 구성은 사용자가 만들 때만 존재합니다. 사이트 수준의 보관 구성은 수정하거나 삭제할 수 있습니다. 사이트 수준의 보관 구성은 전역 구성을 무시하지만 해당 사이트 수준의 구성에 지정된 사이트로만 제한됩니다. 예를 들어 전역 구성에서 IM에 대해서만 보관을 사용하도록 설정하고 IM 및 회의 모두에 대해 보관을 사용하도록 설정하는 사이트 구성을 만들었다면 조직 전체가 아니라 해당 사이트에 대해서만 회의 내용이 보관됩니다.

  - **풀 보관 구성**. 선택적으로 개별 풀에 대해 풀 수준의 구성을 만들고 구성하여 하나 이상의 특정 풀에 대한 보관 설정을 지정할 수 있습니다. 풀 수준의 보관 구성은 사용자가 만들 때만 존재합니다. 풀 수준의 보관 구성은 수정 및 삭제할 수 있습니다. 풀 수준의 보관 구성은 전역 구성 및 사용자가 만들었을 수 있는 모든 사이트 보관 구성을 무시합니다. 예를 들어 전역 구성에서 IM에 대해서만 보관을 사용하도록 설정하고, 특정 사이트에 대해 IM 및 회의 모두 보관을 사용하도록 설정하는 사이트 수준의 구성을 만들고, IM에 대해서만 보관을 사용하도록 설정하는 풀 수준의 구성을 만들었으면 풀 수준 구성에 지정된 풀에 있는 사용자를 제외하고 해당 사이트의 모든 사용자에 대해 IM과 회의 내용 모두 통신이 보관됩니다. 조직 내 다른 모든 사용자의 경우에는 IM에 대해서만 보관이 사용하도록 설정됩니다.

보관을 배포할 때 초기 보관 구성을 설정 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 보관 옵션 구성을](lync-server-2013-configuring-archiving-options.md) 참조 하십시오. 보관 정책을 사용 하 여 배포 후에 통신을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 작업 설명서에서 [조직, 사이트 및 풀에 대해 Lync Server 2013의 보관 구성 옵션 관리](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) 를 참조 하십시오.

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a>Windows PowerShell에서만 사용 가능한 보관 옵션

Lync Server 2013 관리 셸을 사용 하 여 cmdlet을 사용 하 여 Lync Server 2013 제어판에서는 사용할 수 없는 옵션을 구현할 수 있습니다. 이러한 옵션은 다음과 같습니다.

  - **중복 메시지 보관**. 자세한 내용은 작업 설명서에서 [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) 및 [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration)을 참조하십시오.

  - **보관된 데이터 내보내기**. 자세한 내용은 [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)를 참조하십시오.

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a>보관된 데이터에 액세스하는 방법

보관된 데이터에 대한 액세스는 데이터가 저장된 위치에 따라 달라집니다.

  - **Microsoft Exchange 저장소** Exchange 통합 옵션을 선택 하면 Lync Server는 exchange 2013에 있는 모든 사용자의 Exchange 2013 저장소에 있는 보관 콘텐츠를 저축금과 해당 사서함이 보류 된 In-Place 보존 합니다. 보관 된 데이터는 사용자에 게 표시 되지 않으며 Exchange **검색 관리** 역할을 가진 사용자만 검색할 수 있도록 하는 User 사서함 복구 가능한 항목 폴더에 저장 됩니다. Exchange에서는 연결 된 검색 및 검색과 SharePoint (배포 된 경우)를 함께 사용 하도록 설정 합니다. Exchange에 저장 된 데이터의 저장, 보존 및 검색에 대 한 자세한 내용은 Exchange 2013 및 SharePoint 설명서를 참조 하세요.

  - **Lync Server 저장소**. Lync server 데이터 저장용 lync server 2013 보관 데이터베이스를 설정 하는 경우 lync Server 저축금과는 Exchange 2013에 포함 되지 않은 사용자에 대 한 Lync Server 보관 데이터베이스 (SQL Server 데이터베이스)의 콘텐츠를 보관 하 고 사서함을 In-Place 보류 상태로 두지 않은 상태를 유지 합니다. 이 데이터는 검색할 수 없지만 다른 도구를 사용해서 검색할 수 있는 형식으로 내보낼 수 있습니다. 보관 데이터베이스에 저장 된 데이터를 내보내는 방법에 대 한 자세한 내용은 작업 설명서에서 [Lync Server 2013에서 보관 된 데이터 내보내기를](lync-server-2013-exporting-archived-data.md) 참조 하십시오.

Lync Server 2013 및 Exchange 2013가 함께 작동 하는 방식에 대 한 자세한 내용은 지원 가능성 설명서에서 [Lync server 2013의 Exchange server 및 SharePoint 통합 지원](lync-server-2013-exchange-and-sharepoint-integration-support.md) (영문)을 참조 하십시오.

</div>

</div>

<span> </span>

</div>

</div>

</div>

