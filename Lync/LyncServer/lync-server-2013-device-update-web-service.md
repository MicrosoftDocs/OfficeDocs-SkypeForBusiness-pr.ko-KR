---
title: 'Lync Server 2013: 장치 업데이트 웹 서비스'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Update Web service
ms:assetid: 036f473d-a131-431f-8051-76ccadc5cfba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994015(v=OCS.15)
ms:contentKeyID: 51803921
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8c2c9f7068943deabb90e5a87d95f35fecfbc30c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="device-update-web-service-in-lync-server-2013"></a><span data-ttu-id="3c230-102">Lync Server 2013의 장치 업데이트 웹 서비스</span><span class="sxs-lookup"><span data-stu-id="3c230-102">Device Update Web service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c230-103">_**마지막으로 수정한 주제:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="3c230-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="3c230-104">Lync Server에는 웹 서비스 역할의 일부로 자동으로 설치 되는 장치 업데이트 웹 서비스가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c230-104">Lync Server includes the Device Update Web service, which is automatically installed as part of the Web Services role.</span></span> <span data-ttu-id="3c230-105">이 서비스를 사용 하면 Microsoft에서 업데이트를 다운로드 하 고 테스트 한 다음 조직의 IP 휴대폰에 업데이트를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c230-105">This service lets you download updates from Microsoft, test them, and then deploy the updates to IP phones in your organization.</span></span> <span data-ttu-id="3c230-106">장치 업데이트 웹 서비스를 사용 하 여 이전 소프트웨어 버전으로 장치를 롤백할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c230-106">You can also use Device Update Web service to roll back devices to previous software versions.</span></span>

<span data-ttu-id="3c230-107">이 섹션에서는 디바이스 업데이트 웹 서비스를 관리 하는 방법과 장치 업데이트 로그를 사용 하 여 배포 된 업데이트, 규칙 (Lync Phone Edition에서 펌웨어 버전 업데이트를 하드웨어 장치와 연결 하는 *규칙* 을 사용) 및 구성 설정을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c230-107">This section provides details about how to manage the Device Update Web service and deployed updates by using device update logs, rules (Lync Phone Edition uses *rules* to associate firmware version updates with hardware devices), and configuration settings.</span></span>

<span data-ttu-id="3c230-108">장치 업데이트 웹 서비스 프로세스 및 기능에 대 한 자세한 내용은 Lync Server 2010 TechNet 라이브러리에서 [장치 업데이트](http://technet.microsoft.com/en-us/library/gg412864\(v=ocs.14\).aspx) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3c230-108">For details about the Device Update Web service process and features, see [Updating Devices](http://technet.microsoft.com/en-us/library/gg412864\(v=ocs.14\).aspx) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="3c230-109">(모든 Lync Phone Edition 구성 요소와 마찬가지로 장치 업데이트 웹 서비스는 lync server 2010에서와 마찬가지로 Lync Server 2013와 동일한 방식으로 작동 하는 것을 참고 하세요.)</span><span class="sxs-lookup"><span data-stu-id="3c230-109">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3c230-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="3c230-110">In This Section</span></span>

  - [<span data-ttu-id="3c230-111">Lync Server 2013의 장치 업데이트 로그 및 파일</span><span class="sxs-lookup"><span data-stu-id="3c230-111">Device Update logs and files in Lync Server 2013</span></span>](lync-server-2013-device-update-logs-and-files.md)

  - [<span data-ttu-id="3c230-112">Lync Server 2013의 장치 업데이트 규칙</span><span class="sxs-lookup"><span data-stu-id="3c230-112">Device Update rules in Lync Server 2013</span></span>](lync-server-2013-device-update-rules.md)

  - [<span data-ttu-id="3c230-113">Lync Server 2013의 장치 업데이트 구성 설정</span><span class="sxs-lookup"><span data-stu-id="3c230-113">Device Update configuration settings in Lync Server 2013</span></span>](lync-server-2013-device-update-configuration-settings.md)

  - [<span data-ttu-id="3c230-114">Lync Server 2013의 장치 소프트웨어 업데이트 보기</span><span class="sxs-lookup"><span data-stu-id="3c230-114">View software updates for devices in Lync Server 2013</span></span>](lync-server-2013-view-software-updates-for-devices-in-your-organization.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3c230-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3c230-115">See Also</span></span>


<span data-ttu-id="3c230-116">[장치 관리 및 문제 해결을 위한 도구 및 서비스](http://technet.microsoft.com/en-us/library/gg425800\(v=ocs.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="3c230-116">[Tools and Services for Managing and Troubleshooting Devices](http://technet.microsoft.com/en-us/library/gg425800\(v=ocs.14\).aspx)</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

