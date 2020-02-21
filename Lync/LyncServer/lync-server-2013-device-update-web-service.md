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
ms.openlocfilehash: 509428b4cd0646e0993d6127bcee8a1f2182c11f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="device-update-web-service-in-lync-server-2013"></a><span data-ttu-id="35c70-102">Lync Server 2013의 장치 업데이트 웹 서비스</span><span class="sxs-lookup"><span data-stu-id="35c70-102">Device Update Web service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="35c70-103">_**마지막으로 수정 된 항목:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="35c70-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="35c70-104">Lync Server에는 웹 서비스 역할의 일부로 자동 설치 되는 장치 업데이트 웹 서비스가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35c70-104">Lync Server includes the Device Update Web service, which is automatically installed as part of the Web Services role.</span></span> <span data-ttu-id="35c70-105">이 서비스를 사용 하면 Microsoft에서 업데이트를 다운로드 하 여 테스트 한 다음 조직의 IP 전화에 업데이트를 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35c70-105">This service lets you download updates from Microsoft, test them, and then deploy the updates to IP phones in your organization.</span></span> <span data-ttu-id="35c70-106">장치 업데이트 웹 서비스를 사용 하 여 이전 소프트웨어 버전에 장치를 롤백할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35c70-106">You can also use Device Update Web service to roll back devices to previous software versions.</span></span>

<span data-ttu-id="35c70-107">이 섹션에서는 장치 업데이트 웹 서비스 및 배포 된 업데이트를 관리 하는 방법에 대해 자세히 설명 합니다 (Lync Phone Edition은 규칙을 사용 하 여 펌웨어 버전 업데이트를 하드웨어 장치와 연결 하는 데 *사용할 수 있습니다* ), 구성 설정에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="35c70-107">This section provides details about how to manage the Device Update Web service and deployed updates by using device update logs, rules (Lync Phone Edition uses *rules* to associate firmware version updates with hardware devices), and configuration settings.</span></span>

<span data-ttu-id="35c70-108">장치 업데이트 웹 서비스의 프로세스 및 기능에 대 한 자세한 내용은 Lync Server 2010 TechNet 라이브러리에서 [장치](https://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) 업데이트를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="35c70-108">For details about the Device Update Web service process and features, see [Updating Devices](https://technet.microsoft.com/library/gg412864\(v=ocs.14\).aspx) in the Lync Server 2010 TechNet Library.</span></span> <span data-ttu-id="35c70-109">모든 Lync Phone Edition 구성 요소와 마찬가지로 장치 업데이트 웹 서비스는 lync Server 2010와 마찬가지로 Lync Server 2013 에서도 동일한 방식으로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="35c70-109">(Note that the Device Update Web service, like all Lync Phone Edition components, works the same way with Lync Server 2013 as it does with Lync Server 2010.)</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="35c70-110">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="35c70-110">In This Section</span></span>

  - [<span data-ttu-id="35c70-111">Lync Server 2013의 장치 업데이트 로그 및 파일</span><span class="sxs-lookup"><span data-stu-id="35c70-111">Device Update logs and files in Lync Server 2013</span></span>](lync-server-2013-device-update-logs-and-files.md)

  - [<span data-ttu-id="35c70-112">Lync Server 2013의 장치 업데이트 규칙</span><span class="sxs-lookup"><span data-stu-id="35c70-112">Device Update rules in Lync Server 2013</span></span>](lync-server-2013-device-update-rules.md)

  - [<span data-ttu-id="35c70-113">Lync Server 2013의 장치 업데이트 구성 설정</span><span class="sxs-lookup"><span data-stu-id="35c70-113">Device Update configuration settings in Lync Server 2013</span></span>](lync-server-2013-device-update-configuration-settings.md)

  - [<span data-ttu-id="35c70-114">Lync Server 2013의 장치에 대 한 소프트웨어 업데이트 보기</span><span class="sxs-lookup"><span data-stu-id="35c70-114">View software updates for devices in Lync Server 2013</span></span>](lync-server-2013-view-software-updates-for-devices-in-your-organization.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="35c70-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="35c70-115">See Also</span></span>


<span data-ttu-id="35c70-116">[장치 관리 및 문제 해결을 위한 도구 및 서비스](https://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span><span class="sxs-lookup"><span data-stu-id="35c70-116">[Tools and Services for Managing and Troubleshooting Devices](https://technet.microsoft.com/library/gg425800\(v=ocs.14\).aspx)</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

