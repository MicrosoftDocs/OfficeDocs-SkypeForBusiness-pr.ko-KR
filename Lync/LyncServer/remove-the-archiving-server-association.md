---
title: 보관 서버 연결 제거
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove the Archiving server association
ms:assetid: dabac157-71ee-4afe-b0b6-4a083d165ffb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721903(v=OCS.15)
ms:contentKeyID: 49733837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 04ab171493890c610e0f11b7cd124c7c2e1c600c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-the-archiving-server-association"></a><span data-ttu-id="ceb79-102">보관 서버 연결 제거</span><span class="sxs-lookup"><span data-stu-id="ceb79-102">Remove the Archiving server association</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ceb79-103">_**마지막으로 수정한 주제:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="ceb79-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="ceb79-104">보관 서버를 제거 하려면 연결 된 프런트 엔드 풀, 프런트 엔드 서버, Survivable Branch 기기 및 Survivable Branch 서버에 대 한 종속성을 변경 하거나 선택 취소 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb79-104">To remove an Archiving Server, you need to change or clear the dependency on the associated Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server.</span></span> <span data-ttu-id="ceb79-105">프런트 엔드 풀, 프런트 엔드 서버, Survivable Branch 기기 및 Survivable Branch 서버의 속성을 편집 하 여 종속성을 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb79-105">You edit the properties of the Front End pool, Front End Server, Survivable Branch Appliance and Survivable Branch Server to remove the dependency.</span></span> <span data-ttu-id="ceb79-106">종속성을 지우고 토폴로지 작성기에서 서버를 삭제 하면 토폴로지 작성기의 관련 데이터베이스 저장소 개체도 삭제 된다는 알림이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ceb79-106">After you clear the dependency and you delete the server in Topology Builder, you are notified that the associated database store object in Topology Builder will also be deleted.</span></span>

<div>

## <a name="to-remove-the-archiving-server-association"></a><span data-ttu-id="ceb79-107">보관 서버 연결을 제거 하려면</span><span class="sxs-lookup"><span data-stu-id="ceb79-107">To remove the Archiving Server association</span></span>

1.  <span data-ttu-id="ceb79-108">Lync Server 2013 프런트 엔드 서버를 열고 토폴로지 작성기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ceb79-108">Open the Lync Server 2013 Front End Server, open Topology Builder.</span></span>

2.  <span data-ttu-id="ceb79-109">Lync Server 2010 노드로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb79-109">Navigate to the Lync Server 2010 node.</span></span>

3.  <span data-ttu-id="ceb79-110">토폴로지 작성기에서 보관 서버가 정의 된 위치에 따라 **Enterprise Edition 프런트 엔드 풀**, **Standard Edition 프런트 엔드 서버**또는 **분기 사이트**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb79-110">In Topology Builder, expand **Enterprise Edition Front End pools**, **Standard Edition Front End Servers**, or **Branch sites**, based on where the Archiving Server is defined.</span></span>

4.  <span data-ttu-id="ceb79-111">연결 된 Survivable Branch 서버가 있는 경우 **분기**사이트를 확장 하 고 분기 사이트 이름을 확장 한 다음 **Survivable branch 기기**를 확장 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb79-111">If you have Survivable Branch Server associated, expand **Branch sites**, expand the branch site name, and then expand **Survivable Branch Appliances**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ceb79-112">사용자 인터페이스의 <STRONG>Survivable Branch 기기</STRONG> 는 Survivable branch 서버와 Survivable branch 기기 둘 다에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ceb79-112"><STRONG>Survivable Branch Appliances</STRONG> in the user interface applies to both Survivable Branch Server and Survivable Branch Appliance.</span></span>

    
    </div>

5.  <span data-ttu-id="ceb79-113">보관 서버와 연결 된 풀, 서버 또는 장치를 마우스 오른쪽 단추로 클릭 한 다음 **속성 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb79-113">Right-click the pool, server, or device that is associated with the Archiving Server, and then click **Edit Properties**.</span></span>

6.  <span data-ttu-id="ceb79-114">**속성 편집**의 **일반**아래에 있는 **연결**에서 **보관 서버 연결** 확인란의 선택을 취소 한 다음 **확인을**클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb79-114">In **Edit Properties**, under **General**, under **Associations**, clear the **Associate Archiving Server** check box, and then click **OK**.</span></span>

7.  <span data-ttu-id="ceb79-115">제거 하려는 보관 서버와 연결 된 다른 풀, 서버 또는 장치에 대해 앞의 단계를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb79-115">Repeat the previous step for any other pool, server or device associated with the Archiving Server that you want to remove.</span></span>

8.  <span data-ttu-id="ceb79-116">보관 서버를 마우스 오른쪽 단추로 클릭 한 다음 **삭제**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb79-116">Right-click the Archiving Server, and then click **Delete**.</span></span>

9.  <span data-ttu-id="ceb79-117">**종속 저장소 삭제**에서 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb79-117">On **Delete Dependent Stores**, click **OK**.</span></span>

10. <span data-ttu-id="ceb79-118">토폴로지를 게시 하 고, 복제 상태를 확인 한 다음 필요에 따라 Lync Server 배포 마법사를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="ceb79-118">Publish the topology, check replication status, and then run the Lync Server Deployment Wizard as needed.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

