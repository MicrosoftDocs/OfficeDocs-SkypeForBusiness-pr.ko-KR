---
title: 'Lync Server 2013: 스키마 복제 확인'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d115738a4f22cb7795c2eb5a00ac642fbe43fc77
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40983172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a><span data-ttu-id="b39d3-102">Lync Server 2013에서 Active Directory 스키마 복제 확인</span><span class="sxs-lookup"><span data-stu-id="b39d3-102">Verifying Active Directory schema replication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b39d3-103">_**마지막으로 수정한 주제:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="b39d3-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="b39d3-104">포리스트 준비를 실행 하기 전에 스키마 파티션이 복제 되었는지 수동으로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b39d3-104">Before you run forest preparation, manually verify that the schema partition has been replicated.</span></span>

<div>

## <a name="to-manually-verify-schema-replication"></a><span data-ttu-id="b39d3-105">수동으로 스키마 복제를 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="b39d3-105">To manually verify schema replication</span></span>

1.  <span data-ttu-id="b39d3-106">엔터프라이즈 관리자 그룹의 구성원으로 도메인 컨트롤러에 로그온 합니다.</span><span class="sxs-lookup"><span data-stu-id="b39d3-106">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="b39d3-107">**시작**을 클릭 하 고 **관리 도구**를 클릭 한 다음 **adsi 편집**을 클릭 하 여 adsi 편집을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b39d3-107">Open ADSI Edit by clicking **Start**, clicking **Administrative Tools**, and then clicking **ADSI Edit**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="b39d3-108">또는 명령줄에서 <STRONG>adsiedit</STRONG> 를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b39d3-108">Alternatively, you can run <STRONG>adsiedit.msc</STRONG> from the command line.</span></span>

    
    </div>

3.  <span data-ttu-id="b39d3-109">MMC (Microsoft Management Console) 트리에서 아직 선택 하지 않은 경우 **ADSI 편집**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b39d3-109">In the Microsoft Management Console (MMC) tree, if it is not already selected, click **ADSI Edit**.</span></span>

4.  <span data-ttu-id="b39d3-110">**작업** 메뉴에서 **연결 대상**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b39d3-110">On the **Action** menu, click **Connect to**.</span></span>

5.  <span data-ttu-id="b39d3-111">**연결 설정** 대화 상자의 **잘 알려진 명명 컨텍스트 선택**에서 **스키마**를 선택한 다음 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="b39d3-111">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>

6.  <span data-ttu-id="b39d3-112">스키마 컨테이너 아래에서 CN = ms-RTC-SIP-SchemaVersion을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="b39d3-112">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="b39d3-113">이 개체가 존재 하 고, **Range upper** 특성의 값이 1150이 고, **range lower** 특성의 값이 3 이면 스키마가 성공적으로 업데이트 되 고 복제 된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b39d3-113">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="b39d3-114">이 개체가 없거나 **Range upper** 및 **range lower** 특성 값이 지정 되지 않은 경우 스키마는 수정 되거나 복제 되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b39d3-114">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b39d3-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b39d3-115">See Also</span></span>


[<span data-ttu-id="b39d3-116">Lync Server 2013에서 Active Directory 스키마 준비 실행</span><span class="sxs-lookup"><span data-stu-id="b39d3-116">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)  


[<span data-ttu-id="b39d3-117">Lync Server 2013에서 Active Directory 스키마 준비</span><span class="sxs-lookup"><span data-stu-id="b39d3-117">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

