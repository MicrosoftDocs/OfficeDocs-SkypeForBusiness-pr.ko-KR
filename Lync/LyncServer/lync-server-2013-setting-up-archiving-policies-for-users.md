---
title: 'Lync Server 2013: 사용자의 보관 정책 설정'
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
ms.openlocfilehash: 0c3f2be2a41aae741a2dae5e3becb522dead8754
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732238"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a><span data-ttu-id="eef6f-102">Lync Server 2013에서 사용자에 대 한 보관 정책 설정</span><span class="sxs-lookup"><span data-stu-id="eef6f-102">Setting up Archiving policies for users in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eef6f-103">_**마지막으로 수정한 주제:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="eef6f-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="eef6f-104">사용자의 보관 정책을 만들고 구성한 다음 특정 사용자 또는 사용자 그룹에 정책을 적용 하 여 특정 사용자에 대해 보관을 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eef6f-104">You can enable or disable Archiving for specific users by creating and configuring an Archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="eef6f-105">사용자 정책은 모든 글로벌 정책 또는 사이트 정책에 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="eef6f-105">User policies override any global policy or site policies.</span></span> <span data-ttu-id="eef6f-106">Microsoft Exchange 통합을 사용 하지 않는 경우 또는 Microsoft Exchange 통합을 사용 하는 경우 Exchange 2013에 없고 사서함이 원본 위치 유지에 저장 되어 있는 사용자가 있는 경우에만 보관 정책이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="eef6f-106">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="eef6f-107">전역, 사이트 및 사용자 정책에 대 한 계층 구조를 포함 하 여 보관 정책이 작동 하는 방법에 대 한 자세한 내용은 Lync Server 2013 계획 설명서, 배포 설명서 또는 운영 설명서 [에서 보관을 사용 하는 방법을](lync-server-2013-how-archiving-works.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eef6f-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eef6f-108">배포에 Microsoft Exchange 통합을 사용 하도록 설정 하는 경우 Exchange 원본 위치 유지 정책은 Exchange 2013에 있는 사용자에 대해 보관을 사용할 수 있는지 여부를 제어 하 고 사서함이 원본 위치 유지에 배치 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="eef6f-108">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="eef6f-109">자세한 내용은 배포 설명서에서 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Exchange server 통합을 사용 하는 경우 Lync server 2013에서 보관에 대 한 정책 설정을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eef6f-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="eef6f-110">보관 정책에서 내부 또는 외부 통신의 보관을 사용 하도록 설정 하기 전에 보관 구성에서 해당 옵션을 모두 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eef6f-110">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="eef6f-111">자세한 내용은 배포 설명서의 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013에서 보관 옵션 구성을</A> 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="eef6f-111">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="eef6f-112">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="eef6f-112">In This Section</span></span>

  - [<span data-ttu-id="eef6f-113">Lync Server 2013에서 보관을 위한 사용자 정책 설정</span><span class="sxs-lookup"><span data-stu-id="eef6f-113">Setting up user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="eef6f-114">Exchange Server 통합을 사용 하는 경우 Lync Server 2013에서 보관할 정책 설정</span><span class="sxs-lookup"><span data-stu-id="eef6f-114">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

