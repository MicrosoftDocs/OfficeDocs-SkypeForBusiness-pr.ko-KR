---
title: 'Lync Server 2013: 업데이트된 토폴로지 게시'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9f3be1443f98444712a66942417e1812181efe7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a><span data-ttu-id="62678-102">Lync Server 2013에서 업데이트된 토폴로지 게시</span><span class="sxs-lookup"><span data-stu-id="62678-102">Publish the updated topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="62678-103">_**마지막으로 수정한 주제:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="62678-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="62678-104">토폴로지 작성기에서 토폴로지를 업데이트 한 후에는 영구 채팅 서버를 구성 하 고 사용할 수 있도록 먼저 토폴로지를 중앙 관리 저장소에 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="62678-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Persistent Chat Server.</span></span> <span data-ttu-id="62678-105">모든 서버가 토폴로지와 다른 구성 변경 사항과 동기화 되도록 유지 하기 위해 데이터의 읽기 전용 복사본이 토폴로지의 모든 서버에 복제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62678-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-an-updated-topology"></a><span data-ttu-id="62678-106">업데이트 된 토폴로지를 게시 하려면</span><span class="sxs-lookup"><span data-stu-id="62678-106">To publish an updated topology</span></span>

<span data-ttu-id="62678-107">토폴로지를 게시 하기 전에 영구 채팅 서버용 데이터베이스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="62678-107">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="62678-108">**작업** 및 **데이터베이스 설치**를 선택 하 여 토폴로지 작성기를 사용 하 여 데이터베이스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="62678-108">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>

1.  <span data-ttu-id="62678-109">Lync Server 2013을 실행 하거나 Lync Server 관리 도구가 설치 되어 있는 컴퓨터에서 **도메인 관리자** 그룹과 **RTCUniversalServerAdmins** 그룹 모두의 구성원 인 계정을 사용 하 여 로그온 하 고, 영구적 채팅 서버 파일 저장소에 사용할 파일 저장소에 대 한 모든 권한 (즉, 읽기, 쓰기 및 수정)이 있으며,이는 토폴로지 작성기가 필수 dacl (임의 액세스 제어 목록)을 구성할 수 있도록 하는 계정 이거나 해당 사용자 권한이 있는 계정을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="62678-109">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>

2.  <span data-ttu-id="62678-110">토폴로지 작성기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="62678-110">Start Topology Builder.</span></span> <span data-ttu-id="62678-111">**기존 배포에서 토폴로지 다운로드**를 선택 하거나 **로컬 파일을 로컬로 저장 한 경우에는 토폴로지를 엽니다** .</span><span class="sxs-lookup"><span data-stu-id="62678-111">Select **Download Topology from existing deployment**, or **Open Topology from a local file** if you saved it locally.</span></span>

3.  <span data-ttu-id="62678-112">콘솔 트리에서 **Lync Server 2013**을 마우스 오른쪽 단추로 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="62678-112">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="62678-113">**토폴로지 게시** 페이지에서 **다음**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="62678-113">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="62678-114">**게시 마법사 완료** 페이지에서 토폴로지가 성공적으로 게시 되었는지 확인 한 다음 **마침을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="62678-114">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="62678-115">토폴로지를 게시 한 후에는 영구 채팅 서버에 대 한 지원을 구성 해야 콘텐츠를 보관할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62678-115">After publishing the topology, you must configure support for Persistent Chat Server before any content can be archived.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

