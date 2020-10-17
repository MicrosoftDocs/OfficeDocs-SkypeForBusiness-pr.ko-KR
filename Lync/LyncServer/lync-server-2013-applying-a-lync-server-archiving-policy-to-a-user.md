---
title: 'Lync Server 2013: 사용자에 게 Lync Server 보관 정책 적용'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying a Lync Server Archiving policy to a user
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205143(v=OCS.15)
ms:contentKeyID: 48185024
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2cad9784eb2c50662bfedc460cb0dbc8c892206c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504935"
---
# <a name="applying-a-lync-server-archiving-policy-to-a-user-in-lync-server-2013"></a><span data-ttu-id="7ddd2-102">Lync Server 2013의 사용자에 게 Lync Server 보관 정책 적용</span><span class="sxs-lookup"><span data-stu-id="7ddd2-102">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ddd2-103">_**마지막으로 수정 된 항목:** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="7ddd2-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="7ddd2-104">Lync Server 사용자 정책을 만든 후에는 Lync Server 2013에 있는 특정 사용자 또는 사용자 그룹에 적용 하 여 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ddd2-104">After creating a Lync Server user policy, you must apply it to specific the users or user groups that are homed on Lync Server 2013 before it can take effect.</span></span> <span data-ttu-id="7ddd2-105">특정 사용자에 대 한 사용자 정책을 만드는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync Server 2013에서 보관용 사용자 정책 만들기 및 구성을](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ddd2-105">For details about creating user policies for specific users, see [Creating and configuring user policies for Archiving in Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="7ddd2-106">전역, 사이트 및 사용자 정책의 계층 구조를 비롯 하 여 보관 정책이 작동 하는 방식에 대 한 자세한 내용은 계획 설명서, 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ddd2-106">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7ddd2-107">보관을 구성 및 사용 하려면 먼저 보관을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ddd2-107">In order to configure and use archiving, you must first deploy archiving.</span></span> <span data-ttu-id="7ddd2-108">자세한 내용은 배포 설명서의 <A href="lync-server-2013-deploying-archiving.md">Lync Server 2013에서 보관 배포</A> 를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ddd2-108">For details, see <A href="lync-server-2013-deploying-archiving.md">Deploying Archiving in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="7ddd2-109">배포에 Microsoft Exchange 통합을 사용 하도록 설정한 경우 exchange 2013에 있는 사용자에 대해 보관을 사용 하도록 설정 하 고 사서함을 In-Place 보류에 In-Place 여부를 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ddd2-109">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="7ddd2-110">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ddd2-110">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="7ddd2-111">보관을 사용하도록 설정하기 전에 보관 구성에서 모든 해당 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ddd2-111">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="7ddd2-112">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013의 보관 옵션 구성을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ddd2-112">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-apply-a-lync-server-archiving-policy-to-a-user"></a><span data-ttu-id="7ddd2-113">사용자에 게 Lync Server 보관 정책을 적용 하려면</span><span class="sxs-lookup"><span data-stu-id="7ddd2-113">To apply a Lync Server archiving policy to a user</span></span>

1.  <span data-ttu-id="7ddd2-114">CsArchivingAdministrator 또는 CsAdministrator 역할에 할당된 사용자 계정에서 내부 배포된 컴퓨터에 로그온합니다.</span><span class="sxs-lookup"><span data-stu-id="7ddd2-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7ddd2-115">브라우저 창을 연 다음 Admin URL을 입력 하 여 Lync Server 2013 제어판을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7ddd2-115">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="7ddd2-116">Lync Server 2013 제어판을 시작 하는 데 사용할 수 있는 다양 한 방법에 대 한 자세한 내용은 [Open Lync server 2013 관리 도구](lync-server-2013-open-lync-server-administrative-tools.md)를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ddd2-116">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7ddd2-117">왼쪽 탐색 모음에서 **사용자**를 클릭하고 구성하려는 사용자 계정을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7ddd2-117">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>

4.  <span data-ttu-id="7ddd2-118">검색 결과가 나열된 표에서 사용자 계정을 클릭하고 **편집**을 클릭한 후에 **세부 정보 표시**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7ddd2-118">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="7ddd2-119">**보관 정책**아래의 **Lync Server 사용자 편집** 에서 적용 하려는 보관 사용자 정책을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ddd2-119">In **Edit Lync Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7ddd2-120"><STRONG> &lt; 자동 &gt; </STRONG> 설정은 기본 서버 설치 설정을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ddd2-120">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings.</span></span> <span data-ttu-id="7ddd2-121">이러한 설정은 서버에 의해 자동으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ddd2-121">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="7ddd2-122">**커밋**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="7ddd2-122">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

