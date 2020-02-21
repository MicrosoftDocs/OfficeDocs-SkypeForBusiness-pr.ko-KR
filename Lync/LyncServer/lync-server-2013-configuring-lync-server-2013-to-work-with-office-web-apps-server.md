---
title: Office Web Apps 서버에서 작동 하도록 Lync Server 2013 구성
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to work with Office Web Apps Server
ms:assetid: 6231e519-9010-4ff9-b5a6-b5859c2b3e11
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204944(v=OCS.15)
ms:contentKeyID: 48184288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2043c974654ba2a65b3d831cd65fef420e4b5708
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42206354"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-lync-server-2013-to-work-with-office-web-apps-server"></a><span data-ttu-id="646b0-102">Office Web Apps 서버에서 작동 하도록 Lync Server 2013 구성</span><span class="sxs-lookup"><span data-stu-id="646b0-102">Configuring Lync Server 2013 to work with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="646b0-103">_**마지막으로 수정 된 항목:** 2013-04-22_</span><span class="sxs-lookup"><span data-stu-id="646b0-103">_**Topic Last Modified:** 2013-04-22_</span></span>

<span data-ttu-id="646b0-104">Office Web Apps 서버를 사용 하도록 Lync Server 2013을 구성 하려면 먼저 Office Web Apps 서버를 배포 및 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="646b0-104">Before you can configure Lync Server 2013 to use Office Web Apps Server, Office Web Apps Server must be deployed and configured.</span></span> <span data-ttu-id="646b0-105">단일 Office Web Apps Server를 설치 및 구성하는 방법에 또는 고가용성을 위해 Office Web Apps Server 팜을 설치하고 구성하는 방법에 대한 자세한 내용은 **Office Web Apps Server 및 Office Web Apps 배포 지침** 문서를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="646b0-105">See the document **Guide to Deploying Office Web Apps Server and Office Web Apps** for detail information on how to install and configure a single Office Web Apps Server, or for information on how to install and configure an Office Web Apps Server Farm for high availability.</span></span>

<span data-ttu-id="646b0-106">Office Web Apps 서버를 성공적으로 설치 하 고 웹 팜을 올바르게 구성한 후에는 새 서버와 통신 하도록 Lync Server를 구성 해야 합니다. 이 작업은 Office Web Apps 서버 검색 URL을 Lync Server 토폴로지에 추가 하 여 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="646b0-106">After Office Web Apps Server has been successfully installed and your Web farm correctly configured, you must then configure Lync Server to communicate with the new server; this is done by adding the Office Web Apps Server discovery URL to your Lync Server topology.</span></span> <span data-ttu-id="646b0-107">Office Web Apps 서버를 토폴로지에 추가 하려면 다음 단계를 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="646b0-107">To add Office Web Apps Server to your topology, complete the following steps:</span></span>

1.  <span data-ttu-id="646b0-108">**시작**, **모든 프로그램**, **Microsoft lync server 2013**을 차례로 클릭 한 다음 **Lync server 토폴로지 작성기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="646b0-108">Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Topology Builder**.</span></span>

2.  <span data-ttu-id="646b0-109">**토폴로지 작성기** 대화 상자에서 **기존 배포에서 토폴로지 다운로드**를 선택한 후 **확인**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="646b0-109">In the **Topology Builder** dialog box, select **Download Topology from existing deployment** and then click **OK**.</span></span>

3.  <span data-ttu-id="646b0-p103">**토폴로지를 다른 이름으로 저장** 대화 상자에서 **파일 이름** 상자에 토폴로지 문서 이름(예: **PreWebAppsServerTopology**)을 입력한 후 **저장**을 클릭합니다. 이 토폴로지는 나중에 새 토폴로지에 문제가 발생한 경우 검색하고 다시 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="646b0-p103">In the **Save Topology As** dialog box, type a name for your topology document (for example, **PreWebAppsServerTopology**) in the **File name** box and then click **Save**. This topology can later be retrieved and republished if you encounter problems with your new topology.</span></span>

4.  <span data-ttu-id="646b0-112">토폴로지 작성기에서 **Lync Server 2013**, 사이트 이름, **Enterprise Edition 프런트 엔드 풀**을 차례로 확장 하 고 풀 중 하나의 이름을 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="646b0-112">In Topology Builder, expand **Lync Server 2013**, expand the name of your site, expand **Enterprise Edition Front End pools**, right-click the name of one of your pools, and then click **Edit Properties**.</span></span>

5.  <span data-ttu-id="646b0-113">**속성 편집** 대화 상자의 **일반** 탭에서 **Office Web Apps Server 연결** 제목을 찾아서 **새로 만들기**를 클릭합니다(또는 드롭다운 목록에서 기존 Office Web Apps Server 선택).</span><span class="sxs-lookup"><span data-stu-id="646b0-113">In the **Edit Properties** dialog box, on the **General** tab, find the heading **Associate Office Web Apps Server** and then click **New** (or select an existing Office Web Apps Server from the drop-down list).</span></span>

6.  <span data-ttu-id="646b0-114">**새 Office Web Apps Server 정의** 대화 상자에서 **Office Web Apps Server FQDN** 상자에 Office Web Apps Server 컴퓨터의 FQDN(정규화된 도메인 이름)을 입력합니다. 이렇게 하면 Office Web Apps Server 검색 URL이 **Office Web Apps Server 검색 URL** 상자에 자동으로 입력됩니다.</span><span class="sxs-lookup"><span data-stu-id="646b0-114">In the **Define New Office Web Apps Server** dialog box, type the fully qualified domain name (FQDN) of your Office Web Apps Server computer in the **Office Web Apps Server FQDN** box; when you do this, your Office Web Apps Server discovery URL should automatically be entered into the **Office Web Apps Server discovery URL** box.</span></span>
    
    <span data-ttu-id="646b0-115">Office Web Apps 서버를 Lync Server 2013와 동일한 네트워크 영역에 설치 하는 경우에는 **Office Web Apps 서버를 외부 네트워크 (경계/인터넷)에 배포** 하는 옵션을 선택 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="646b0-115">If the Office Web Apps Server is installed on-premises and in the same network zone as Lync Server 2013 then the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)** should not be selected.</span></span>
    
    <span data-ttu-id="646b0-116">Office Web Apps Server가 내부 방화벽 외부에 배포된 경우 **Office Web Apps Server가 외부 네트워크에 배포되어 있습니다(경계/인터넷).** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="646b0-116">If the Office Web Apps Server is deployed outside your internal firewall, then select the option **Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**.</span></span>

7.  <span data-ttu-id="646b0-p104">**새 Office Web Apps Server 정의** 대화 상자에서 **확인**을 클릭한 후 **속성 편집** 대화 상자에서 **확인**을 클릭합니다. 그러면 Office Web Apps 검색 URL이 풀의 연결 중 하나로 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="646b0-p104">In the **Define New Office Web Apps Server** dialog box, click **OK**, and then click **OK** in the **Edit Properties** dialog box. The Office Web Apps discovery URL will then be listed as one of the pool's Associations.</span></span>

<span data-ttu-id="646b0-119">Office Web Apps Server와 연결해야 하는 각 풀에 대해 이 프로세스를 반복해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="646b0-119">You will have to repeat this process for each pool that needs to be associated with your Office Web Apps Server.</span></span>

<span data-ttu-id="646b0-p105">토폴로지에 검색 URL을 추가한 후에는 이 업데이트된 토폴로지를 게시해야 합니다. 이렇게 하려면 토폴로지 작성기에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="646b0-p105">After you have added the discovery URL to the topology you must then publish this updated topology. To do that in Topology Builder:</span></span>

1.  <span data-ttu-id="646b0-122">**동작**을 클릭하고, **토폴로지 게시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="646b0-122">Click **Action** and then click **Publish Topology**.</span></span>

2.  <span data-ttu-id="646b0-123">토폴로지 게시 마법사의 **토폴로지 게시** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="646b0-123">In the Publish Topology wizard, on the **Publish the Topology** page, click **Next**.</span></span>

3.  <span data-ttu-id="646b0-124">**게시 마법사 완료** 페이지에서 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="646b0-124">On the **Publishing wizard complete** page, click **Finish**.</span></span>

4.  <span data-ttu-id="646b0-125">토폴로지 작성기를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="646b0-125">Close Topology Builder.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

