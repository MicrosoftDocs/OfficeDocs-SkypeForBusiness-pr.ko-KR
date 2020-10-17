---
title: 'Lync Server 2013: 보관에 대 한 기술 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f0d1b609f7e053823de68363059d7c8b35c0659
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533935"
---
# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a>Lync Server 2013의 보관에 대 한 기술 요구 사항

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2012-10-09_

Lync Server 2013 기술 요구 사항에는 다음이 포함 됩니다.

  - 인프라 요구 사항

  - 보관용으로 설치해야 하는 필수 구성 요소 소프트웨어

  - 보관용 데이터 저장소 요구 사항

  - 보관 배포에 대한 확장 요구 사항 및 고려 사항

  - 보관 데이터베이스에 대한 성능 요구 사항 및 고려 사항

<div>


> [!NOTE]  
> 이 Lync Server 2013 릴리스에서는 확장 및 성능 정보를 사용할 수 없습니다.



</div>

<div>

## <a name="infrastructure-requirements"></a>인프라 요구 사항

Lync Server 2013 보관 인프라 요구 사항은 Lync Server 2013 배포와 동일 합니다. 자세한 내용은 계획 설명서에서 [Lync Server 2013에 대 한 인프라 요구 사항 결정](lync-server-2013-determining-your-infrastructure-requirements.md) 을 참조 하십시오.

</div>

<div>

## <a name="archiving-prerequisites"></a>보관 필요 조건

Lync Server 2013는 다음과 같은 이유로 보관을 위한 필수 구성 요소를 합리화 합니다.

  - 보관 서버가 더 이상 서버 역할이 아닙니다. 대신 보관용 데이터를 캡처하기 위해 통합 데이터 컬렉션 에이전트가 풀의 프런트 엔드 서버 및 Standard Edition 서버에서 실행되므로 보관을 위한 별도의 시스템 플랫폼을 설정하지 않아도 됩니다.

  - 보관은 Lync Server 2013 파일 저장소를 사용 하 여 모임 콘텐츠 파일을 임시로 저장 하므로 보관을 위해 별도의 파일 저장소를 설정 하지 않아도 됩니다.

  - Lync Server 2013에서는 메시지 큐가 필요 하지 않습니다.

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a>보관용 데이터 저장소 요구 사항

또한 보관 저장소에 대한 인프라를 설정할 필요가 없습니다. 여기에는 다음과 같은 항목 중 하나 또는 모두가 포함됩니다.

  - **Microsoft Exchange 저장소** 모임 콘텐츠 파일(예: PowerPoint 프레젠테이션)이 첨부 파일로 보관됩니다. Microsoft Exchange 통합을 사용 하 여 Lync 보관 데이터가 Exchange 준수 데이터와 함께 저장 되도록 하려면 exchange 배포에 Exchange 2013을 사용 하 고 최대 저장소 크기가 모임 콘텐츠 파일의 저장을 지원 하는지 확인 해야 합니다. Microsoft Exchange 통합 옵션을 사용 하 여 보관을 배포 하는 경우 Lync 보관 데이터는 Exchange 2013 서버에 있는 사용자에 대해서만 Exchange 2013 준수 데이터와 함께 저장 됩니다. Microsoft Exchange 통합 옵션을 사용 하 여 보관을 배포 하 고 사용 하려면 먼저 Exchange 2013를 배포 해야 합니다. Exchange 2013 저장소를 사용 하도록 선택 하는 경우 Exchange 2013 서버에 있지 않은 Lync 사용자가 없는 한 보관을 위해 별도의 SQL Server 데이터베이스를 배포할 필요가 없습니다.

  - **보관용 SQL Server 데이터베이스 저장소**입니다. Exchange 2013 서버에 없는 사용자를 지원 하거나 Microsoft Exchange 통합 옵션을 사용 하지 않으려는 경우 SQL Server 데이터베이스를 사용 하 여 보관 저장소를 배포 해야 합니다. Lync Server 2013에서는 다음 64 비트 버전의 SQL Server를 지원 합니다.
    
      - Microsoft SQL Server 2008 R2 Enterprise
    
      - Microsoft SQL Server 2008 R2 Standard
    
      - Microsoft SQL Server 2012 Enterprise
    
      - Microsoft SQL Server 2012 Standard
    
    <div>
    

    > [!NOTE]  
    > Microsoft SQL Server 2008 R2 Express 및 Microsoft SQL Server 2012 Express는 보관용으로 지원 되지 않습니다. 32 비트 버전의 SQL Server는 지원 되지 않습니다. SQL Server 요구 사항에 대 한 자세한 내용은 계획 설명서 또는 지원 가능성 설명서에서 <A href="lync-server-2013-database-software-support.md">Lync Server 2013의 데이터베이스 소프트웨어 지원을</A> 참조 하십시오.

    
    </div>
    
    보관을 배포 하 고 사용 하도록 설정 하기 전에 SQL Server 플랫폼을 설정 해야 합니다. 토폴로지를 게시하는 데 사용될 계정에 적절한 관리자 권한 및 권한이 있는 경우 토폴로지를 게시할 때 보관 데이터베이스(LcsLog)를 만들 수 있습니다. 또한 설치 절차의 일부로 포함하는 등 나중에 데이터베이스를 만들 수도 있습니다. SQL Server에 대 한 자세한 내용은 SQL Server TechCenter at를 참조 하십시오 [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045) .

</div>

</div>

<span> </span>

</div>

</div>

</div>

