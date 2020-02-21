---
title: 'Lync Server 2013: 백업 및 복원 프로세스 개요'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dd6efce509283d59c5cecc7325c35c9cf1ab371e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187081"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a>Lync Server 2013에 대 한 백업 및 복원 프로세스 개요

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-03-26_

이 섹션에서는 Lync Server 2013에 대해 백업 및 복원 프로세스가 작동 하는 방식에 대 한 개요를 제공 합니다. 위치에 관계없이 모든 Standard Edition 서버 및 Enterprise Edition 서버에 대해 동일한 프로세스를 사용합니다.

일반적으로 백업 프로세스는 다음과 같이 작동 합니다.

  - 특정 풀에 속하지 않는 독립 실행형 컴퓨터에서 공유 폴더로 백업 위치를 만듭니다. 백업 위치는 **$Backup**에서 참조됩니다.

  - 정기적으로 일정에 따라 lync server [2013의 백업 및 복원 요구 사항](lync-server-2013-backup-and-restoration-requirements-data.md) 에 설명 되어 있는 모든 파일 저장소 및 모든 lync server [2013](lync-server-2013-backing-up-lync-server.md) 백업에 설명 된 절차에 따라 중앙 관리 저장소에는 모든 서버 설정 및 구성이 포함 됩니다.

  - 이후 백업을 실행할 때마다 새 공유 폴더를 만들고 **$Backup**이 참조하는 경로를 변경합니다.

일반적으로 복원 프로세스는 다음과 같이 작동 합니다.

  - 오류 또는 중단이 발생 하면 **$Backup** 에서 참조 하는 위치에 있는 데이터를 새 컴퓨터나 정상 컴퓨터로 복원 합니다.
    
    <div>
    

    > [!IMPORTANT]  
    > 이 복원 프로세스에서는 데이터를 기존 서버 상태로 복원하지 않습니다. 즉, 이 프로세스에서는 서버가 신규 서버이거나 깨끗한 서버여야 합니다.

    
    </div>

  - 사용자 및 전화 회의 정보를 오류 지점으로 복구할 수 있도록 하려면 [Lync Server 2013의 고가용성 및 재해 복구 계획](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)에서 설명 하는 대로 쌍으로 된 프런트 엔드 풀을 사용 하 여 재해 복구 토폴로지를 구현할 수 있습니다.

  - 모든 DNS(Domain Name System) 구성, DHCP(Dynamic Host Configuration Protocol) 구성, 도메인 이름, 컴퓨터 FQDN(정규화된 도메인 이름), 파일 저장소 경로 등은 백업할 때와 동일한 상태로 복원해야 합니다.

Lync Server를 실행 하는 서버에 오류가 발생 하면 다음과 같은 단계가 복구 됩니다.

  - 오류가 발생한 컴퓨터와 동일한 FQDN을 사용하여 신규 또는 깨끗한 컴퓨터에 운영 체제를 설치합니다.

  - 인증서를 다시 설치합니다.

  - 서버에서 데이터베이스를 호스트 하는 경우 Microsoft SQL Server 2012 또는 Microsoft SQL Server 2008 r 2를 설치 합니다.

  - 일반적으로 서버에서 데이터베이스를 호스팅한 경우 토폴로지 작성기를 실행 하 여 데이터베이스를 만들고 설치 하 고 Acl (액세스 제어 목록)을 설정 합니다.

  - 일반적으로 서버가 서버 역할을 호스트 하는 경우 Lync Server 배포 마법사의 1-4 단계를 실행 하 여 로컬 구성 파일을 설치 하 고, 서버 역할 구성 요소를 설치 하 고, 인증서를 할당 하 고, 서비스를 시작 합니다.
    
    <div>
    

    > [!NOTE]  
    > 서버가 서버 역할을 가진 데이터베이스를 호스트 하는 경우에는 Lync Server 배포 마법사의 2 단계를 실행 하 여 데이터베이스를 다시 만듭니다.

    
    </div>

  - 서버에서 데이터베이스를 호스트 하는 경우 백업한 데이터를 복원 합니다.

</div>

<span> </span>

</div>

</div>

</div>

