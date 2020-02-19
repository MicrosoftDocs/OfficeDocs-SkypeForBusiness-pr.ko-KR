---
title: 'Lync Server 2013: 재해 복구 시 알림 관리'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage announcements during disaster recovery
ms:assetid: c33e51ea-421f-42d2-826b-b73968f6bd5b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721874(v=OCS.15)
ms:contentKeyID: 49733807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0f7c54293205ac9246db39950e701074b12a42a6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013에서 재해 복구 시 알림 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정 된 항목:** 2013-02-23_

Lync Server 2013에서는 중단 시 할당 되지 않은 번호로 전화를 걸 수 있는 알림을 지원 합니다. 중단 시 알림 기능을 복원하는 것은 선택 사항입니다. 중단 시 알림을 복원하려는 경우 백업 풀에서 알림 구성을 다시 만들어야 합니다. 이 섹션에서는 재해 복구 시 알림을 복원하려는 경우 수행해야 할 작업에 대해 설명합니다.

이 섹션은 알림 응용 프로그램을 사용 하는 할당 되지 않은 번호 범위에 적용 됩니다. 이 섹션은 Exchange UM (통합 메시징) 자동 전화 교환을 사용 하는 할당 되지 않은 번호 범위에는 적용 되지 않습니다.

<div>

## <a name="before-an-outage"></a>중단 전 수행할 작업

중단 시간 중에 알림을 사용할지 여부에 관계 없이 알림 응용 프로그램에 대해 구성한 모든 사용자 지정 오디오 파일을 별도로 백업 해야 합니다. 사용자 지정 된 알림은 Lync Server 재해 복구 프로세스의 일부로 백업 되지 않습니다. 이러한 파일의 별도 백업을 만들지 않은 상태에서 서버 또는 풀에 업로드한 파일이 손상되거나 삭제될 경우 파일이 손실됩니다.

사용자 지정 된 오디오 파일의 백업 복사본을 사용 하지 않고 원본 오디오 파일을 더 이상 사용할 수 없는 경우 알림 응용 프로그램에 대해 구성한 오디오 파일을 찾을 수 있습니다. 파일을 가져왔습니다. 알림 응용 프로그램에 대해 구성한 모든 오디오 파일을 파일 저장소에서 복사할 수 있습니다.

**파일 저장소에서 오디오 파일을 복사 하려면**

1.  명령줄에서 다음을 실행합니다.
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    예를 들면 다음과 같습니다.
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    여기서 X-ApplicationServer-X는 풀의 응용 프로그램 서버의 서비스 ID(예: 1-ApplicationServer-1")를 나타냅니다.


</div>

<div>

## <a name="during-an-outage"></a>중단 도중 수행할 작업

중단 되는 동안 알림 응용 프로그램을 사용 하려면이 섹션에서 설명 하는 작업을 수행 하 여 백업 풀에서 알림 구성을 다시 만들어야 합니다.

<div>


> [!NOTE]  
> 이러한 작업은 백업 풀로 장애 조치한(failover) 후에 수행하는 것이 좋습니다. 2단계를 수행하자마자 할당되지 않은 번호 범위를 백업 풀에서 소유하기 때문입니다.



</div>

<div>


> [!NOTE]  
> 이러한 단계는 Exchange UM 자동 전화 교환 전화 번호를 사용하는 번호 범위에는 필요하지 않습니다.



</div>

**백업 풀에서 알림 구성을 다시 만들려면**

1.  백업 풀에서 다음을 수행하여 주 풀에 배포한 알림을 다시 만듭니다.
    
    1.  **Import-CsAnnouncementFile** cmdlet을 사용하고 Parent 매개 변수에 백업 풀을 지정하여 주 풀에서 사용된 모든 오디오 파일을 해당 백업 풀로 가져옵니다.
    
    2.  **New-CsAnnouncement** cmdlet을 사용하고 Parent 매개 변수에 백업 풀을 지정하여 각 알림을 다시 만듭니다.
    
    <div>
    

    > [!NOTE]  
    > 이러한 매개 변수를 사용 하 여 백업 풀에서 알림을 만드는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-create-an-announcement.md">create a 공고 in The Lync Server 2013</A>을 참조 하십시오.

    
    </div>

2.  백업 풀에서 모든 알림을 다시 만든 후에는 주 풀에서 알림을 사용하는, 할당되지 않은 모든 번호 범위를 백업 풀에 다시 만든 알림으로 리디렉션합니다.
    
    주 풀에서 알림을 사용하는, 할당되지 않은 각 번호 범위를 얻으려면 다음을 실행합니다.
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a>중단 후 수행할 작업

주 풀을 사용할 수 있게 되면 중단 시 변경한 할당되지 않은 번호 범위를 주 풀로 다시 리디렉션해야 합니다.

<div>


> [!NOTE]  
> 이러한 단계는 Exchange UM 자동 전화 교환 전화 번호를 사용하는 번호 범위에는 필요하지 않습니다.



</div>

**기본 풀에서 알림을 복원 하려면**

1.  복구 시 주 풀을 재구성해야 했던 경우, 백업 풀에서 한 것처럼(단, Parent 매개 변수에 주 풀을 지정) 오디오 파일을 가져오고 알림을 만들어 주 풀에서 알림을 다시 만들어야 합니다. 자세한 내용은 이 항목 앞부분에 있는 "중단 도중 수행할 작업"을 참조하십시오.

2.  중단 시 변경한 할당되지 않은 각 번호 범위를 얻으려면 다음을 실행합니다.
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  필요한 경우 백업 풀에서 다시 만든 알림을 제거 합니다. 백업 풀 알림 응용 프로그램에 대 한 공지 사항 목록을 가져옵니다. 명령줄에서 다음을 실행합니다.
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    예를 들면 다음과 같습니다.
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    결과로 반환된 목록에서 제거할 알림을 찾아 GUID를 복사합니다. 제거할 각 알림에 대해 다음을 실행합니다.
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    예를 들면 다음과 같습니다.
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

