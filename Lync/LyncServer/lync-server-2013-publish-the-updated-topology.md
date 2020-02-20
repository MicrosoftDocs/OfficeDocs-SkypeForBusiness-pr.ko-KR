---
title: 'Lync Server 2013: 업데이트 된 토폴로지 게시'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 589398c97a17f41f38394d5d3a57da4d3fec14ed
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a><span data-ttu-id="981e7-102">Lync Server 2013에서 업데이트 된 토폴로지 게시</span><span class="sxs-lookup"><span data-stu-id="981e7-102">Publish the updated topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="981e7-103">_**마지막으로 수정 된 항목:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="981e7-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="981e7-104">토폴로지 작성기에서 토폴로지를 업데이트 한 후에는 영구 채팅 서버를 구성 하 고 사용 하기 전에 토폴로지를 중앙 관리 저장소에 게시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="981e7-104">After updating your topology in Topology Builder, you must publish the topology to the Central Management store before you can configure and use Persistent Chat Server.</span></span> <span data-ttu-id="981e7-105">모든 서버가 토폴로지 및 기타 구성 변경 내용과 동기화되도록 데이터의 읽기 전용 복사본이 토폴로지의 모든 서버에 복제됩니다.</span><span class="sxs-lookup"><span data-stu-id="981e7-105">Read-only copies of the data are replicated to all servers in the topology to keep all servers in sync with topology and other configuration changes.</span></span>

<div>

## <a name="to-publish-an-updated-topology"></a><span data-ttu-id="981e7-106">업데이트된 토폴로지를 게시하려면</span><span class="sxs-lookup"><span data-stu-id="981e7-106">To publish an updated topology</span></span>

<span data-ttu-id="981e7-107">토폴로지를 게시 하기 전에 영구 채팅 서버용 데이터베이스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="981e7-107">Before you publish your topology, install the databases for Persistent Chat Server.</span></span> <span data-ttu-id="981e7-108">**작업** 및 **데이터베이스 설치**를 선택 하 여 토폴로지 작성기를 사용 하 여 데이터베이스를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="981e7-108">Use Topology Builder to install databases by selecting **Action** and **Install Database**.</span></span>

1.  <span data-ttu-id="981e7-109">Lync Server 2013을 실행 하거나 Lync Server 관리 도구를 설치 하는 컴퓨터에서 다음을 수행 합니다. **Domain Admins** 그룹 및 **RTCUniversalServerAdmins** 그룹의 구성원 인 계정을 사용 하 여 로그온 하 고, 영구 채팅 서버 파일 저장소에 사용할 파일 저장소에 대 한 모든 권한 (읽기, 쓰기 및 수정)을 포함 하는 (토폴로지 작성기가 필요한 임의 액세스 제어 목록 (dacl)를 구성할 수 있도록 함) 또는 이와 동등한 사용자 권한을 가진 계정으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="981e7-109">On a computer that is running Lync Server 2013 or on which the Lync Server administrative tools are installed, log on using an account that is a member of both the **Domain Admins** group and the **RTCUniversalServerAdmins** group, and that has full control permissions (that is, read, write, and modify) on the file store to be used for the Persistent Chat Server file store (so that Topology Builder can configure the required discretionary access control lists (DACLs)), or an account with equivalent user rights.</span></span>

2.  <span data-ttu-id="981e7-110">토폴로지 작성기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="981e7-110">Start Topology Builder.</span></span> <span data-ttu-id="981e7-111">**기존 배포에서 토폴로지 다운로드** 또는 **로컬 파일에서 토폴로지 열기**(로컬로 저장한 경우)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="981e7-111">Select **Download Topology from existing deployment**, or **Open Topology from a local file** if you saved it locally.</span></span>

3.  <span data-ttu-id="981e7-112">콘솔 트리에서 **Lync Server 2013**를 마우스 오른쪽 단추로 클릭 한 다음 **토폴로지 게시**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="981e7-112">In the console tree, right-click **Lync Server 2013**, and then click **Publish Topology**.</span></span>

4.  <span data-ttu-id="981e7-113">**토폴로지 게시** 페이지에서 **다음**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="981e7-113">On the **Publish the topology** page, click **Next**.</span></span>

5.  <span data-ttu-id="981e7-114">**게시 마법사 완료** 페이지에서 토폴로지가 게시되었는지 확인하고 **마침**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="981e7-114">On the **Publishing wizard complete** page, verify that the topology was successfully published, and then click **Finish**.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="981e7-115">토폴로지를 게시 한 후에는 콘텐츠를 보관 하기 전에 영구 채팅 서버에 대 한 지원을 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="981e7-115">After publishing the topology, you must configure support for Persistent Chat Server before any content can be archived.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

