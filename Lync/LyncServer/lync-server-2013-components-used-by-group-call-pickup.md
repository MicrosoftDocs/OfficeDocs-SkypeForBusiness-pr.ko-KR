---
title: 'Lync Server 2013: 그룹 통화 픽업에서 사용 되는 구성 요소'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components used by Group Call Pickup
ms:assetid: 45db2f23-d486-4b20-a8cf-7b48a1f9fd3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945625(v=OCS.15)
ms:contentKeyID: 51541470
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 062dc114534abb7d2a011c31b9747c2d6a0a45bb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502365"
---
# <a name="components-used-by-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="7f122-102">Lync Server 2013의 그룹 통화 픽업에서 사용 되는 구성 요소</span><span class="sxs-lookup"><span data-stu-id="7f122-102">Components used by Group Call Pickup in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f122-103">_**마지막으로 수정 된 항목:** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="7f122-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="7f122-104">그룹 통화 픽업 기능은 Enterprise Voice 및 통화 대기 응용 프로그램을 배포할 때 자동으로 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f122-104">Group Call Pickup is automatically deployed when you deploy Enterprise Voice and the Call Park application.</span></span> <span data-ttu-id="7f122-105">통화 대기 번호 표는 call pickup 그룹 번호로 지정 된 별도의 숫자 범위로 구성한 다음, 사용자를 지정 하 여 pickup 그룹에 전화를 걸어 사용자를 그룹 통화 픽업으로 설정 하 여 그룹 통화 픽업을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f122-105">You enable Group Call Pickup by configuring the Call Park orbit table with separate ranges of numbers designated as call pickup group numbers, and then by assigning users to call pickup groups and enabling the users for Group Call Pickup.</span></span> <span data-ttu-id="7f122-106">다음 Lync Server 구성 요소는 그룹 통화 픽업를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f122-106">The following Lync Server components support Group Call Pickup:</span></span>

  - <span data-ttu-id="7f122-107">**응용 프로그램 서비스**     응용 프로그램 서비스는 통화 대기 응용 프로그램 등의 통합 통신 응용 프로그램을 배포, 호스팅 및 관리 하기 위한 플랫폼을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f122-107">**Application service**   Application service provides a platform for deploying, hosting, and managing unified communications applications, such as the Call Park application.</span></span> <span data-ttu-id="7f122-108">응용 프로그램 서비스는 프런트 엔드 풀의 모든 프런트 엔드 서버와 모든 Standard Edition 서버에 자동으로 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f122-108">Application service is automatically installed on every Front End Server in a Front End pool and on every Standard Edition server.</span></span>

  - <span data-ttu-id="7f122-109">**통화 대기 응용 프로그램**     통화 대기 응용 프로그램은 응용 프로그램 서비스에서 호스팅하는 통합 통신 응용 프로그램 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="7f122-109">**Call Park application**   The Call Park application is one of the unified communications applications that are hosted by Application service.</span></span> <span data-ttu-id="7f122-110">그룹 통화 픽업는 통화 대기 응용 프로그램을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f122-110">Group Call Pickup is based on the Call Park application.</span></span>

  - <span data-ttu-id="7f122-111">**Lync Server 관리 셸**     Lync Server 관리 셸을 사용 하 여 그룹 통화 픽업 그룹을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f122-111">**Lync Server Management Shell**   You use Lync Server Management Shell to manage Group Call Pickup groups.</span></span>

  - <span data-ttu-id="7f122-112">**SEFAUtil resource kit 도구**     SEFAUtil (보조 확장 기능 정품 인증 유틸리티)를 사용 하 여 사용자를 통화 픽업 그룹에 할당 하 고 사용자를 위해 call pickup를 사용 하거나 사용 하지 않도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f122-112">**SEFAUtil resource kit tool**   You use the secondary extension feature activation utility (SEFAUtil) to assign users to a call pickup group and to enable or disable call pickup for users.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

