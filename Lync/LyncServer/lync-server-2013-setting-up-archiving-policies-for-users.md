---
title: 'Lync Server 2013: 사용자에 대 한 보관 정책 설정'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Archiving policies for users
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204722(v=OCS.15)
ms:contentKeyID: 48183549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5adef442b4e890a8f157208aa6e7055725c014e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a><span data-ttu-id="0e4c3-102">Lync Server 2013에서 사용자에 대 한 보관 정책 설정</span><span class="sxs-lookup"><span data-stu-id="0e4c3-102">Setting up Archiving policies for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e4c3-103">_**마지막으로 수정 된 항목:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="0e4c3-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="0e4c3-104">사용자에 대해 보관 정책을 만들고 구성한 다음 특정 사용자 또는 사용자 그룹에 정책을 적용하여 특정 사용자에 대해 보관을 사용하거나 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-104">You can enable or disable Archiving for specific users by creating and configuring an Archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="0e4c3-105">사용자 정책은 글로벌 정책 또는 사이트 정책을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-105">User policies override any global policy or site policies.</span></span> <span data-ttu-id="0e4c3-106">보관 정책은 Microsoft Exchange 통합을 사용 하지 않는 경우 또는 Microsoft Exchange 통합을 사용 하는 경우에만 적용 되 고 Exchange 2013에 포함 되지 않고 사서함을 원본 위치 유지 상태로 설정 하는 일부 사용자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-106">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="0e4c3-107">전역, 사이트 및 사용자 정책의 계층 구조를 비롯 하 여 보관 정책이 작동 하는 방식에 대 한 자세한 내용은 Lync Server 2013 계획 설명서, 배포 설명서 또는 작업 설명서 [에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0e4c3-108">배포에 Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange 원본 위치 유지 정책은 Exchange 2013에 있는 사용자에 대해 보관을 사용 하도록 설정할지 여부를 제어 하 고 사서함을 원본 위치 유지 상태로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-108">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="0e4c3-109">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange Server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="0e4c3-110">보관 정책에서 내부 또는 외부 통신의 보관을 사용하도록 설정하기 전에 보관 구성에서 해당하는 모든 옵션을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-110">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="0e4c3-111">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013의 보관 옵션 구성을</A> 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="0e4c3-111">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0e4c3-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="0e4c3-112">In This Section</span></span>

  - [<span data-ttu-id="0e4c3-113">Lync Server 2013에서 보관용 사용자 정책 설정</span><span class="sxs-lookup"><span data-stu-id="0e4c3-113">Setting up user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="0e4c3-114">Exchange Server 통합을 사용 하는 경우 Lync Server 2013에서 보관용 정책 설정</span><span class="sxs-lookup"><span data-stu-id="0e4c3-114">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

