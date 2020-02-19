---
title: 위치를 수동으로 가져오기 위한 사용자 환경 정의
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining the user experience for manually acquiring a location
ms:assetid: d37f67d3-e248-483b-b64c-3986559ef357
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398912(v=OCS.15)
ms:contentKeyID: 48185435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20bd88f9c9f619e67c9aec8f6b0111320fa3ed2d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-the-user-experience-for-manually-acquiring-a-location-in-lync-server-2013"></a><span data-ttu-id="37413-102">Lync Server 2013에서 위치를 수동으로 가져오기 위한 사용자 환경 정의</span><span class="sxs-lookup"><span data-stu-id="37413-102">Defining the user experience for manually acquiring a location in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="37413-103">_**마지막으로 수정 된 항목:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="37413-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="37413-104">클라이언트가 네트워크 외부에 있거나 정의 되지 않은 서브넷에 있는 경우 사용자가 위치를 수동으로 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37413-104">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location.</span></span> <span data-ttu-id="37413-105">그러나 긴급 통화 중에는 통화가 공용 안전 응답 지점 (PSAP)으로 라우팅되도록 하기 전에 먼저 국내/지역별 E9-1-1 긴급 통화 응답 센터 (ECRC) 발송자에 게 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="37413-105">But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="37413-106">ECRC는 이동할에서 위치를 쿼리 한 다음 제공 된 정보에 따라 적절 한 PSAP로 통화를 착신 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="37413-106">The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span>

  - <span data-ttu-id="37413-107">**위치 정보 서비스에서 자동으로 제공 되지 않는 위치를 입력 하 라는 메시지가 표시 됩니까?**</span><span class="sxs-lookup"><span data-stu-id="37413-107">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>  
    <span data-ttu-id="37413-108">예를 들어 클라이언트가 정의 되지 않은 서브넷, 집, 호텔 또는 네트워크 외부의 다른 위치에 있는 경우 사용자가 위치를 입력 해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="37413-108">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
    <span data-ttu-id="37413-109">위치 정책에서 클라이언트 동작을 정의 하는 **위치** 설정을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37413-109">You can configure the **Location Required** setting in the location policy to define the client behavior.</span></span> <span data-ttu-id="37413-110">이 값을 No로 설정 하면 사용자에 게 위치를 입력 하 라는 메시지가 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37413-110">Setting this value to No means that the user will not be prompted for a location.</span></span> <span data-ttu-id="37413-111">이 값을 Yes로 설정 하면 사용자에 게 위치를 입력 하 라는 메시지가 표시 되지만 메시지를 닫을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37413-111">Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt.</span></span> <span data-ttu-id="37413-112">이 값을 고 지 수로 설정 하면 사용자에 게 위치를 입력 하 라는 메시지가 표시 되며 메시지를 다시 표시 하지 않을 경우 고 지 사항이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37413-112">Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt.</span></span> <span data-ttu-id="37413-113">모든 경우에 사용자는 평소와 같이 클라이언트를 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37413-113">In all cases, the user can continue to use the client as usual.</span></span>

<span data-ttu-id="37413-114">사용자가 위치를 수동으로 입력 하면 위치가 클라이언트 네트워크의 기본 게이트웨이의 MAC 주소에 매핑되고 클라이언트에 있는 사용자별 테이블에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37413-114">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client’s network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="37413-115">사용자가 이전에 저장 된 위치로 반환 되 면 Lync 클라이언트는 자동으로 해당 위치로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="37413-115">When the user returns to any previously stored location, the Lync client automatically sets itself to that location.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="37413-116">클라이언트의 현재 위치만 수정할 수 있지만 로컬 사용자의 테이블에 저장 된 모든 위치를 삭제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37413-116">You can modify only the current location of your client, but you can also delete any location stored in the local user’s table.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

