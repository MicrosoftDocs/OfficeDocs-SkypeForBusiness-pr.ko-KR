---
title: 'Lync Server 2013: 응답 그룹 설정 복원'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Response Group settings
ms:assetid: 4f8e1949-925d-4538-be1d-9ac7c06b2aca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202174(v=OCS.15)
ms:contentKeyID: 51541473
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3c663441496d7a08a656095da4371376912fadc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="restoring-response-group-settings-in-lync-server-2013"></a><span data-ttu-id="070aa-102">Lync Server 2013에서 응답 그룹 설정 복원</span><span class="sxs-lookup"><span data-stu-id="070aa-102">Restoring Response Group settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="070aa-103">_**마지막으로 수정 된 항목:** 2013-02-18_</span><span class="sxs-lookup"><span data-stu-id="070aa-103">_**Topic Last Modified:** 2013-02-18_</span></span>

<span data-ttu-id="070aa-104">응답 그룹 응용 프로그램을 배포한 경우 백 엔드 서버 또는 Standard Edition 서버를 복원 해야 하는 경우에도 응답 그룹 구성 설정을 복원 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="070aa-104">If you deployed the Response Group application and you need to restore a Back End Server or a Standard Edition server, you also need to restore the Response Group configuration settings.</span></span>

<div>

## <a name="to-restore-response-group-configuration-settings"></a><span data-ttu-id="070aa-105">응답 그룹 구성 설정을 복원하려면</span><span class="sxs-lookup"><span data-stu-id="070aa-105">To restore Response Group configuration settings</span></span>

1.  <span data-ttu-id="070aa-106">명령줄에 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="070aa-106">At the command line, type:</span></span>
    
        Import-CsRgsConfiguration -Destination "service:ApplicationServer:<pool FQDN>" -OverwriteOwner -FileName "<path and file name of the backed up file at $Backup>"
    
    <span data-ttu-id="070aa-107">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="070aa-107">For example:</span></span>
    
        Import-CsRgsConfiguration -Destination "service: ApplicationServer:pool01.contoso.com" -OverwriteOwner -FileName "C:\RgsConfiguration.zip"

</div>

</div>

<span> </span>

</div>

</div>

</div>

