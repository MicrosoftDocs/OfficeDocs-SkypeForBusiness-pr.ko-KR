---
title: 'Lync Server 2013: 보관 방식'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: How Archiving works
ms:assetid: 536a52a9-cfb7-4392-9620-ffc5b319b31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204900(v=OCS.15)
ms:contentKeyID: 48184174
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 097b40ef4194a618c090e0d67f73583d6aa427b3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985230"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-archiving-works-in-lync-server-2013"></a>Lync Server 2013에서 보관 하는 방식

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2014-02-04_

Lync Server 2013 보관은 준수 요구 사항을 충족 하는 데 도움이 되는 옵션을 제공 합니다. 조직의 요구 사항을 가장 효과적으로 충족 하는 방식으로 구현 하 고 유지 관리 하려면 다음 사항을 이해 해야 합니다.

  - 보관할 수 있는 정보

  - 배포에서 보관을 사용 하거나 사용 하지 않도록 설정 하는 방법

  - 보관을 구현 하는 방법을 제어 하기 위해 구성할 수 있는 보관 옵션입니다.

<div>

## <a name="what-information-can-be-archived"></a>보관할 수 있는 정보

다음 콘텐츠 형식을 보관할 수 있습니다.

  - 피어 투 피어 인스턴트 메시지

  - 회의 (모임)-단체 인스턴트 메시지

  - 업로드 된 콘텐츠 (예: 유인물) 및 이벤트 관련 콘텐츠 (예: 참가, 종료, 공유 업로드, 표시 유형 변경)를 포함 한 컨퍼런스 콘텐츠

  - 회의 중에 화이트 보드 및 설문 조사 공유

다음과 같은 유형의 콘텐츠는 보관 되지 않습니다.

  - 피어 투 피어 파일 전송

  - 피어 투 피어 인스턴트 메시지 및 회의를 위한 오디오/비디오

  - 피어 투 피어 인스턴트 메시지 및 회의를 위한 데스크톱 및 응용 프로그램 공유

또한 Lync 서버는 영구 채팅 대화를 보관 하지 않습니다. 영구 채팅 대화를 보관 하려면 Microsoft Lync Server 2013, 영구 채팅 서버를 사용 하 여 배포할 수 있는 구성 요소인 준수 서비스를 사용 하도록 설정 하 고 구성 해야 합니다. 자세한 내용은 계획 설명서의 [Lync Server 2013에서 영구 채팅 서버 계획](lync-server-2013-planning-for-persistent-chat-server.md) 을 참조 하세요.

</div>

<div>

## <a name="how-do-i-start-using-archiving"></a>보관 사용을 시작 하려면 어떻게 하나요?

서버를 배포할 때 각 프런트 엔드 서버에 보관이 자동으로 설치 되지만 보관은 구성할 때까지 사용할 수 없습니다. 이를 구성 하는 방법은 보관을 배포 하는 방법에 따라 결정 됩니다.

  - **Microsoft Exchange 통합을 사용 하 여 보관** Exchange 2013에 속한 사용자와 사서함이 원본 위치 유지에 저장 되어 있는 경우 Lync Server 2013 저장소를 Exchange 저장소와 통합 하는 옵션을 선택할 수 있습니다. Microsoft Exchange 통합 옵션을 선택 하는 경우 Exchange 2013 정책 및 구성을 사용 하 여 해당 사용자를 위한 Lync Server 2013 데이터 보관을 제어 합니다.

  - **Lync Server 보관 데이터베이스를 사용 하 여 보관** Exchange 2013 또는 사서함이 원본 위치 유지에 있지 않은 사용자가 있거나 배포의 모든 사용자에 대해 Microsoft Exchange 통합을 사용 하지 않으려는 경우에는 SQL Server를 사용 하 여 Lync Server 보관 데이터베이스를 배포할 수 있습니다.  해당 사용자에 대 한 보관 데이터를 저장 합니다. 이 경우 Lync Server 2013 보관 정책 및 구성에서 보관을 사용할지 여부와 구현 방법을 결정 합니다. Lync Server 2013을 사용 하려면 적절 한 SQL Server 데이터베이스를 토폴로지에 추가 하 고 토폴로지를 게시 해야 합니다.

<div>

## <a name="archiving-setup-when-using-microsoft-exchange-integration"></a>Microsoft Exchange 통합을 사용 하는 경우 보관 설정

사용자가 Exchange 2013에 있고 해당 사서함이 원본 위치 유지에 저장 되어 있는 경우이 섹션의 뒷부분에 설명 된 **Microsoft Exchange 통합** 옵션을 선택 하 여 해당 사용자에 대 한 Lync server 2013을 보관 한 다음 Exchange 원본 위치 유지 정책 및 설정을 지정 하 고 Lync server 구성을 사용 하 여 다음을 제어 하는 방법으로 해당 사용자의 보관을 제어할 수 있습니다.

  - IM, 회의 또는 두 가지 모두 보관 여부

  - Lync 서버 배포에 대해 중요 한 모드를 구현할지 여부

  - Microsoft Exchange 통합 옵션을 선택 하 여 보관 된 데이터 저장소에 Exchange 2013을 사용 합니다.

이러한 Lync Server 2013 보관 구성 옵션은이 섹션의 뒷부분에서 설명 합니다. 보관을 지원 하도록 Exchange 원본 위치 유지 정책 및 설정을 구성 하는 방법에 대 한 자세한 내용은 Exchange 2013 제품 설명서를 참조 하세요.

</div>

<div>

## <a name="archiving-setup-when-using-lync-server-archiving-database-storage"></a>Lync Server 보관 데이터베이스 저장소를 사용할 때의 보관 설정

SQL Server 데이터베이스를 사용 하 여 Lync Server 보관 데이터베이스를 사용 하 여 배포의 모든 사용자에 대 한 데이터를 보관 하려면 해당 사용자에 대해 보관을 사용할 수 있는지 여부를 제어 하는 Lync Server 보관 정책을 구성 하면 됩니다. 각 보관 정책에서 다음 중 하나 또는 모두에 대해 보관을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.

  - 내부 통신

  - 외부 통신

기본적으로 Lync Server 보관 정책의 내부 통신 또는 외부 통신에 대해 보관을 사용할 수 없습니다. Lync server 2013 제어판 또는 Lync Server 2013 관리 셸에서 cmdlet을 사용 하 여 통신을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.

Lync Server 2013 보관 정책에는 다음이 포함 됩니다.

  - **전역 보관 정책**. 기본 보관 정책으로, 전체 배포에 적용 됩니다. Lync Server 2013을 배포할 때 만들어지고 기본적으로 내부 및 외부 통신 모두에 대 한 보관을 사용 하지 않도록 설정 합니다. 이 정책은 삭제할 수 없습니다. 삭제 옵션을 선택 하면 전역 정책이 기본 설정으로 다시 설정 됩니다.

  - **사이트 보관 정책**. 필요에 따라 사이트에 대 한 사이트 수준 보관 정책을 만들어 구성 하 여 하나 이상의 특정 사이트에 대해 보관을 사용 하거나 사용 하지 않도록 설정할 수 있습니다. 사이트 수준 보관 정책을 만드는 경우 기본적으로 보관을 사용할 수 없습니다. 만든 사이트 수준의 보관 정책을 삭제할 수 있습니다. 사이트 수준 보관 정책은 정책에 지정 된 사이트에 대해서만 전역 정책에 우선 합니다. 예를 들어 글로벌 정책에서 내부 및 외부 통신에 대해 보관을 사용 하도록 설정 하 고 외부 통신에 대 한 보관을 사용 하지 않도록 설정 하는 사이트 정책을 만들면 해당 사이트에 대 한 내부 통신만 보관 됩니다.

  - **사용자 아카이빙 정책**. 필요한 경우 지정 된 사용자 및 사용자 그룹에 대해 사용자 수준 보관 정책을 만들고, 구성 하 고, 적용 하 여 하나 이상의 특정 사용자 및 사용자 그룹에 대해 보관을 사용 하거나 사용 하지 않도록 설정할 수 있습니다. 사용자 수준 보관 정책을 만드는 경우 기본적으로 보관을 사용할 수 없습니다. 만드는 모든 사용자 수준 보관 정책을 삭제할 수 있으며, 보관 정책이 적용 되는 사용자와 사용자 그룹을 변경할 수 있습니다. 사용자 수준 보관 정책은 정책이 적용 되는 사용자 및 사용자 그룹에 대해서만 전역 정책과 모든 사이트 정책을 재정의 합니다. 예를 들어 전역 정책에서 내부 및 외부 통신에 대 한 보관을 사용 하지 않도록 설정 하는 경우 내부 및 외부 통신에 대 한 보관을 사용 하도록 설정한 사이트 수준 정책을 만든 다음 사용 하지 않도록 설정 하는 사용자 수준 정책을 만듭니다. 외부 통신 보관을 위해 통신은 사용자 수준 정책을 적용 하는 사용자에 게는 내부 통신만 보관 되므로 모든 사이트 사용자의 외부 및 내부 통신에 대해 보관 됩니다.

보관을 배포할 때 초기 보관 정책을 설정 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 보관 정책 구성 및 할당](lync-server-2013-configuring-and-assigning-archiving-policies.md) 을 참조 하세요. 배포 후 보관 정책을 사용 하 고 통신을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 운영 설명서의 [Lync Server 2013에서 내부 및 외부 통신 보관 관리](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) 를 참조 하세요.

<div>


> [!NOTE]  
> Lync Server 2013 보관 데이터베이스를 모두 구현 하 고 Microsoft Exchange 통합을 사용 하는 경우 Exchange 2013 정책은 Exchange 2013에 속한 사용자와 사서함이 원본 위치 유지에 배치 된 경우에만 Lync Server 보관 정책을 재정의 합니다. . Lync 보관은 Microsoft Exchange 원본 위치 유지 정책에만 종속 됩니다.



</div>

</div>

<div>

## <a name="what-options-do-i-have-for-configuring-archiving"></a>보관을 구성 하는 데 사용할 수 있는 옵션은 무엇 인가요?

정책을 사용 하 고 보관을 사용 하거나 사용 하지 않도록 설정 하는 것 외에도 전체 배포에 대해 구성할 수 있는 다른 보관 옵션이 있으며, 선택적으로 특정 사이트와 풀에 대 한 관리 옵션도 있습니다. Lync Server 2013 제어판에서 사용할 수 있는 하나 이상의 보관 구성을 사용 하 여 대부분의 보관 옵션을 제어 하지만 Lync Server 2013 Management Shell을 사용 하 여 구성에만 사용할 수 있는 다른 옵션을 사용할 수도 있습니다.

<div>

## <a name="archiving-configuration-options-available-in-lync-server-2013-control-panel"></a>Lync Server 2013 제어판에서 사용할 수 있는 보관 구성 옵션

각 보관 구성은 다음 옵션을 제공 합니다.

전역 수준 구성은 보관을 배포할 때 자동으로 만들어지고, 구성 될 수 있지만 삭제 되지는 않습니다. 전역 구성을 삭제 하는 옵션을 선택 하면 설정이 기본값으로 다시 설정 됩니다. 전역 구성과 함께 보관 설정을 제어 하는 여러 사이트 및 풀 구성을 만들 수 있습니다. 전역 구성과 각 사이트 및 풀 구성에 대해 다음 옵션을 사용할 수 있습니다.

  - 보관을 사용 하지 않도록 설정 하거나 im (인스턴트 메시징)에 대해서만 보관을 사용 하도록 설정 하거나 IM 및 회의 보관을 사용할 수 있도록 설정 합니다.

  - Lync 서버 장애가 발생 하는 경우 IM 및 회의 세션을 차단 하도록 중요 모드를 구성 합니다. 오류에는 다음이 포함 됩니다.
    
      - **메신저 대화**. Lync Server 저장소 서비스에 문제가 있습니다. 이 경우 보관을 사용하도록 설정된 사용자에 대해 메신저가 차단됩니다.
    
      - **회의**. 파일 공유를 사용할 수 없거나 저장소 서비스에 문제가 있는 경우 보관에 실패할 수 있습니다. 이 경우 실패 시 풀에서 호스팅되는 모든 활성 회의가 제한 모드로 전환되며 새 회의를 활성화할 수 없습니다.
    
    오류가 수정된 다음에는 메신저 및 회의 모두 자동으로 복구됩니다.

  - Lync Server 2013 보관 데이터를 저장 하는 별도의 SQL Server 데이터베이스를 설정 하는 대신 Microsoft Exchange Server 2013 통합을 사용 하 여 보관 된 데이터 저장소에 Exchange 2013을 사용 하도록 지정 합니다.

  - 보관 된 데이터의 제거 옵션을 구성 합니다. 보관 된 데이터 제거 시기를 지정 하는 것은 다음 중 하나가 될 수 있습니다.
    
      - 지정 된 날짜 수가 지난 후
    
      - 보관 데이터를 내보낸 후 (Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange에 업로드 된 데이터 포함)
    
    <div>
    

    > [!NOTE]  
    > Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange 2013에 있는 사용자를 제거 하 고 해당 사서함이 원본 위치 유지에 포함 되는 경우 Exchange에서 제어 합니다. 유일한 자격은 Lync Server 파일 공유에 저장 된 회의 파일에 대 한 것입니다. 이러한 파일은 보관 데이터를 내보낸 후 데이터를 삭제하는 옵션을 선택하는 경우에는 파일을 내보내 해당 파일이 Exchange에 업로드된 후에, 그리고 최대 보존 기간(일)을 지정하는 경우에는 지정된 최대 기간(일) 후에 파일 공유에서 삭제됩니다.

    
    </div>

기본적으로 보관 옵션이 설정 되어 있지 않습니다. Lync Server 2013 제어판을 사용 하 여 보관 구성을 관리할 수 있습니다.

다음과 같은 보관 구성을 지정할 수 있습니다.

  - **전역 보관 구성**. 이는 기본 보관 구성으로, 전체 배포에 적용 됩니다. Lync Server 2013을 배포할 때 만들어지고 기본적으로 보관 기능을 사용 하지 않습니다. 전역 구성은 수정할 수 있지만 삭제할 수는 없습니다. 구성에 대 한 삭제 옵션을 선택 하면 전역 구성이 기본 설정으로 다시 설정 됩니다.

  - **사이트 보관 구성**. 필요에 따라 개별 사이트에 대 한 사이트 수준 보관 구성을 만들고 구성 하 여 하나 이상의 특정 사이트에 대해 보관을 구성할 수 있습니다. 사이트 수준 보관 구성은 만든 경우에만 존재 합니다. 사이트 수준의 보관 구성을 수정 하거나 삭제할 수 있습니다. 사이트 수준 보관 구성은 사이트 수준 구성에 지정 된 사이트에 대해서만 전역 구성 보다 우선 합니다. 예를 들어 전역 구성에서 IM만 보관을 사용 하도록 설정 하 고 IM 및 회의를 모두 보관할 수 있는 사이트 구성을 만들면, 회의는 조직의 나머지 사용자가 아닌 사이트에 대해서만 보관 됩니다.

  - **풀 아카이빙 구성**. 필요에 따라 개별 풀에 대 한 풀 수준 구성을 만들고 구성 하 여 하나 이상의 특정 풀에 대 한 보관 설정을 지정할 수 있습니다. 풀 수준 보관 구성은 만든 경우에만 존재 합니다. 풀 수준의 보관 구성을 수정 하 고 삭제할 수 있습니다. 풀 수준 보관 구성은 전역 구성 및 사용자가 만든 사이트 보관 구성 보다 우선 합니다. 예를 들어 전역 구성에서 IM만 보관을 사용 하도록 설정한 경우 사이트에 대 한 IM 및 회의 모두 보관을 사용 하도록 설정한 사이트 수준 구성을 만든 다음 다음에 대 한 보관만 사용 하도록 설정 하는 풀 수준 구성을 만듭니다. IM은 풀 수준 구성에 지정 된 풀에 속한 사용자를 제외 하 고 사이트의 모든 사용자에 대해 IM 및 회의에 대 한 통신을 보관 합니다. 조직의 다른 모든 사용자의 경우 IM에 대해서만 보관을 사용할 수 있습니다.

보관을 배포할 때 초기 보관 구성을 설정 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 보관 옵션 구성을](lync-server-2013-configuring-archiving-options.md) 참조 하세요. 배포 후 보관 정책을 사용 하 고 통신을 사용 하거나 사용 하지 않도록 설정 하는 방법에 대 한 자세한 내용은 운영 설명서에서 [조직, 사이트 및 풀에 대 한 Lync Server 2013의 보관 구성 옵션 관리](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md) 를 참조 하세요.

</div>

<div>

## <a name="archiving-options-available-only-in-windows-powershell"></a>보관 옵션은 Windows PowerShell 에서만 사용할 수 있습니다.

Lync Server 2013 관리 셸을 사용 하면 cmdlet을 사용 하 여 Lync Server 2013 제어판에서 사용할 수 없는 옵션을 구현할 수 있습니다. 이러한 옵션에는 다음이 포함 됩니다.

  - **중복 메시지 보관** 자세한 내용은 운영 설명서의 [CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsArchivingConfiguration) 및 [Set-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsArchivingConfiguration) 을 참조 하세요.

  - **보관 된 데이터 내보내기** 자세한 내용은 [내보내기-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) 을 참조 하세요.

</div>

</div>

</div>

<div>

## <a name="how-do-i-access-archived-data"></a>보관 된 데이터에 액세스 하려면 어떻게 하나요?

보관 된 데이터에 대 한 액세스는 데이터가 저장 되는 위치에 따라 달라 집니다.

  - **Microsoft Exchange 저장소**. Exchange 통합 옵션을 선택 하면 Lync Server는 exchange 2013에 있는 모든 사용자에 대해 Exchange 2013 저장소의 보관 콘텐츠를 저축과 하 고 사서함이 원본 위치 유지에 배치 되어 있는지 여부를 표시 합니다. 저장 된 데이터는 사용자에 게 표시 되지 않으며, Exchange **검색 관리** 역할을 사용 하는 사용자만 검색할 수 있는 사용자 사서함 복구 가능한 항목 폴더에 저장 됩니다. Exchange는 배포 된 경우 SharePoint와 함께 페더레이션 검색 및 검색이 가능 합니다. Exchange에 저장 된 데이터를 저장, 보존 및 검색 하는 방법에 대 한 자세한 내용은 Exchange 2013 및 SharePoint 설명서를 참조 하세요.

  - **Lync Server 저장소**. Lync 서버 데이터 저장소에 대 한 Lync Server 2013 보관 데이터베이스를 설정 하는 경우 Lync Server는 Exchange 2013에 포함 되지 않은 모든 사용자의 Lync Server 보관 데이터베이스 (SQL Server 데이터베이스)에 콘텐츠를 보관 하 고, 사서함이 없는 사람을 저축과. 원본 위치 유지 이 데이터는 검색 가능 하지 않지만 다른 도구를 사용 하 여 검색 가능한 형식으로 내보낼 수 있습니다. 보관 데이터베이스에 저장 된 데이터를 내보내는 방법에 대 한 자세한 내용은 운영 설명서의 [Lync Server 2013에서 보관 된 데이터 내보내기를](lync-server-2013-exporting-archived-data.md) 참조 하세요.

Lync Server 2013 및 Exchange 2013을 함께 사용 하는 방법에 대 한 자세한 내용은 지원 가능성 설명서의 [Lync server 2013에서 Exchange server 및 SharePoint 통합 지원](lync-server-2013-exchange-and-sharepoint-integration-support.md) 을 참조 하세요.

</div>

</div>

<span> </span>

</div>

</div>

</div>

