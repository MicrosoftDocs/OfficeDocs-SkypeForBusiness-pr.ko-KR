---
title: 'Lync Server 2013: 장치 업데이트 로그 및 파일'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update logs and files
ms:assetid: f7f822b8-0a62-4ff2-a4cb-1ab1ed7503eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994090(v=OCS.15)
ms:contentKeyID: 51804004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 170bafb3d00940995e8355c7775681c2af5fd078
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762396"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-logs-and-files-in-lync-server-2013"></a><span data-ttu-id="3c7e6-102">Lync Server 2013의 장치 업데이트 로그 및 파일</span><span class="sxs-lookup"><span data-stu-id="3c7e6-102">Device Update logs and files in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c7e6-103">_**마지막으로 수정한 주제:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="3c7e6-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="3c7e6-104">장치 업데이트 로그에는 장치 업데이트 웹 서비스를 관리 하 고 문제를 해결 하는 데 사용할 수 있는 중요 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c7e6-104">Device update logs contain important information that you can use to manage and troubleshoot the Device Update Web service.</span></span> <span data-ttu-id="3c7e6-105">기록 되는 내용을 변경 하 고 더 이상 필요 하지 않거나 원하지 않는 장치 로그 및 업데이트를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c7e6-105">You can change what is logged and remove device logs and updates that you don’t want or no longer need.</span></span> <span data-ttu-id="3c7e6-106">이 섹션에서는 Lync Server 제어판 또는 Lync Server Management Shell을 사용 하 여 로깅 설정을 수정 하거나, 장치 업데이트 로그를 지우거 나, 서버에서 로그 파일을 제거 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c7e6-106">This section describes how you can use Lync Server Control Panel or Lync Server Management Shell to modify logging settings, clear the device update log, or remove log files from the server.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3c7e6-107">장치 업데이트 로그 파일에 대 한 자세한 내용은 Lync Server 2010 TechNet 라이브러리의 <A href="http://technet.microsoft.com/en-us/library/gg398250(v=ocs.14).aspx">로그 파일 형식 및 위치</A> 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3c7e6-107">For details about device update log files, see <A href="http://technet.microsoft.com/en-us/library/gg398250(v=ocs.14).aspx">Log File Types and Locations</A> in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="3c7e6-108">(모든 Lync Phone Edition 구성 요소와 마찬가지로 장치 업데이트 웹 서비스는 lync server 2010에서와 마찬가지로 Lync Server 2013와 동일한 방식으로 작동 하는 것을 참고 하세요.)</span><span class="sxs-lookup"><span data-stu-id="3c7e6-108">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3c7e6-109">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="3c7e6-109">In This Section</span></span>

  - [<span data-ttu-id="3c7e6-110">Lync Server 2013에서 장치 업데이트 로그 파일에 대 한 설정 수정</span><span class="sxs-lookup"><span data-stu-id="3c7e6-110">Modify settings for Device Update log files in Lync Server 2013</span></span>](lync-server-2013-modify-settings-for-device-update-log-files.md)

  - [<span data-ttu-id="3c7e6-111">Lync Server 2013에서 장치 업데이트 로그 파일 삭제</span><span class="sxs-lookup"><span data-stu-id="3c7e6-111">Delete Device Update log files in Lync Server 2013</span></span>](lync-server-2013-delete-device-update-log-files.md)

  - [<span data-ttu-id="3c7e6-112">장치 제거 장치에 연결 되지 않은 장치 업데이트 파일 제거 Lync Server 2013의 장치와 연결 되지 않은 디바이스 업데이트 파일 삭제</span><span class="sxs-lookup"><span data-stu-id="3c7e6-112">Remove Device Update files not associated with a device in Remove Device Update files not associated with a device in Lync Server 2013</span></span>](lync-server-2013-remove-device-update-files-not-associated-with-a-device.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

