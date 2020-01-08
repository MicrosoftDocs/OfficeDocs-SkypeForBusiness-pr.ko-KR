---
title: 'Lync Server 2013: 통합 연락처 저장소 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying unified contact store
ms:assetid: 68959d58-ac8a-45de-afcd-b9de2c36799c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204963(v=OCS.15)
ms:contentKeyID: 48184373
ms.date: 06/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94f4c52eb3adda31f32de410f139154788fa37e9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="99150-102">Lync Server 2013에서 통합 연락처 저장소 배포</span><span class="sxs-lookup"><span data-stu-id="99150-102">Deploying unified contact store in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="99150-103">_**마지막으로 수정한 주제:** 2016-06-06_</span><span class="sxs-lookup"><span data-stu-id="99150-103">_**Topic Last Modified:** 2016-06-06_</span></span>

<span data-ttu-id="99150-104">Lync Server 2013에서 통합 된 연락처 저장소를 사용 하도록 설정 하는 경우에는 토폴로지 설정이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="99150-104">Enabling unified contact store in Lync Server 2013 does not require any topology settings.</span></span> <span data-ttu-id="99150-105">사용자를 위해 통일 된 연락처 저장소를 사용 하도록 설정 하려면 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="99150-105">Enabling unified contact store for users requires the following:</span></span>

  - <span data-ttu-id="99150-106">통합 된 대화 상대 저장소 정책을 사용할 수 있습니다 (기본값 사용 가능).</span><span class="sxs-lookup"><span data-stu-id="99150-106">Unified contact store policy is enabled (default is enabled).</span></span>

  - <span data-ttu-id="99150-107">사용자가 최소한 한 번 Lync 2013으로 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="99150-107">Users log in with Lync 2013 at least once.</span></span>

<span data-ttu-id="99150-108">사용자가 Lync 2013을 사용 하 여 로그인 할 때 자동으로 발생 하는 사용자의 연락처를 마이그레이션한 후에는 사용자가 lync 2013, Outlook 2013 또는 Outlook Web Access에서 Lync 연락처에 액세스 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="99150-108">After a user’s contacts have been migrated, which happens automatically when a user logs in with Lync 2013, the user can access and manage their Lync contacts from Lync 2013, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="99150-109">사용자는 Outlook 또는 Outlook Web Access에서 연락처를 관리 하기 위해 Lync에 로그인 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99150-109">The user does not have to be logged in to Lync to manage their contacts from Outlook or Outlook Web Access.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="99150-110">사용자가 마이그레이션 후 Lync 2010에서 로그인 한 경우에는 연락처 및 그룹을 사용할 수 있지만, 사용자는 해당 연락처를 관리 (추가, 삭제, 이동, 태그 지정, untag 또는 수정) 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="99150-110">If a user logs in from Lync 2010 after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="99150-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="99150-111">In This Section</span></span>

  - [<span data-ttu-id="99150-112">Lync Server 2013에서 통합 연락처 저장소에 사용자 사용</span><span class="sxs-lookup"><span data-stu-id="99150-112">Enable users for unified contact store in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [<span data-ttu-id="99150-113">Lync Server 2013에서 통합 연락처 저장소로 사용자 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="99150-113">Migrate users to unified contact store in Lync Server 2013</span></span>](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [<span data-ttu-id="99150-114">Lync Server 2013에서 마이그레이션된 사용자 롤백</span><span class="sxs-lookup"><span data-stu-id="99150-114">Roll back migrated users in Lync Server 2013</span></span>](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

