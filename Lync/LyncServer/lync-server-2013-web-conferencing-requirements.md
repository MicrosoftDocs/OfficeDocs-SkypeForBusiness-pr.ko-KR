---
title: 'Lync Server 2013: 웹 회의 요구 사항'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Web conferencing requirements
ms:assetid: 125f847c-58ab-450f-ae43-41219fd38477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ619171(v=OCS.15)
ms:contentKeyID: 49733559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dddfd7c2fdfe6cbcefcca7533e93c3c377cceea8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="web-conferencing-requirements-in-lync-server-2013"></a><span data-ttu-id="dfebb-102">Lync Server 2013의 웹 회의 요구 사항</span><span class="sxs-lookup"><span data-stu-id="dfebb-102">Web conferencing requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfebb-103">_**마지막으로 수정한 주제:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="dfebb-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="dfebb-104">웹 회의를 사용 하도록 선택한 경우 다음을 계획 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-104">If you have chosen to enable web conferencing, you need to plan for the following:</span></span>

  - <span></span>  
    <span data-ttu-id="dfebb-105">웹 회의 콘텐츠를 저장 하는 데 사용 되는 파일 저장소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-105">Access to the file store, which is used for storing web conferencing content.</span></span>

  - <span></span>  
    <span data-ttu-id="dfebb-106">전화 회의 중에 PowerPoint 파일을 공유 하기 위해 필요한 Office Web Apps 서버와 통합</span><span class="sxs-lookup"><span data-stu-id="dfebb-106">Integration with Office Web Apps Server, which is necessary in order to share PowerPoint files during a conference.</span></span>

<div>

## <a name="file-store"></a><span data-ttu-id="dfebb-107">파일 저장소</span><span class="sxs-lookup"><span data-stu-id="dfebb-107">File Store</span></span>

<span data-ttu-id="dfebb-108">Lync Server 2013 웹 회의 서비스는 파일 저장소의 모임 중에 공유 된 콘텐츠를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-108">The Lync Server 2013 web conferencing service stores content shared during meetings in the file store.</span></span> <span data-ttu-id="dfebb-109">배포의 일부로 표준 버전 서버 또는 Enterprise Edition 프런트 엔드 풀에 대 한 파일 저장소로 사용할 파일 공유를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-109">As part of deployment, you must specify a file share to be used as the file store for the either Standard Edition server or Enterprise Edition Front End pool.</span></span> <span data-ttu-id="dfebb-110">기존 파일 공유를 파일 저장소로 사용하거나 파일 공유가 위치할 파일 서버의 FQDN(정규화된 도메인 이름) 및 새 파일 공유의 폴더 이름을 지정하여 새 파일 공유를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-110">You can use an existing file share for the file store or you can specify a new file share by specifying the fully qualified domain name (FQDN) of the file server on which the file share is to be located and a folder name for the new file share.</span></span><span data-ttu-id="dfebb-111">자세한 내용은 토폴로지 작성기 – 프런트 엔드에서 파일 저장소 정의를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dfebb-111">  For more information, see Topology Builder – Define the File Store for the Front End.</span></span> <span data-ttu-id="dfebb-112">웹 회의 서비스는 콘텐츠를 파일 저장소에 저장 하기 전에 암호화 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-112">The web conferencing service encrypts the content before it stores the content in the file store.</span></span>

<span data-ttu-id="dfebb-113">Lync Server 2013는 직접 연결 저장소 (DAS) 또는 파일 저장소에 대 한 독립 디스크 (RAID)의 중복 배열 (분산 파일 시스템)을 비롯 한 SAN (저장소 영역 네트워크)에서 파일 공유를 사용 하도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-113">Lync Server 2013 supports using file shares on either direct attached storage (DAS) or a storage area network (SAN), including Distributed File System (DFS) and on a redundant array of independent disks (RAID) for file stores.</span></span> <span data-ttu-id="dfebb-114">Lync Server 배포 마법사에서 파일 공유 위치를 정의한 후에는 Lync Server가 다음과 같은 파일 공유 내에 폴더 구조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-114">After the Lync Server Deployment Wizard has defined the location of the file share, Lync Server creates a folder structure within the file share similar to:</span></span>

  - <span data-ttu-id="dfebb-115">1-ApplicationServer-1</span><span class="sxs-lookup"><span data-stu-id="dfebb-115">1-ApplicationServer-1</span></span>

  - <span data-ttu-id="dfebb-116">1-CentralMgmt-1</span><span class="sxs-lookup"><span data-stu-id="dfebb-116">1-CentralMgmt-1</span></span>

  - <span data-ttu-id="dfebb-117">1-WebServices-1</span><span class="sxs-lookup"><span data-stu-id="dfebb-117">1-WebServices-1</span></span>
    
      - <span data-ttu-id="dfebb-118">CollabContent</span><span class="sxs-lookup"><span data-stu-id="dfebb-118">CollabContent</span></span>
    
      - <span data-ttu-id="dfebb-119">CollabMetadata</span><span class="sxs-lookup"><span data-stu-id="dfebb-119">CollabMetadata</span></span>
    
      - <span data-ttu-id="dfebb-120">DataConf</span><span class="sxs-lookup"><span data-stu-id="dfebb-120">DataConf</span></span>

<span data-ttu-id="dfebb-121">그런 다음 웹 회의 서비스는 PowerPoint 슬라이드, 화이트 보드, 설문 조사, 첨부 파일 등의 콘텐츠를 WebServices 폴더에 있는 CollabContent 및 CollabMetadata 폴더에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-121">The web conferencing service then stores content such as PowerPoint slides, whiteboards, polls, and attachments in the CollabContent and CollabMetadata folders, located in the WebServices folder.</span></span>

<span data-ttu-id="dfebb-122">관리자가 파일 공유에 대 한 사용 권한을 설정 해야 RTC 그룹이 필요한 읽기 및 쓰기 권한을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-122">The administrator must set permissions on the file share so that RTC groups have the necessary read and write access.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="dfebb-123">사용 권한에 대 한 오류가 발생 하면 토폴로지 작성기를 열고 기존 토폴로지를 다운로드 하 여 다시 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-123">If you encounter any errors with the permissions, open Topology Builder, download and republish the existing topology.</span></span> <span data-ttu-id="dfebb-124">토폴로지를 게시 하면 파일 공유 권한을 확인 하 고 필요한 경우 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-124">Publishing the topology will verify the file share permissions and reset them if needed.</span></span>



</div>

<span data-ttu-id="dfebb-125">다음 설정을 사용 하 여 모임에 대 한 콘텐츠 저장 방법을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-125">You can use the following settings to manage how content is stored for a meeting:</span></span>

  - <span data-ttu-id="dfebb-126">**ContentGracePeriod**는 [CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)에 있으며, 모임이 종료 된 후에 서버에 웹 회의 콘텐츠를 유지 하는 시간을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-126">**ContentGracePeriod**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets how long web conferencing content will remain on the server after the meeting has ended.</span></span>

  - <span data-ttu-id="dfebb-127">[CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration)에 있는 **Maxcontentstoragemb**은 단일 모임 중에 콘텐츠 저장소에 허용 되는 최대 파일 공간 크기를 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-127">**MaxContentStorageMb**, located in [Set-CsConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsConferencingConfiguration), sets the maximum amount of file space allowed for the storage of content during a single meeting.</span></span>

<span data-ttu-id="dfebb-128">**MaxUploadFileSizeMb** 는 Lync Web App에 대 한 파일 업로드 설정을 제한 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-128">**MaxUploadFileSizeMb** does not limit the file upload setting for Lync Web App.</span></span> <span data-ttu-id="dfebb-129">Lync Web App에 대 한 파일 크기 업로드 제한은 약 30MB로 설정 되며 IIS web.config 파일:/Datacol/m/web.config에\[\]의해 제어 됩니다. Lync Web App, update `maxRequestLength` 및 `maxAllowedContentLength` 아래와 같이 web.config 파일에 대 한 파일 크기 업로드 제한을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-129">The file size upload limit for Lync Web App is set to approximately 30MB and is controlled by the IIS web.config file: /DataCollabWeb/Int\[Ext\]/Handler/web.config. To configure the file size upload limit for Lync Web App, update `maxRequestLength` and `maxAllowedContentLength` in the web.config file as shown below.</span></span>

    <system.web>
        <!-- 
            Since this handler is used to upload files to DMCU the request size (in kilobytes) 
            has to fit max allowed file size uploaded by Lync Web App client.
            The timeout has to reflect the min client bandwidth. Timeout of 600 secs 
            and 512 Kbits of *client* bandwidth would result into aproximately 30 Mbytes 
            for Lync Web App upload size limit.
        -->
          <httpRuntime maxRequestLength="500000" executionTimeout="600" />
    
    
    
                    <security>
                    <requestFiltering>
                               <requestLimits maxAllowedContentLength="524288000" />
                    </requestFiltering>
                    </security>

<span data-ttu-id="dfebb-130">각 프런트 엔드 서버에 대 한 web.config 파일을 업데이트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-130">You must update the web.config file for each Front End Server.</span></span>

</div>

<div>

## <a name="office-web-apps-server"></a><span data-ttu-id="dfebb-131">Office Web Apps 서버</span><span class="sxs-lookup"><span data-stu-id="dfebb-131">Office Web Apps Server</span></span>

<span data-ttu-id="dfebb-132">이러한 새 기능을 사용 하려면 관리자가 Office Web Apps 서버를 설치 하 고 Office Web Apps 서버와 통신 하도록 Lync Server 2013를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-132">In order to use these new capabilities administrators must install Office Web Apps Server and they must configure Lync Server 2013 to communicate with Office Web Apps Server.</span></span> <span data-ttu-id="dfebb-133">이 문서는 Office Web Apps 서버에서 작동 하도록 Lync Server 2013를 구성 하는 방법에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-133">This documentation provides information on how to configure Lync Server 2013 to work with Office Web Apps Server.</span></span> <span data-ttu-id="dfebb-134">이 설명서에는 Office Web Apps Server를 설치 하는 방법에 대 한 정보가 나와 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-134">What this documentation does not provide is information about how to install Office Web Apps Server.</span></span> <span data-ttu-id="dfebb-135">설치에 대 한 자세한 내용은 Microsoft Office Web Apps 배포 웹 사이트 <http://go.microsoft.com/fwlink/p/?linkid=257525>를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dfebb-135">For installation details, see the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span> <span data-ttu-id="dfebb-136">이 가이드에는 Office Web Apps Server에 대 한 전체 필수 구성 요소 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-136">That guide includes complete prerequisite information for Office Web Apps Server.</span></span> <span data-ttu-id="dfebb-137">Office Web Apps 서버는 Lync Server, SQL Server 또는 기타 서버 응용 프로그램을 실행 하지 않는 독립 실행형 컴퓨터에 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-137">Note that Office Web Apps Server should be installed on a stand-alone computer that is not running Lync Server, SQL Server, or any other server application.</span></span> <span data-ttu-id="dfebb-138">(해당 컴퓨터에 Office 버전이 설치 되어 있지 않아야 합니다.) Office Web Apps Server를 실행 하는 데 사용 되는 컴퓨터에는 .NET Framework 4.5 및 Windows PowerShell 3.0을 포함 하 여 특정 소프트웨어 집합도 설치 되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-138">(You must not have any version of Office installed on that computer.) Any computer used to run Office Web Apps Server must also have a specific set of software installed (including .NET Framework 4.5 and Windows PowerShell 3.0).</span></span> <span data-ttu-id="dfebb-139">이러한 요구 사항은 인증서 및 IIS (인터넷 정보 서비스)를 구성 하는 방법에 대 한 정보와 함께 Microsoft Office Web Apps 배포 웹 사이트에서 자세히 <http://go.microsoft.com/fwlink/p/?linkid=257525>설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="dfebb-139">These requirements, along with information about configuring certificates and Internet Information Services (IIS), are discussed in detail in the Microsoft Office Web Apps Deployment website at <http://go.microsoft.com/fwlink/p/?linkid=257525>.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dfebb-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dfebb-140">See Also</span></span>


[<span data-ttu-id="dfebb-141">Lync Server 2013의 웹 회의 개요</span><span class="sxs-lookup"><span data-stu-id="dfebb-141">Overview of web conferencing in Lync Server 2013</span></span>](lync-server-2013-web-conferencing-overview.md)  
[<span data-ttu-id="dfebb-142">Lync Server 2013의 웹 회의에 대 한 배포 검사 목록</span><span class="sxs-lookup"><span data-stu-id="dfebb-142">Deployment checklist for web conferencing in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-web-conferencing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

