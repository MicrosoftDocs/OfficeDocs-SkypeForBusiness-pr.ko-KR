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
ms.openlocfilehash: dfc987ea579bef4e2b02c8da210efe9a707c5900
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-announcements-during-disaster-recovery-in-lync-server-2013"></a>Lync Server 2013에서 재해 복구 시 알림 관리

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**마지막으로 수정한 주제:** 2013-02-23_

Lync Server 2013는 작동 중단 중에 할당 되지 않은 번호로 전화를 걸 때의 알림을 지원 합니다. 중단 중에 알림 기능을 복원 하는 것은 선택 사항입니다. 중단 중에 알림을 복원 하도록 선택한 경우에는 백업 풀에 알림 구성을 다시 만들어야 합니다. 이 섹션에서는 재해 복구 중에 알림을 복원 하도록 선택한 경우 수행 해야 할 작업에 대해 설명 합니다.

이 섹션은 공지 사항 응용 프로그램을 사용 하는 지정 되지 않은 숫자 범위에 적용 됩니다. 이 섹션은 Exchange UM (통합 메시징) 자동 전화 교환을 사용 하는 지정 되지 않은 숫자 범위에는 적용 되지 않습니다.

<div>

## <a name="before-an-outage"></a>중단 전

중단 중에 알림을 사용할지 여부에 관계 없이 알림 응용 프로그램에 대해 구성한 모든 사용자 지정 오디오 파일을 별도의 백업으로 사용 해야 합니다. 사용자 지정 된 알림은 Lync Server 재해 복구 프로세스의 일부로 백업 되지 않습니다. 파일을 별도로 백업 하지 않고 서버 또는 풀에 업로드 한 파일이 손상, 손상 또는 지워진 경우 파일이 손실 됩니다.

사용자 지정 오디오 파일의 백업 복사본이 없고 원본 오디오 파일을 더 이상 사용할 수 없는 경우, 원래 위치에 있는 서버 또는 풀에 대 한 파일 저장소에서 알림 응용 프로그램에 대해 구성한 오디오 파일을 찾을 수 있습니다. 파일을 가져왔습니다. 파일 저장소에서 알림 신청에 대해 구성한 모든 오디오 파일을 복사할 수 있습니다.

**파일 저장소에서 오디오 파일을 복사 하려면**

1.  명령줄에서 다음을 실행 합니다.
    
        Xcopy <Source: Pool Announcement Service File Store path> <Destination>
    
    예를 들면 다음과 같습니다.
    
        Xcopy "<Pool File Store Path>\X-ApplicationServer-X\AppServerFiles\RGS\AS" "<Destination: Backup location>"
    
    여기서 X-ApplicationServer-X는 풀의 응용 프로그램 서버의 서비스 ID를 참조 합니다 (예: 1-ApplicationServer-1 ").


</div>

<div>

## <a name="during-an-outage"></a>중단 하는 동안

중단 하는 동안 알림 응용 프로그램을 사용 하려면이 섹션에서 설명 하는 작업을 수행 하 여 백업 풀에 알림 구성을 다시 만들어야 합니다.

<div>


> [!NOTE]  
> 백업 풀에 대 한 작업을 수행 하는 즉시 백업 풀이 할당 되지 않은 번호 범위에 대 한 소유권을 가지 므 때문에이 두 단계를 수행 하는 것이 좋습니다.



</div>

<div>


> [!NOTE]  
> 이 단계는 Exchange UM 자동 전화 교환 전화 번호를 사용 하는 숫자 범위에는 필요 하지 않습니다.



</div>

**백업 풀에서 알림 구성 다시 만들기**

1.  다음을 수행 하 여 백업 풀의 기본 풀에 배포한 알림을 다시 만듭니다.
    
    1.  **CsAnnouncementFile** cmdlet을 사용 하 고 부모 매개 변수에 대 한 백업 풀을 지정 하 여 기본 풀에 사용 되는 오디오 파일을 백업 풀에 가져옵니다.
    
    2.  **새 csannouncement** cmdlet을 사용 하 고 부모 매개 변수에 대 한 백업 풀을 지정 하 여 각 알림을 다시 만듭니다.
    
    <div>
    

    > [!NOTE]  
    > 이러한 매개 변수를 사용 하 여 백업 풀에 알림을 만드는 방법에 대 한 자세한 내용은 <A href="lync-server-2013-create-an-announcement.md">Lync Server 2013에서 공지 만들기</A>를 참조 하세요.

    
    </div>

2.  백업 풀에 모든 알림이 다시 만들어진 후에는 기본 풀의 공지 사항을 사용 하는 모든 할당 되지 않은 번호 범위를 백업 풀의 재작성 된 공지 사항으로 리디렉션합니다.
    
    기본 풀에서 알림을 사용 하는 각 할당 되지 않은 숫자 범위에 대해 다음을 실행 합니다.
    
        Set-CsUnassignedNumber -Identity "<name of number range>" -AnnouncementService "<FQDN of backup pool>" -AnnouncementName "<announcement name in backup pool>"

</div>

<div>

## <a name="after-the-outage"></a>중단 후

주 풀을 사용할 수 있게 되 면 중단에 대해 변경한 할당 되지 않은 번호 범위를 다시 기본 풀로 리디렉션해야 합니다.

<div>


> [!NOTE]  
> 이 단계는 Exchange UM 자동 전화 교환 전화 번호를 사용 하는 숫자 범위에는 필요 하지 않습니다.



</div>

**기본 풀에서 알림을 복원 하려면**

1.  복구 하는 동안 기본 풀을 다시 작성 해야 하는 경우 부모에 대 한 기본 풀을 지정 하는 경우를 제외 하 고 백업 풀에서와 마찬가지로 오디오 파일을 가져오고 알림을 만들어 기본 풀에 알림을 다시 만들어야 합니다. 변수도. 자세한 내용은이 항목의 앞부분에 있는 "중단 하는 동안"을 참조 하세요.

2.  중단을 위해 변경한 각 할당 되지 않은 숫자 범위에 대해 다음을 실행 합니다.
    
        Set-CsUnassignedNumber [-Identity "<name of number range>"] -AnnouncementService "<FQDN of primary pool>" -AnnouncementName "<announcement name in primary pool>"

3.  필요에 따라 백업 풀에서 다시 만든 알림을 제거 합니다. 백업 풀 알림 응용 프로그램의 공지 사항 목록을 가져옵니다. 명령줄에서 다음을 실행 합니다.
    
        Get-CsAnnouncement -Identity "<Service:service ID>"
    
    예를 들면 다음과 같습니다.
    
        Get-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com
    
    결과 목록에서 제거 하 고 Guid를 복사 하려는 공지 사항을 찾습니다. 제거 하려는 각 공지 사항에 대해 다음을 실행 합니다.
    
        Remove-CsAnnouncement -Identity "<Service:service ID/guid>"
    
    예를 들면 다음과 같습니다.
    
        Remove-CsAnnouncement -Identity "ApplicationServer:redmond.contoso.com/1951f734-c80f-4fb2-965d-51807c792b90"


</div>

</div>

<span> </span>

</div>

</div>

</div>

