---
title: 'Lync Server 2013: 통합 연락처 저장소 배포'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying unified contact store
ms:assetid: 68959d58-ac8a-45de-afcd-b9de2c36799c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204963(v=OCS.15)
ms:contentKeyID: 48184373
ms.date: 06/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a94d19026d2df00caf8079914d8b93bd70a87f6d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522855"
---
# <a name="deploying-unified-contact-store-in-lync-server-2013"></a><span data-ttu-id="06c2a-102">Lync Server 2013에서 통합 연락처 저장소 배포</span><span class="sxs-lookup"><span data-stu-id="06c2a-102">Deploying unified contact store in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06c2a-103">_**마지막으로 수정 된 항목:** 2016-06-06_</span><span class="sxs-lookup"><span data-stu-id="06c2a-103">_**Topic Last Modified:** 2016-06-06_</span></span>

<span data-ttu-id="06c2a-104">Lync Server 2013에서 통합 연락처 저장소를 사용 하도록 설정 하는 경우에는 토폴로지 설정이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06c2a-104">Enabling unified contact store in Lync Server 2013 does not require any topology settings.</span></span> <span data-ttu-id="06c2a-105">사용자에 대해 통합 연락처 저장소를 사용 하도록 설정 하려면 다음이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c2a-105">Enabling unified contact store for users requires the following:</span></span>

  - <span data-ttu-id="06c2a-106">통합 연락처 저장소 정책이 사용 하도록 설정 되어 있습니다 (기본값을 사용 하도록 설정 됨).</span><span class="sxs-lookup"><span data-stu-id="06c2a-106">Unified contact store policy is enabled (default is enabled).</span></span>

  - <span data-ttu-id="06c2a-107">사용자가 한 번 이상 Lync 2013을 사용 하 여 로그인 합니다.</span><span class="sxs-lookup"><span data-stu-id="06c2a-107">Users log in with Lync 2013 at least once.</span></span>

<span data-ttu-id="06c2a-108">사용자가 Lync 2013을 사용 하 여 로그인 할 때 자동으로 실행 되는 사용자의 연락처가 마이그레이션된 후 사용자는 Lync 2013, Outlook 2013 또는 Outlook Web Access에서 Lync 연락처에 액세스 하 고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06c2a-108">After a user’s contacts have been migrated, which happens automatically when a user logs in with Lync 2013, the user can access and manage their Lync contacts from Lync 2013, Outlook 2013, or Outlook Web Access.</span></span> <span data-ttu-id="06c2a-109">사용자는 Outlook 또는 Outlook Web Access에서 연락처를 관리 하기 위해 Lync에 로그인 할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06c2a-109">The user does not have to be logged in to Lync to manage their contacts from Outlook or Outlook Web Access.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="06c2a-110">사용자가 마이그레이션 후 Lync 2010에서 로그인 하는 경우, 연락처 및 그룹을 최신 상태로 사용할 수 있지만 사용자가 관리할 수는 없습니다 (즉, 해당 연락처를 추가, 삭제, 이동, 태그, 해도, 수정).</span><span class="sxs-lookup"><span data-stu-id="06c2a-110">If a user logs in from Lync 2010 after migration, contacts and groups are available and up-to-date, but the user cannot manage (that is, add, delete, move, tag, untag, or modify) those contacts.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="06c2a-111">이 섹션의 내용</span><span class="sxs-lookup"><span data-stu-id="06c2a-111">In This Section</span></span>

  - [<span data-ttu-id="06c2a-112">Lync Server 2013에서 통합 연락처 저장소에 사용자 사용</span><span class="sxs-lookup"><span data-stu-id="06c2a-112">Enable users for unified contact store in Lync Server 2013</span></span>](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [<span data-ttu-id="06c2a-113">Lync Server 2013에서 통합 연락처 저장소로 사용자 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="06c2a-113">Migrate users to unified contact store in Lync Server 2013</span></span>](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [<span data-ttu-id="06c2a-114">Lync Server 2013에서 마이그레이션된 사용자 롤백</span><span class="sxs-lookup"><span data-stu-id="06c2a-114">Roll back migrated users in Lync Server 2013</span></span>](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

