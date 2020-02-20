---
title: Exchange Server 통합을 사용할 때 보관용 정책 설정
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up policies for Archiving when using Exchange Server integration
ms:assetid: 8b9b2bad-a4b3-42e1-85a7-04022e9442ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205063(v=OCS.15)
ms:contentKeyID: 48184742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 948d57d753c774737d0a1c6b98bd24560d47606b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-policies-for-archiving-in-lync-server-2013-when-using-exchange-server-integration"></a><span data-ttu-id="ad4c8-102">Exchange Server 통합을 사용 하는 경우 Lync Server 2013에서 보관용 정책 설정</span><span class="sxs-lookup"><span data-stu-id="ad4c8-102">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad4c8-103">_**마지막으로 수정 된 항목:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="ad4c8-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="ad4c8-104">Exchange 2013에 있는 사용자가 사서함을 원본 위치 유지 상태로 설정 하면 Exchange 원본 위치 유지 정책에서 해당 사용자에 대 한 보관을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4c8-104">If users homed on Exchange 2013 have their mailboxes put on In-Place Hold, Exchange In-Place Hold policies control archiving for those users.</span></span> <span data-ttu-id="ad4c8-105">배포에 Microsoft Exchange 통합을 사용 하는 경우 Exchange 2013 정책은 Exchange 2013에 있는 사용자에 대 한 Lync Server 보관 정책을 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4c8-105">If you use Microsoft Exchange integration for your deployment, Exchange 2013 policies override Lync Server Archiving policies for users who are homed on Exchange 2013.</span></span> <span data-ttu-id="ad4c8-106">Exchange 보관 정책 구성에 대 한 자세한 내용은 Exchange 2013 설명서를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad4c8-106">For information about configuring Exchange Archiving policies, see the Exchange 2013 documentation.</span></span> <span data-ttu-id="ad4c8-107">Lync Server 2013에 있는 사용자에 대 한 사용자 정책을 설정 하는 방법에 대 한 자세한 내용은 배포 설명서의 [Lync server 2013에서 보관용 사용자 정책 설정을](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="ad4c8-107">For details about setting up user policies for users homed on Lync Server 2013, see [Setting up user policies for Archiving in Lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span> <span data-ttu-id="ad4c8-108">정책이 작동 하는 방식에 대 한 자세한 내용은 계획 설명서, 배포 설명서 또는 작업 설명서의 [Lync Server 2013에서 보관이 작동 하는 방식을](lync-server-2013-how-archiving-works.md) 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad4c8-108">For details about how policies work, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="ad4c8-109">동일한 포리스트에 Exchange 2013 및 Lync Server 2013을 배포 하는 경우 Exchange 2013 원본 위치 유지 정책에서 보관을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="ad4c8-109">If you deploy Exchange 2013 and Lync Server 2013 in the same forest, your Exchange 2013 In-Place Hold policies control archiving.</span></span> <span data-ttu-id="ad4c8-110">Exchange 2013 및 Lync Server 2013를 별도의 포리스트에 배포 하는 경우 <A href="lync-server-2013-deployment-checklist-for-archiving.md">배포 검사 목록에서 Lync server 2013의 보관을 위한</A>"lync Server 및 Microsoft Exchange를 다른 포리스트에서 배포"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ad4c8-110">If you deploy Exchange 2013 and Lync Server 2013 in separate forests, see “Deploying Lync Server and Microsoft Exchange in Different Forests” in <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

